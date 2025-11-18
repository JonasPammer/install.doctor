# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Install Doctor is a cross-platform desktop provisioning and dotfile management system designed to automate workstation setup and enable complete environment reproducibility. The project philosophy: "Bash all your computers to bits with a hammer and resurrect them the next day" by storing stateful data in encrypted S3 buckets and automating desktop configuration.

**Key Technologies:**
- **Chezmoi** - Orchestrates the entire provisioning process using scripts and templates
- **ZX (Google)** - JavaScript-based shell scripting for software installation
- **Task (go-task)** - Build automation with 103 modular taskfiles
- **Ansible** - Optional provisioning for complex setups (legacy/fallback)

**Supported Platforms:**
- macOS (Darwin)
- Linux: Arch, Debian, Ubuntu, Fedora, CentOS, Alpine
- Windows (in development)
- Qubes OS (specialized support)
- FreeBSD (partial)

## Quick Start Commands

### Initial Provisioning

```bash
# Standard installation
bash <(curl -sSL https://install.doctor/start)

# With custom fork
START_REPO=my-gh-user/my-fork-name bash <(curl -sSL https://install.doctor/start)

# With GitLab or custom git provider
START_REPO=git@gitlab.com:user/repo.git bash <(curl -sSL https://install.doctor/start)
```

### Development Workflow

```bash
# Initialize/start the project (installs dependencies, runs repairs)
task start

# Build the project
task build
npm run build

# Run linters
task lint
npm run lint

# Auto-fix code issues
task fix
npm run fix

# Run tests
task test
npm run test

# Commit changes (opens interactive commit dialog)
task commit
npm run commit

# Update project with upstream changes
task update
npm run update

# Preload system with common dependencies (requires reboot after)
task preload

# View all available tasks
task --list
task --menu
npm run help
```

### Resetting Chezmoi

If the provision process encounters errors or cached changes need clearing:

```bash
# macOS/Linux
rm -rf ~/.config/chezmoi && rm -rf ~/.cache/chezmoi

# Then re-run provisioning
bash <(curl -sSL https://install.doctor/start)
```

### Testing

```bash
# Test on specific Linux distro using Docker
task shell -- ubuntu-21.04

# VM testing (uses Vagrant)
bash scripts/test-linux.sh
bash scripts/test-macos.sh
```

## Architecture

### Provisioning Flow

Chezmoi orchestrates provisioning through numbered scripts in `home/.chezmoiscripts/`:

1. **run_before_01-prepare.sh** - Ensures system dependencies, sets up logging
2. **run_before_02-homebrew.sh** - Installs Homebrew (if not present)
3. **run_before_03-decrypt-age-key.sh** - Decrypts secrets using age encryption
4. **run_before_04-requirements.sh** - Installs essential tools (Task, ZX, etc.)
5. **run_before_05-system.sh** - System-level configurations
6. **run_after_01-pre-install.sh** - Pre-installation hooks
7. **run_after_10-install.sh** - **Main software installation** (calls `installx`)
8. **run_after_15-chezmoi-system.sh** - System file synchronization
9. **run_after_20-post-install.sh** - Post-installation tasks
10. **run_after_24-cleanup.sh** - Cleanup and finalization

### Software Installation System

**Central Configuration:** `software.yml` (13,087 lines)

Defines all software packages with metadata:
```yaml
softwarePackages:
  packagename:
    _name: "Display Name"
    _desc: "Detailed description"
    _short: "Short description"
    _github: "https://github.com/org/repo"
    _bin: "binary-name"
    apt: package-name-apt
    brew: package-name-brew
    cask: package-name-cask
    flatpak: com.example.AppName
    npm: package-name-npm
    # ... other package managers
    _post: |
      # Post-installation script
    _groups:
      - group1
      - group2
```

**Installation Priority (varies by OS):**

- **Linux (apt):** flatpak → snap → whalebrew → apt → brew → go → cargo → npm → pipx → pip → gem → appimage → script → ansible → binary
- **macOS:** whalebrew → cask → brew → go → cargo → npm → pipx → pip → gem → pkg-darwin → script → ansible → binary
- **Windows:** choco → scoop → winget → go → cargo → npm → pipx → gem → script → ansible → binary

**Custom Installer:** `scripts/software.mjs`
- ZX-based asynchronous installer
- Processes software.yml definitions
- Respects OS-specific package preferences
- Runs post-installation hooks
- Manages groups and permissions

**Helper Commands:**
```bash
# Called by run_after_10-install.sh
installx --all --lazy           # Install all software for current group
process-software-groups         # Process group permissions
process-software-post-scripts   # Run post-install scripts
process-software-services       # Start enabled services
```

### Chezmoi Configuration

**Main Config:** `home/.chezmoi.yaml.tmpl`
- Go template that detects system type (desktop/laptop/server/ephemeral)
- Configures encryption (age + GPG)
- Sets user/host data from environment variables
- Enables toolchains (CLI-Extras, Docker, Go, Kubernetes, Web-Development)
- Detects work environments, headless mode, desktop sessions

**Important Environment Variables:**
- `SOFTWARE_GROUP` - Controls which software set to install (default: "Standard", auto-adds "-Desktop" if GUI detected)
- `WORK_ENVIRONMENT` - Enables restricted/work mode
- `WITHOUT_TOOLCHAINS` - Disable all toolchains
- `WITHOUT_<TOOLCHAIN>` - Disable specific toolchain (e.g., `WITHOUT_DOCKER`)
- `WITH_<TOOLCHAIN>` - Force enable specific toolchain

**Other Key Chezmoi Files:**
- `.chezmoiignore` - Conditional file inclusion based on OS/environment
- `.chezmoiexternal.toml.tmpl` - External file management
- `.chezmoitemplates/` - Reusable template snippets
- `.chezmoiscripts/qubes/` - Qubes-specific provisioning

### Task System

**Main Taskfile:** `Taskfile.yml`
- Includes 103 modular taskfiles from `.config/taskfiles/`
- Categories: ansible, ci, cloud, docker, git, install, lint, npm, publish, security, etc.

**Key Task Patterns:**
```bash
task <namespace>:<command>              # Run specific task
task install:software:<package>         # Install specific package
task lint:all                          # Run all linters
task fix:all                           # Run all auto-fixers
task docker:build                      # Build Docker images
task git:commit                        # Git workflow
```

### Application Configurations

**Location:** `home/dot_config/`

120+ application configurations including:
- VSCode (Code/)
- Terminal emulators (alacritty, kitty, wezterm)
- Shell (bash, zsh, fish)
- Development tools (git, vim, tmux)
- Cloud tools (docker, kubernetes, terraform)
- System utilities (bat, fd, ripgrep, etc.)

Files use Chezmoi naming conventions:
- `dot_config` → `~/.config`
- `private_dot_ssh` → `~/.ssh`
- `executable_script` → executable script
- `.tmpl` suffix → processed as Go template

### System Files

**Location:** `system/`

System-level configurations applied to `/`:
- `/etc/profile` modifications
- Service definitions
- System-wide settings

Applied via: `sudo rsync -artuE --chown=root: ... "${XDG_CONFIG_HOME:-$HOME/.config}/system/" /`

## Development Guidelines

### Project Structure

```
install.doctor/
├── .config/
│   ├── taskfiles/          # 103 modular Task definitions
│   ├── scripts/            # Build and automation scripts
│   ├── docs/               # Documentation templates
│   └── husky/              # Git hooks
├── .github/workflows/      # CI/CD (test-linux, test-macos)
├── docs/                   # User documentation
├── home/                   # Chezmoi source (dotfiles)
│   ├── .chezmoiscripts/   # Provisioning scripts
│   ├── .chezmoitemplates/ # Reusable templates
│   ├── dot_config/        # ~/.config applications (120+)
│   ├── dot_local/         # ~/.local binaries and data
│   └── private_*/         # Encrypted/private files
├── scripts/               # Standalone provisioning scripts
│   ├── software.mjs       # Software installer (ZX)
│   └── provision.sh       # Main provisioning script
├── software.yml           # 13,087 lines of software definitions
├── Taskfile.yml           # Main task definitions
├── package.json           # Node.js configuration
└── start.sh               # Entry point script
```

### Modifying Software Definitions

When adding/modifying software in `software.yml`:

1. **Define package across installers:**
   ```yaml
   mypackage:
     _name: "My Package"
     _desc: "Full description..."
     _short: "Brief description"
     _github: "https://github.com/org/repo"
     _bin: "binary-name"
     _preload: true  # Include in 'task preload'
     brew: package-name
     apt: package-name
     flatpak: com.example.Package
     # ... other package managers
   ```

2. **Add to software groups** (if needed):
   ```yaml
   mypackage:
     _groups:
       - Standard         # Included in all installations
       - Standard-Desktop # Only for GUI environments
   ```

3. **Add post-installation script** (if needed):
   ```yaml
   mypackage:
     _post: |
       #!/bin/bash
       # Post-install configuration
   ```

4. **Test the change:**
   ```bash
   # Sort software.yml (recommended)
   npm run sort:software

   # Test installation
   chezmoi apply --verbose
   ```

### Modifying Taskfiles

When adding new tasks:

1. **Choose appropriate taskfile** in `.config/taskfiles/<category>/`
2. **Follow existing patterns:**
   ```yaml
   tasks:
     mytask:
       desc: Short description
       summary: |
         # Detailed Description
         More information about what this task does
       deps:
         - dependency:task
       cmds:
         - command to run
       status:
         - test -f /path/to/check  # Skip if condition met
   ```

3. **Use logging:**
   ```yaml
   log:
     error: Error message
     start: Starting message
     success: Success message
   ```

### Working with Chezmoi Scripts

**Script Naming Convention:**
- `run_before_##-name.sh.tmpl` - Runs before chezmoi applies files
- `run_after_##-name.sh.tmpl` - Runs after chezmoi applies files
- `run_onchange_*.sh.tmpl` - Runs only when script content changes
- `run_once_*.sh.tmpl` - Runs only once ever

**Template Features:**
```bash
# Access chezmoi data
{{ .chezmoi.os }}                    # Operating system
{{ .chezmoi.osRelease.id }}         # Distribution ID
{{ .host.hostname }}                 # Hostname
{{ .user.email }}                    # User email

# Include templates
{{ includeTemplate "universal/logg" }}
{{ includeTemplate "universal/profile" }}

# Conditionals
{{ if eq .chezmoi.os "darwin" }}
# macOS-specific code
{{ end }}
```

**Logging in scripts:**
```bash
# Include logging helper
{{ includeTemplate "universal/logg" }}

# Use logging
logg info 'Information message'
logg success 'Success message'
logg warn 'Warning message'
logg error 'Error message'
gum log -sl info 'Using gum for logging'
```

### Git Workflow

**Committing Changes:**
```bash
# Preferred method (interactive, enforces standards)
task commit

# Alternative
npm run commit

# Quick commit (bypasses hooks - use sparingly)
task commit:quick

# Manual commit (not recommended, bypasses pre-commit checks)
git commit -m "message" --no-verify
```

**Commit Message Format:**
Follows conventional commits:
- `feat:` New feature
- `fix:` Bug fix
- `docs:` Documentation changes
- `style:` Code style changes
- `refactor:` Code refactoring
- `test:` Test changes
- `chore:` Maintenance tasks

**Pre-commit Hooks:**
Automatically runs on `git commit`:
- Prettier formatting
- ESLint (JavaScript/TypeScript)
- ShellCheck (shell scripts)
- YAML linting
- Image compression
- Spell checking

### Testing Locally

**Docker-based testing:**
```bash
# Interactive OS selection
task shell

# Specific OS
task shell -- archlinux
task shell -- ubuntu-21.04
task shell -- fedora-34
task shell -- debian-10
```

**VM testing:**
```bash
# Uses Vagrantfile for multi-distro testing
vagrant up debian
vagrant up fedora
vagrant up ubuntu
```

**CI/CD:**
- GitHub Actions: `.github/workflows/test-linux.yml`, `test-macos.yml`
- GitLab CI: `.gitlab-ci.yml`
- Tests across 6+ Linux distros and macOS

### Code Style

**JavaScript/TypeScript:**
- ESLint config: `eslint-config-strict-mode`
- Prettier config: `prettier-config-sexy-mode`
- Strict TypeScript mode enabled

**Shell Scripts:**
- Use ShellCheck
- Include file headers (see existing scripts)
- Use logging helpers (`logg`, `gum`)

**YAML:**
- 2-space indentation
- Run `npm run sort:software` for software.yml

**Editorconfig:**
- 2-space indent
- UTF-8 encoding
- LF line endings
- Trim trailing whitespace

## Common Development Patterns

### Adding a New Application Configuration

1. **Create dotfile in home/:**
   ```bash
   # Example: adding ~/.config/myapp/config.yml
   mkdir -p home/dot_config/myapp
   echo "config: value" > home/dot_config/myapp/config.yml.tmpl
   ```

2. **Use templating if needed:**
   ```yaml
   # config.yml.tmpl
   email: {{ .user.email }}
   name: {{ .user.name }}
   {{ if eq .chezmoi.os "darwin" }}
   # macOS-specific config
   {{ end }}
   ```

3. **Test with chezmoi:**
   ```bash
   chezmoi apply --dry-run --verbose
   chezmoi apply
   ```

### Adding System Dependencies

1. **Add to software.yml:**
   ```yaml
   mytool:
     _preload: true  # Include in common dependencies
     brew: mytool
     apt: mytool
     dnf: mytool
     pacman: mytool
   ```

2. **Or add to requirements template:**
   Edit `home/.chezmoitemplates/<distro>` (e.g., `ubuntu`, `darwin`)

### Debugging Provisioning Issues

```bash
# Enable verbose logging
export DEBUG=1

# Dry run
chezmoi apply --dry-run --verbose

# See what would change
chezmoi diff

# Check chezmoi data
chezmoi data

# Re-run specific script
chezmoi apply --verbose --include scripts/run_after_10-install.sh.tmpl

# Clear cache and re-run
rm -rf ~/.cache/chezmoi
chezmoi apply --force
```

### Security Considerations

- **Never commit secrets** - Use age encryption or environment variables
- **Firejail sandboxing** - Preferred for Linux applications
- **Flatpak preference** - More secure than traditional packages on Linux
- **GPG/SSH keys** - Managed through private_dot_* directories with encryption
- **Age encryption** - Recipient: `age1necy24c4lzxheey4p2m8v4q000n442wyv47qc640ulyxx9l8dpesdqv7ey`

## Important Files

- **software.yml** - All software package definitions (13,087 lines)
- **Taskfile.yml** - Main task runner entry point
- **package.json** - NPM scripts and dependencies
- **start.sh** - Bootstrap script (ensures Task is installed)
- **home/.chezmoi.yaml.tmpl** - Chezmoi configuration
- **home/.chezmoiignore** - Conditional file inclusion rules
- **scripts/software.mjs** - Custom software installer (ZX-based)

## Environment Detection

The system automatically detects:
- **OS Type:** macOS, Linux (distro-specific), Windows
- **Chassis Type:** laptop, desktop, server, ephemeral (container/VM)
- **Session Type:** desktop (GUI) vs headless
- **Work Environment:** Managed Mac detection, WORK_ENVIRONMENT variable
- **CPU Info:** Cores and threads for parallel operations
- **Qubes OS:** Special provisioning for Qubes

## Toolchains

Available toolchains (can be enabled/disabled):
- **CLI-Extras** - Enhanced CLI tools (bat, fd, ripgrep, etc.)
- **Docker** - Container development tools
- **Go** - Go development environment
- **Kubernetes** - K8s tools (kubectl, helm, k9s, etc.)
- **Web-Development** - Node.js, browsers, web tools

Control via environment variables:
```bash
# Disable all toolchains
WITHOUT_TOOLCHAINS=true

# Disable specific toolchain
WITHOUT_DOCKER=true

# Force enable specific toolchain
WITH_KUBERNETES=true
```

## Publishing

```bash
# Semantic release (automated versioning)
task publish
npm run release

# Force a release
task publish:force -- 'PATCH UPDATE'
task publish:force -- 'MINOR UPDATE'
task publish:force -- 'MAJOR UPDATE'
```

## Additional Resources

- **Documentation:** `docs/` directory
- **Contributing Guide:** `docs/CONTRIBUTING.md`
- **Ecosystem:** `docs/ECOSYSTEM.md`
- **Code of Conduct:** `docs/CODE_OF_CONDUCT.md`
- **Main Website:** https://install.doctor
- **GitHub:** https://github.com/megabyte-labs/install.doctor
- **GitLab:** https://gitlab.com/megabyte-labs/install.doctor
