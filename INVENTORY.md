# Install.Doctor Complete Inventory

This is a comprehensive list of everything this repository installs, configures, and does to your system.

## Overview
- **Total Software Packages**: 1,180 packages defined in software.yml
- **Application Configurations**: 120+ applications configured in ~/.config
- **Provisioning Scripts**: 15 main scripts that set up your system
- **Task Operations**: 103 modular taskfiles for various automation
- **Toolchains**: CLI-Extras, Docker, Go, Kubernetes, Web-Development

---

## PROVISIONING OPERATIONS

### What Happens During Provisioning

1. **run_before_01-prepare.sh** - Ensures system dependencies, sets up logging
2. **run_before_02-homebrew.sh** - Installs Homebrew package manager (macOS/Linux)
3. **run_before_03-decrypt-age-key.sh** - Decrypts secrets using age encryption
4. **run_before_04-requirements.sh** - Installs Task, ZX, and essential tools
5. **run_before_05-system.sh** - Applies system-level configurations
6. **run_after_01-pre-install.sh** - Pre-installation hooks and preparations
7. **run_after_10-install.sh** - **MAIN SOFTWARE INSTALLATION** (installs all packages)
8. **run_after_15-chezmoi-system.sh** - Syncs system files to /
9. **run_after_20-post-install.sh** - Post-installation configuration tasks
10. **run_after_24-cleanup.sh** - Cleanup and finalization

### Qubes OS Specific (if detected)
- Updates dom0
- Installs Qubes templates
- Configures sys-usb and sys-gui

---

## SOFTWARE PACKAGES BY CATEGORY

### AI & LLM Tools (20+)
- ai-shell - AI shell enhancement
- aiac - AI Infrastructure as Code
- aicommits - AI-powered commit messages
- aider - AI pair programming
- aifiles - AI file analysis
- crush - AI terminal (Charm)
- gemini-cli - Google Gemini CLI
- opencode - AI terminal companion
- chatgpt - ChatGPT desktop
- chatgpt-nofwl - ChatGPT without firewall
- gpt-engineer - AI code generation
- amazon-q - Amazon's AI assistant
- msty - AI chat interface
- anythingllm - Local LLM platform
- limitless - AI meeting assistant
- pieces - AI code snippets
- pieces-cli - Pieces CLI
- pieces-os - Pieces backend
- ollama - Local LLM runtime
- search-gpt - AI-powered search
- shell-gpt - GPT in your shell

### Web Browsers (8)
- arc - Arc browser
- brave-browser - Privacy-focused browser
- google-chrome - Google Chrome
- chromium - Open-source Chrome
- firefox - Mozilla Firefox
- librewolf - Privacy-hardened Firefox
- microsoft-edge - Microsoft Edge
- vivaldi - Customizable browser

### IDEs & Code Editors (15+)
- android-studio - Android development IDE
- codeedit - macOS native code editor
- coder - Cloud development environment
- cursor - AI-powered IDE
- helix - Post-modern text editor
- intellij-idea-ce - IntelliJ Community Edition
- lapce - Lightning-fast editor
- macvim - macOS Vim with GUI
- neovim - Hyperextensible Vim
- vim - Classic text editor
- visual-studio - Microsoft Visual Studio
- vscode - Visual Studio Code
- vscodium - VSCode without telemetry

### Terminal Emulators & Shells
- alacritty - GPU-accelerated terminal
- hyper - Electron-based terminal
- iterm2 - macOS terminal replacement
- kitty - Fast, feature-rich terminal
- tabby - Cross-platform terminal
- warp-terminal - AI-powered terminal
- bash - Bourne Again SHell
- fish - Friendly Interactive SHell
- nushell - Modern shell with data structures
- zsh - Z Shell

### Version Control & Git Tools (30+)
- gh - GitHub CLI
- ghcup - Haskell toolchain manager (but used for Git in some contexts)
- ghorg - Clone entire GitHub orgs
- git - Distributed version control
- git-branchless - Branchless workflow tools
- git-bug - Distributed bug tracker
- git-extras - Extra Git utilities
- git-filter-repo - Git history rewriting
- git-jump - Jump to Git conflicts
- git-lfs - Git Large File Storage
- git-notify - Git notifications
- git-open - Open repo in browser
- git-secret - Store secrets in Git
- git-stats - Git statistics
- git-subrepo - Git subrepo management
- git-town - Git workflow tool
- gitdock - Git Docker integration
- github-desktop - GitHub Desktop app
- gitify - GitHub notifications
- gitkraken - Git GUI client
- gitlab-runner - GitLab CI runner
- gitlabform - GitLab configuration
- gitleaks - Scan for secrets
- gitmoji-cli - Commit with emojis
- gitomatic - Automatic Git operations
- gitql - Query Git repos with SQL
- gitui - Git terminal UI
- glab - GitLab CLI
- gitfs - Git filesystem

### Container & Virtualization Tools (40+)
- docker - Container runtime
- docker-desktop - Docker Desktop
- docker-credential-helper - Docker credential management
- docker-langserver - Docker language server
- docker-plugins - Docker plugins
- docker-pushrm - Push Docker README
- docker-slim - Minify Docker images
- dockfmt - Dockerfile formatter
- dockle - Container security linter
- dockly - Docker terminal UI
- podman - Daemonless containers
- rancher-desktop - Kubernetes & container management
- orbstack - Fast Docker & Linux on macOS
- multipass - Ubuntu VMs
- vagrant - Development environment automation
- vagrant-manager - Vagrant GUI
- virtualbox - x86 virtualization
- vmware - VMware products
- parallels - Parallels Desktop (macOS)
- utm - Virtual machines for macOS
- qemu - Generic machine emulator
- kvm - Kernel Virtual Machine
- lxc - Linux containers
- lxd - LXD container manager
- lxd-ui - LXD web interface
- distrobox - Use any Linux distro
- kubernetes-cli (kubectl) - Kubernetes control
- k9s - Kubernetes TUI
- helm - Kubernetes package manager
- helm-docs - Helm documentation
- helmfile - Helm releases
- minikube - Local Kubernetes
- kind - Kubernetes in Docker
- tilt - Local Kubernetes dev
- skaffold - Kubernetes workflow
- lens - Kubernetes IDE
- kubenav - Kubernetes navigator
- kubectx - Switch Kubernetes contexts
- kustomize - Kubernetes configuration
- kn - Knative CLI
- fleetctl - Fleet management

### Cloud Provider CLIs & Tools (20+)
- awscli - AWS Command Line Interface
- aws-shell - Interactive AWS CLI
- azure-cli - Azure CLI
- azure-functions - Azure Functions tools
- gcloud - Google Cloud SDK
- doctl - DigitalOcean CLI
- flyctl - Fly.io CLI
- heroku-cli - Heroku CLI
- cf - Cloud Foundry CLI
- cloudflare-cli - Cloudflare CLI
- cloudflared - Cloudflare Tunnel
- ibmcloud - IBM Cloud CLI
- oci-cli - Oracle Cloud CLI
- openstack - OpenStack CLI
- terraform - Infrastructure as Code
- pulumi - Modern IaC

### Infrastructure as Code (15+)
- terraform - HashiCorp Terraform
- terraform-ls - Terraform language server
- tfenv - Terraform version manager
- tflint - Terraform linter
- tfsec - Terraform security scanner
- pulumi - Modern infrastructure as code
- ansible - IT automation
- ansible-lint - Ansible linter
- packer - Image automation
- vagrant - Development environments
- cloudformation - AWS CloudFormation
- consul-cli - Consul CLI
- consul-template - Consul templating
- nomad - Workload orchestrator
- vault - Secrets management

### Programming Languages & Runtimes (25+)
- go - Go programming language
- rust - Rust programming language
- python - Python 3
- python2 - Python 2 (legacy)
- node - Node.js JavaScript runtime
- deno - Secure TypeScript runtime
- bun - Fast all-in-one JavaScript runtime
- ruby - Ruby programming language
- openjdk - OpenJDK Java
- java - Java runtime
- dotnet - .NET runtime
- php - PHP language
- lua - Lua programming language
- perl - Perl language
- r - R statistical language
- julia - Julia language
- erlang - Erlang language
- elixir - Elixir language
- haskell - Haskell language
- scala - Scala language
- kotlin - Kotlin language
- swift - Swift language
- dart - Dart language
- crystal - Crystal language
- zig - Zig language

### Package Managers & Version Managers (20+)
- homebrew - macOS/Linux package manager
- apt - Debian package manager
- dnf - Fedora package manager
- pacman - Arch package manager
- npm - Node package manager
- yarn - Fast npm alternative
- pnpm - Efficient npm alternative
- pip - Python package installer
- pipx - Python app installer
- cargo - Rust package manager
- gem - Ruby package manager
- composer - PHP package manager
- poetry - Python dependency manager
- bundler - Ruby dependency manager
- mise - Polyglot version manager
- asdf - Multiple runtime version manager
- volta - JavaScript tool manager
- proto - Multi-language version manager
- pkgx - Package manager without installation

### Database Tools & Clients (20+)
- postgresql - PostgreSQL database
- mysql - MySQL database
- mariadb - MariaDB database
- mongodb - MongoDB database
- mongodb-atlas - MongoDB Atlas CLI
- mongodb-compass - MongoDB GUI
- redis - Redis in-memory database
- redis-insight - Redis GUI
- redis-desktop-manager - Redis manager
- beekeeper-studio - SQL editor
- dbeaver - Universal database tool
- pgcli - PostgreSQL CLI with autocomplete
- mycli - MySQL CLI with autocomplete
- litecli - SQLite CLI
- sqlite - SQLite database
- usql - Universal SQL CLI
- octosql - Query tool for files
- sqlectron - SQL client

### API Development & Testing (15+)
- postman - API platform
- httpie - HTTP CLI client
- curl - Transfer data with URLs
- curlie - curl + httpie
- hurl - HTTP testing tool
- http-toolkit - HTTP debugging
- http-prompt - Interactive HTTP client
- insomnia - API client
- newman - Postman CLI
- graphql-playground - GraphQL IDE
- altair - GraphQL client (deprecated)
- mockoon - API mocking

### File Transfer & Sync (15+)
- rsync - Fast incremental transfer
- rclone - Cloud storage sync
- syncthing - Continuous file sync
- nextcloud - Self-hosted cloud
- seafile-client - Seafile sync
- croc - Secure file transfer
- magic-wormhole - Secure send
- ffsend - Firefox Send CLI
- portal - File transfer
- warp-transfer - File sharing

### Security & Privacy Tools (50+)
- bitwarden - Password manager
- bitwarden-cli - Bitwarden CLI
- 1password - 1Password (if you have it)
- 1password-cli - 1Password CLI
- pass - Unix password manager
- gopass - Team password manager
- keepassxc - KeePass client
- keybase - Crypto for everyone
- yubikey-agent - SSH with YubiKey
- yubikey-authenticator - 2FA with YubiKey
- yubikey-manager - YubiKey management
- yubikey-manager-qt - YubiKey GUI
- onlykey - OnlyKey management
- onlykey-agent - OnlyKey SSH
- onlykey-cli - OnlyKey CLI
- gpg - GNU Privacy Guard
- age - Modern encryption
- vault - HashiCorp Vault
- sops - Secrets operations
- git-secret - Store secrets in Git
- ssh-vault - SSH key encryption
- clamav - Antivirus
- fail2ban - Intrusion prevention
- rkhunter - Rootkit hunter
- wazuh - Security monitoring
- osquery - OS analytics
- nmap - Network mapper
- masscan - Mass IP scanner
- wireshark - Network analyzer
- ettercap - Network sniffer
- john - Password cracker
- hashcat - Password recovery
- metasploit - Penetration testing
- zaproxy - Security scanner
- burpsuite - Web security
- snitch - Network monitor (macOS)
- lulu - Firewall (macOS)
- santa - Binary authorization (macOS)
- opensnitch - Application firewall (Linux)
- portmaster - Privacy firewall
- privaxy - Privacy proxy
- privoxy - Privacy proxy
- tor - Anonymity network
- tor-browser - Tor browser
- mullvad-vpn - Mullvad VPN
- protonvpn - ProtonVPN
- wireguard - Fast VPN
- openvpn - VPN protocol
- tailscale - Mesh VPN
- zerotier - Network virtualization
- tunnelblick - OpenVPN (macOS)

### Networking Tools (30+)
- netcat - Network swiss army knife
- socat - Socket connector
- ngrok - Expose local servers
- localtunnel - Tunnel local servers
- ssh - Secure shell
- openssh-server - SSH server
- sshfs - SSH filesystem
- sshpass - Non-interactive SSH
- sshuttle - VPN over SSH
- mosh - Mobile shell
- assh - Advanced SSH config
- tailscale - Mesh VPN
- wireguard-tools - WireGuard utilities
- openvpn - VPN client
- cloudflared - Cloudflare tunnels
- frpc - Fast reverse proxy client
- frps - Fast reverse proxy server
- nginx - Web server
- caddy - Web server with HTTPS
- haproxy - Load balancer
- traefik - Reverse proxy
- dnsmasq - DNS/DHCP server
- bind - DNS server
- pihole - Network ad blocker
- adguard - Network ad blocker
- unbound - DNS resolver
- dog - DNS client
- dig - DNS lookup
- whois - Domain lookup
- tcpdump - Packet analyzer
- iftop - Network bandwidth
- nethogs - Network per-process
- bmon - Bandwidth monitor
- vnstat - Network statistics

### Monitoring & System Tools (40+)
- htop - Interactive process viewer
- bottom (btm) - System monitor
- btop - Resource monitor
- gtop - System monitor
- glances - System monitoring
- netdata - Real-time monitoring
- prometheus - Monitoring system
- grafana - Analytics platform
- osquery - OS analytics
- sysdig - System troubleshooting
- ctop - Container monitoring
- dive - Docker image explorer
- lazydocker - Docker TUI
- bandwhich - Network utilization
- gping - Ping with graph
- procs - Process viewer
- pstree - Process tree
- lsof - List open files
- iotop - I/O monitoring
- dstat - System statistics
- vmstat - Virtual memory stats
- iostat - I/O statistics
- mpstat - CPU statistics
- sar - System activity
- nmon - Performance monitor
- sysstat - System statistics
- stress - CPU stress test
- stress-ng - Stress testing
- sysbench - System benchmark
- hyperfine - Command benchmarking
- wrk - HTTP benchmark
- hey - HTTP load generator
- ab - Apache benchmark
- siege - HTTP load tester
- ddosify - Load testing
- k6 - Load testing
- locust - Load testing
- artillery - Load testing

### File Management & Search (25+)
- fd - Find alternative
- fzf - Fuzzy finder
- ripgrep (rg) - Fast search
- ripgrep-all (rga) - Search all file types
- ag - Silver searcher
- ack - Code search
- grep - Pattern search
- pcregrep - Perl regex grep
- sift - Fast grep alternative
- find/findutils - Find files
- locate - Find files fast
- mlocate - Modern locate
- broot - Directory navigation
- nnn - Terminal file manager
- ranger - File manager
- lf - Terminal file manager
- yazi - Terminal file manager
- mc - Midnight Commander
- vifm - Vi-like file manager
- fff - Fast file manager
- fselect - SQL for files
- walk - Terminal file manager
- clifm - Command line file manager

### Text Processing & Manipulation (25+)
- bat - Cat with syntax highlighting
- jq - JSON processor
- yq - YAML/XML/TOML processor
- htmlq - HTML processor
- xq - XML/HTML processor
- oq - Structured data processor
- miller - CSV/JSON/tabular processor
- csvkit - CSV toolkit
- xsv - CSV toolkit in Rust
- sed - Stream editor
- gnu-sed - GNU sed
- awk - Pattern processing
- gawk - GNU awk
- grep - Pattern matching
- pcre2grep - PCRE regex grep
- dasel - JSON/YAML/TOML/XML query
- fx - JSON viewer
- gron - Make JSON greppable
- jless - JSON viewer
- textql - SQL on CSV/JSON
- q - SQL on CSV/TSV
- hq - HTML processor
- pup - HTML processor
- xmlstarlet - XML toolkit

### File Compression & Archives (15+)
- p7zip - 7-Zip file archiver
- zip - ZIP archiver
- unzip - ZIP extractor
- unrar - RAR extractor
- rar - RAR archiver (proprietary)
- tar - Tape archiver
- gnu-tar - GNU tar
- gzip - GNU zip
- pigz - Parallel gzip
- bzip2 - Block-sorting compressor
- xz - LZMA compression
- zstd - Zstandard compression
- lz4 - Fast compression
- unar - Universal unarchiver
- the-unarchiver - Archive utility (macOS)
- cabextract - Extract CAB files
- unace - Extract ACE archives

### Image & Video Tools (20+)
- ffmpeg - Multimedia framework
- imagemagick - Image manipulation
- graphicsmagick - Image processing
- gimp - Image editor
- inkscape - Vector graphics
- krita - Digital painting
- blender - 3D creation suite
- darktable - Photo workflow
- rawtherapee - RAW converter
- handbrake - Video transcoder
- obs-studio - Streaming/recording
- kdenlive - Video editor
- shotcut - Video editor
- openshot - Video editor
- pitivi - Video editor
- mpv - Media player
- vlc - Media player
- iina - Media player (macOS)
- mplayer - Media player
- exiftool - Metadata editor
- jpegoptim - JPEG optimizer
- pngquant - PNG compressor
- optipng - PNG optimizer
- svgo - SVG optimizer
- tinypng - Image compression

### Communication Apps (15+)
- slack - Team communication
- slack-term - Slack in terminal
- discord - Voice & chat
- telegram - Messaging app
- signal - Private messenger
- element - Matrix client
- zoom - Video conferencing
- microsoft-teams - Team collaboration
- skype - Video calls
- jitsi-meet - Video conferencing
- wire - Secure messenger
- session - Private messenger
- threema - Secure messenger

### Productivity Apps (25+)
- notion - All-in-one workspace
- obsidian - Knowledge base
- logseq - Knowledge graph
- standard-notes - Encrypted notes
- joplin - Note taking
- typora - Markdown editor
- mark-text - Markdown editor
- zettlr - Markdown editor
- notable - Note taking
- simplenote - Notes app
- nb - Notes CLI
- dendron - Note taking
- foam - Note taking (VS Code)
- todoist - Task manager
- ticktick - Task manager
- things - Task manager (macOS)
- omnifocus - Task manager (macOS)
- taskwarrior - Task management CLI
- timewarrior - Time tracking
- watson - Time tracking
- toggl - Time tracking
- clockify - Time tracking
- rescuetime - Time tracking
- activitywatch - Time tracking
- arbtt - Time tracking

### Window Managers & Desktop (20+)
- aerospace - Tiling WM (macOS)
- amethyst - Tiling WM (macOS, deprecated)
- yabai - Tiling WM (macOS)
- rectangle - Window manager (macOS)
- spectacle - Window manager (macOS)
- magnet - Window manager (macOS)
- hammerspoon - Automation (macOS)
- raycast - Launcher (macOS)
- alfred - Launcher (macOS)
- launchbar - Launcher (macOS)
- i3 - Tiling WM (Linux)
- sway - Tiling WM (Wayland)
- bspwm - Tiling WM
- xmonad - Tiling WM
- awesome - Tiling WM
- dwm - Tiling WM
- rofi - Application launcher
- dmenu - Menu system
- polybar - Status bar
- skhd - Hotkey daemon (macOS)
- hiddenbar - Menu bar manager (macOS)
- dozer - Menu bar manager (macOS)

### Music & Audio (15+)
- spotify - Music streaming
- spotify-tui - Spotify terminal
- spotifyd - Spotify daemon
- ncspot - Spotify ncurses
- cmus - Music player
- moc - Music on console
- mpd - Music player daemon
- ncmpcpp - MPD client
- mpc - MPD client
- audacity - Audio editor
- ardour - Digital audio workstation
- lmms - Music production
- musescore - Music notation
- lilypond - Music engraving
- sox - Sound processing
- lollypop - Music player
- nuclear - Music player
- youtube-music - YouTube Music

### Download Managers (12+)
- aria2 - Download utility
- ariang - aria2 web UI
- axel - Download accelerator
- wget - File retriever
- wget2 - GNU Wget2
- curl - Transfer tool
- youtube-dl - Video downloader
- yt-dlp - youtube-dl fork
- spotdl - Spotify downloader
- you-get - Media downloader
- gallery-dl - Image gallery downloader
- gdown - Google Drive downloader

### Documentation & Markdown (15+)
- pandoc - Universal document converter
- mdbook - Markdown book generator
- hugo - Static site generator
- jekyll - Static site generator
- hexo - Static site generator
- mkdocs - Documentation generator
- sphinx - Documentation generator
- doctoc - Table of contents generator
- markdownlint-cli - Markdown linter
- markdown-toc - TOC generator
- marp - Markdown presentations
- slidev - Presentation slides
- reveal-md - Markdown presentations
- mdslides - Terminal presentations
- slides - Terminal presentations (CLI)

### Shell Enhancement & Utilities (40+)
- zsh-autosuggestions - Command suggestions
- zsh-syntax-highlighting - Syntax highlighting
- zsh-completions - Extra completions
- oh-my-zsh - Zsh framework
- oh-my-posh - Prompt theme engine
- starship - Cross-shell prompt
- powerlevel10k - Zsh theme
- pure - Zsh theme
- zoxide - Smart cd
- autojump - Directory jumper
- z - Directory jumper
- fasd - Fast directory access
- fzf - Fuzzy finder
- peco - Interactive filter
- percol - Interactive filter
- pick - Interactive filter
- direnv - Directory environments
- autoenv - Directory environments
- dotenv - Environment variables
- envy - Environment manager
- envchain - Secure environment variables
- tmux - Terminal multiplexer
- tmuxinator - Tmux session manager
- tmuxp - Tmux session manager
- screen - Terminal multiplexer
- zellij - Terminal workspace
- byobu - Terminal multiplexer
- wezterm - GPU-accelerated terminal
- thefuck - Command corrector
- fuck - Alias for thefuck
- navi - Interactive cheatsheet
- cheat - Cheatsheet viewer
- tldr - Simplified man pages
- tealdeer - tldr client
- bro - Just the examples
- howdoi - Instant answers
- kmdr - CLI helper

### Backup & Recovery Tools (15+)
- restic - Backup program
- rustic - Restic in Rust
- autorestic - Restic wrapper
- borg - Deduplicating backup
- borgmatic - Borg wrapper
- duplicity - Encrypted backup
- duplicacy - Cloud backup
- rclone - Cloud sync
- syncthing - File synchronization
- bup - Backup system
- zbackup - Deduplicating backup
- timeshift - System snapshots (Linux)
- snapper - Snapshot management
- deja-dup - Backup tool (GNOME)
- arq - Backup (macOS/Windows)
- sanoid - Snapshot management

### Development Build Tools (25+)
- make - Build automation
- gmake - GNU make
- cmake - Cross-platform build
- ninja - Small build system
- meson - Build system
- scons - Build tool
- bazel - Build system
- bazelisk - Bazel launcher
- buck - Build system
- pants - Build system
- gradle - Build automation (JVM)
- maven - Build automation (Java)
- ant - Build tool (Java)
- sbt - Build tool (Scala)
- leiningen - Build tool (Clojure)
- rake - Build tool (Ruby)
- invoke - Task execution (Python)
- task (go-task) - Task runner
- just - Command runner
- make - Task automation
- mage - Make in Go
- doit - Build tool (Python)
- fabric - Task execution (Python)
- gulp - JavaScript task runner
- grunt - JavaScript task runner
- webpack - Module bundler

### Testing & Quality Tools (25+)
- jest - JavaScript testing
- mocha - JavaScript testing
- cypress - E2E testing
- playwright - Browser automation
- puppeteer - Browser automation
- selenium - Browser automation
- selenium-webdriver - WebDriver
- appium - Mobile testing
- detox - Mobile testing
- xcuitest - iOS testing
- espresso - Android testing
- pytest - Python testing
- unittest - Python testing
- nose - Python testing
- tox - Testing tool (Python)
- robot-framework - Test automation
- cucumber - BDD framework
- behave - BDD (Python)
- specflow - BDD (.NET)
- rspec - Testing (Ruby)
- minitest - Testing (Ruby)
- junit - Testing (Java)
- testng - Testing (Java)
- molecule - Ansible testing
- kitchen - Infrastructure testing
- inspec - Compliance testing
- serverspec - Infrastructure testing
- goss - Server validation
- testinfra - Infrastructure testing

### Formatters & Linters (30+)
- prettier - Code formatter
- prettierd - Prettier daemon
- eslint - JavaScript linter
- eslintd - ESLint daemon
- stylelint - CSS linter
- standard - JavaScript style
- semistandard - JavaScript style
- ts-standard - TypeScript style
- black - Python formatter
- autopep8 - Python formatter
- yapf - Python formatter
- isort - Python import sorter
- flake8 - Python linter
- pylint - Python linter
- mypy - Python type checker
- ruff - Fast Python linter
- rubocop - Ruby linter
- standardrb - Ruby style
- shfmt - Shell script formatter
- shellcheck - Shell script linter
- hadolint - Dockerfile linter
- yamllint - YAML linter
- sqlfluff - SQL linter
- sqlformat - SQL formatter
- terraform fmt - Terraform formatter
- tflint - Terraform linter
- gofmt - Go formatter
- goimports - Go import formatter
- golangci-lint - Go linter
- rustfmt - Rust formatter
- clippy - Rust linter

### PDF & Document Tools (15+)
- libreoffice - Office suite
- onlyoffice - Office suite
- wps-office - Office suite
- calibre - E-book manager
- okular - Document viewer (KDE)
- evince - Document viewer (GNOME)
- zathura - Document viewer
- mupdf - PDF viewer
- xpdf - PDF viewer
- pdf-tools - PDF utilities
- pdftk - PDF toolkit
- qpdf - PDF transformation
- poppler - PDF library
- ghostscript - PostScript/PDF
- pandoc - Document converter
- wkhtmltopdf - HTML to PDF
- weasyprint - HTML/CSS to PDF
- prince - HTML to PDF

### Email Clients (10+)
- thunderbird - Email client
- mailspring - Email client
- mailbird - Email client (Windows)
- evolution - Email client (GNOME)
- geary - Email client (GNOME)
- kmail - Email client (KDE)
- claws-mail - Email client
- mutt - Email client (CLI)
- neomutt - Email client (CLI)
- himalaya - Email client (CLI)
- aerc - Email client (CLI)

### Password Managers (10+)
- bitwarden - Password manager
- bitwarden-cli - Bitwarden CLI
- 1password - 1Password
- 1password-cli - 1Password CLI
- pass - Unix password manager
- gopass - Team password manager
- keepassxc - KeePass client
- keepass - KeePass
- enpass - Password manager
- dashlane - Password manager
- lastpass - Password manager (deprecated)

### VPN Clients (12+)
- mullvad-vpn - Mullvad VPN
- protonvpn - ProtonVPN
- protonvpn-cli - ProtonVPN CLI
- nordvpn - NordVPN
- expressvpn - ExpressVPN
- openvpn - OpenVPN
- wireguard-client - WireGuard
- tailscale - Mesh VPN
- zerotier - Network virtualization
- softether - VPN protocol
- tunnelblick - OpenVPN GUI (macOS)
- viscosity - VPN client

### Screenshot & Recording (12+)
- flameshot - Screenshot tool
- spectacle - Screenshot (KDE)
- gnome-screenshot - Screenshot (GNOME)
- scrot - Screenshot (CLI)
- maim - Screenshot (CLI)
- ksnip - Screenshot annotation
- peek - GIF recorder
- screenkey - Key visualizer
- asciinema - Terminal recorder
- vhs - Terminal GIF generator
- terminalizer - Terminal recorder
- kooha - Screen recorder (GNOME)
- simplescreenrecorder - Screen recorder
- recordmydesktop - Screen recorder
- kazam - Screen recorder
- vokoscreen - Screen recorder

### Remote Desktop (15+)
- chrome-remote-desktop - Chrome remote
- teamviewer - Remote support
- anydesk - Remote desktop
- nomachine - Remote desktop
- vnc - VNC protocol
- tigervnc - TigerVNC
- tightvnc - TightVNC
- realvnc - RealVNC
- kasmvnc - Web VNC
- x11vnc - X11 VNC
- rustdesk - Open source remote desktop
- remmina - Remote desktop client (Linux)
- microsoft-remote-desktop - RDP client
- freerdp - RDP client
- rdesktop - RDP client
- xrdp - RDP server

### 3D Printing & Electronics (10+)
- prusaslicer - 3D slicer
- ultimaker-cura - 3D slicer
- slic3r - 3D slicer
- openscad - 3D CAD
- freecad - Parametric 3D
- blender - 3D creation
- kicad - Electronics CAD
- arduino-ide - Arduino IDE
- platformio - IoT development
- fritzing - Electronics prototyping
- circuitpython - Python for hardware

### Note Taking & PKM (15+)
- obsidian - Knowledge base
- logseq - Knowledge graph
- notion - All-in-one workspace
- anytype - Decentralized workspace
- affine - Next-gen knowledge base
- joplin - Note taking
- standard-notes - Encrypted notes
- simplenote - Simple notes
- notable - Note taking
- trilium - Hierarchical notes
- tiddlywiki - Wiki
- zettlr - Markdown editor
- nb - Notes CLI
- dendron - Note taking
- foam - PKM in VS Code
- Athens Research - Knowledge graph

---

## APPLICATION CONFIGURATIONS (120+)

The following applications have custom configurations in `~/.config`:

### Complete List of Configured Applications
- aerospace - Tiling window manager (macOS)
- aihawk - AI tool
- alacritty - Terminal emulator
- apprise - Notification tool
- aqua - Declarative CLI version manager
- autorestic - Backup wrapper
- autostart - Desktop autostart
- bashtop - Resource monitor
- bat - Cat clone with syntax highlighting
- bin - Custom scripts
- blesh - Bash line editor
- brew - Homebrew configurations
- caddy - Web server
- chrome - Chrome settings
- chromium-flags.conf - Chromium flags
- coc - Conquer of Completion (Vim)
- cockpit - Server administration
- cod - Code completion daemon
- code2prompt - Code to prompt converter
- Code/ - VS Code settings
- conda - Package manager
- crontab - Cron jobs
- cups - Print system
- dagu - Workflow engine
- dconf - GNOME configuration
- desk - Desktop manager
- desktop - Desktop entries
- direnv - Directory environments
- distrobox - Container manager
- docker - Docker settings
- dot_curlrc - Curl configuration
- espanso - Text expander
- fd - Find alternative
- firefox - Firefox settings
- firefoxprofileswitcher - Profile switcher
- firejail - Sandboxing
- firewall - Firewall configuration
- fish - Fish shell
- fontconfig - Font configuration
- gcsf - Google Cloud Storage FUSE
- gdrive3 - Google Drive v3
- ghorg - GitHub org cloner
- git - Git configuration
- gitomatic - Automatic Git operations
- glow - Markdown viewer
- Google Assistant/ - Google Assistant
- gphotos-sync - Google Photos sync
- gtk-1.0 - GTK 1.0 settings
- gtk-2.0 - GTK 2.0 settings
- gtk-3.0 - GTK 3.0 settings
- gtkrc - GTK configuration
- hammerspoon - Automation (macOS)
- helm - Kubernetes package manager
- heroku - Heroku CLI
- himalaya - Email CLI
- hishtory - Shell history
- hoard - File organizer
- jit - Development tool
- k9s - Kubernetes TUI
- kcminputrc - KDE input
- kdeglobals - KDE global settings
- kitty - Terminal emulator
- konsolerc - Konsole settings
- ksplashrc - KDE splash
- ktimezonedrc - KDE timezone
- kwinrc - KWin window manager
- Kvantum/ - Qt theme engine
- lexicon - DNS automation
- libvirt - Virtualization
- lsd - LSDeluxe (ls alternative)
- mackup - Application backup
- macos - macOS settings
- mimeapps.list - MIME associations
- mise - Development environment manager
- navi - Interactive cheatsheet
- neofetch - System info
- netdata - Monitoring
- ngrok - Tunnel service
- npm - Node package manager
- ntfy - Notification service
- nushell - Modern shell
- oh-my-posh - Prompt theme
- oil - Shell
- pg - PostgreSQL
- pgcli - PostgreSQL CLI
- pip - Python package installer
- plasma - KDE Plasma
- plasma-localerc - Plasma locale
- plasmarc - Plasma settings
- portal - File transfer
- postfix - Mail server
- powershell - PowerShell
- privoxy - Privacy proxy
- putty - SSH client (Windows)
- qubes - Qubes OS
- quokka - Python playground
- raycast - Launcher (macOS)
- rclone - Cloud sync
- readline - Input library
- ripgrep - Search tool
- rkhunter - Rootkit hunter
- rofi-user - Rofi configuration
- santa - Binary authorization
- sheldon - Shell plugin manager
- shell - Shell configuration
- shell_gpt - GPT in shell
- skhd - Hotkey daemon (macOS)
- slack-term - Slack terminal
- system - System configurations
- tabby - Terminal
- task - Task runner
- terminator - Terminal emulator
- tmux - Terminal multiplexer
- tor - Tor network
- update - Update scripts
- vagrant - Virtual machines
- vim - Vim editor
- VirtualBox/ - VirtualBox settings
- vnc - VNC settings
- vpn - VPN configurations
- wakatime - Time tracking
- warp - Terminal emulator
- wego - Weather CLI
- wget - Download tool
- xfce4 - XFCE desktop
- xonsh - Shell
- xsettingsd - X settings
- yarn - Package manager
- youtube-dl - Video downloader
- zap - Package manager

---

## SYSTEM-LEVEL CHANGES

### Files Modified/Created in /
- `/etc/profile` - Shell environment modifications
- `/etc/profile.d/` - Profile scripts
- `/etc/environment` - System environment variables
- `/etc/hosts` - Host file modifications
- `/etc/ssh/sshd_config` - SSH server configuration (port 8169)
- `/etc/samba/smb.conf` - Samba configuration
- `/etc/nginx/` - Nginx configuration
- `/etc/caddy/` - Caddy configuration
- `/etc/systemd/` - Systemd units
- `/etc/udev/rules.d/` - udev rules
- `/etc/sysctl.d/` - Kernel parameters
- `/etc/modules-load.d/` - Kernel modules
- `/usr/local/bin/` - Custom scripts
- `/usr/local/etc/rc.d/cloudflared` - Cloudflare tunnel (FreeBSD)

### Services That May Be Installed & Started
- docker - Container runtime
- podman - Container runtime
- nginx - Web server
- caddy - Web server
- netdata - Monitoring
- cockpit - System administration
- privoxy - Privacy proxy
- cloudflared - Cloudflare tunnel
- sshd - SSH server (custom port 8169)
- endlessh - SSH tarpit (port 22)
- postgresql - Database
- mysql/mariadb - Database
- mongodb - Database
- redis - In-memory database
- samba - File sharing
- smbd - Samba daemon
- nmbd - NetBIOS name server
- fail2ban - Intrusion prevention
- clamav - Antivirus
- clamav-daemon - ClamAV daemon
- clamav-freshclam - ClamAV updater
- rkhunter - Rootkit hunter
- wazuh - Security monitoring
- firewalld - Firewall (Linux)
- ufw - Firewall (Ubuntu)
- libvirt - Virtualization
- lxd - Container manager
- snapd - Snap daemon
- flatpak - Flatpak system
- cups - Print system
- avahi-daemon - Zeroconf/mDNS
- docker-compose services - Various containerized services

### Shell Modifications
- `.bashrc` - Bash configuration
- `.bash_profile` - Bash login
- `.zshrc` - Zsh configuration
- `.zprofile` - Zsh login
- `.config/fish/config.fish` - Fish configuration
- Shell completions for 100+ tools
- Custom aliases and functions
- Oh-My-Zsh or Oh-My-Posh installation
- Starship prompt
- Powerlevel10k theme
- zsh-autosuggestions
- zsh-syntax-highlighting
- fzf key bindings
- fzf tab completion
- zoxide integration
- atuin shell history
- direnv hooks
- asdf/mise environment

### macOS Specific Changes
- Homebrew installation (`/opt/homebrew` or `/usr/local`)
- macOS defaults write operations (system preferences)
- Launch Agents (`~/Library/LaunchAgents/`)
- Launch Daemons (`/Library/LaunchDaemons/`)
- Accessibility permissions
- Privacy permissions (TCC.db)
- Firewall rules
- Network settings
- DNS settings (Cloudflare 1.1.1.1)
- Finder preferences
- Dock preferences
- Trackpad/mouse settings
- Keyboard settings
- Screen saver settings
- Energy saver settings
- Application-specific settings via `defaults write`

### Linux Specific Changes
- APT sources (`/etc/apt/sources.list.d/`)
- RPM repositories (`/etc/yum.repos.d/`)
- Flatpak remotes
- Snap connections
- Desktop environment configuration (GNOME/KDE/XFCE)
- Display manager configuration (GDM/SDDM/LightDM)
- Firewall rules (firewalld/ufw/iptables)
- SELinux policies (if enabled)
- AppArmor profiles (if enabled)
- Systemd user services
- Systemd system services
- Kernel parameters (`/etc/sysctl.d/`)
- Kernel modules (`/etc/modules-load.d/`)
- udev rules (`/etc/udev/rules.d/`)
- NetworkManager configuration
- DNS configuration (systemd-resolved or `/etc/resolv.conf`)
- Grub configuration (if modified)
- Plymouth theme (boot splash)

---

## TASK OPERATIONS (103 Taskfiles)

### Categories of Available Tasks

1. **Ansible** (`task ansible:*`)
   - playbook execution
   - testing with Molecule
   - linting
   - galaxy operations

2. **App** (`task app:*`)
   - Application management
   - VirtualBox operations

3. **Boilerplate** (`task boilerplate:*`)
   - Project scaffolding
   - Template population
   - Interactive prompts

4. **CI/CD** (`task ci:*`)
   - GitHub Actions
   - GitLab CI
   - Automated testing

5. **Docker** (`task docker:*`)
   - Build images
   - Push images
   - Container management
   - Multi-arch builds

6. **Fix** (`task fix:*`)
   - Auto-fix code issues
   - Format code
   - Apply linter suggestions

7. **Git** (`task git:*`)
   - Commit with Commitizen
   - GitHub operations
   - GitLab operations
   - Git Bug tracking
   - Gitomatic automation
   - Branch management

8. **Go** (`task go:*`)
   - Build Go projects
   - Test Go code
   - GoReleaser

9. **Image** (`task image:*`)
   - Docker image operations
   - Image optimization

10. **Install** (`task install:*`)
    - Software installation
    - Dependency management
    - Package-specific installs

11. **Lint** (`task lint:*`)
    - Markdown linting
    - Prose linting
    - ESLint
    - ESPrint
    - CodeClimate
    - All linters

12. **Log** (`task log:*`)
    - Logging utilities
    - Log viewing

13. **Nest** (`task nest:*`)
    - NestJS operations

14. **NPM** (`task npm:*`)
    - Package publishing
    - Version management
    - Dependency updates

15. **Publish** (`task publish:*`)
    - Homebrew formula
    - Snap package
    - iOS app
    - Android app
    - Firefox extension
    - Chrome extension
    - Opera extension
    - App store releases

16. **Release** (`task release:*`)
    - Semantic versioning
    - Changelog generation
    - Tag creation
    - Release publishing

17. **Security** (`task security:*`)
    - SSH key management
    - GPG key management
    - YubiKey operations
    - Disk encryption
    - Password management

18. **UI** (`task ui:*`)
    - User interface tasks
    - Frontend operations

19. **Vagrant** (`task vagrant:*`)
    - Vagrant box management
    - Qubes OS operations
    - VM provisioning

20. **Web** (`task web:*`)
    - NX monorepo operations
    - Web development tasks

### Common Task Commands
```bash
task start              # Initialize project, install dependencies
task build              # Build the project
task test               # Run all tests
task lint               # Run all linters
task fix                # Auto-fix all code issues
task commit             # Interactive commit with Commitizen
task publish            # Semantic release
task update             # Update all dependencies
task preload            # Preload common software
task clean              # Clean build artifacts
task reset              # Reset project to clean state
```

---

## TOOLCHAINS

These are optional feature sets that can be enabled/disabled via environment variables:

### 1. CLI-Extras
Enhanced command-line tools including:
- bat, fd, ripgrep
- fzf, zoxide
- exa/eza, lsd
- procs, dust, duf
- bottom, bandwhich
- hyperfine, tokei

### 2. Docker
Container development ecosystem:
- Docker Engine
- Docker Compose
- Docker Desktop
- Portainer
- Lazydocker
- Dive
- Hadolint
- Container scanning tools

### 3. Go
Go programming environment:
- Go compiler
- Go tools (gofmt, goimports, etc.)
- Go linters (golangci-lint)
- Delve debugger
- Air live reload
- GoReleaser

### 4. Kubernetes
Kubernetes tools and utilities:
- kubectl
- helm
- k9s
- kubectx/kubens
- kustomize
- stern
- skaffold
- tilt
- lens
- minikube/kind

### 5. Web-Development
Node.js and web development:
- Node.js
- npm/yarn/pnpm
- TypeScript
- ESLint/Prettier
- Webpack/Vite
- React/Vue/Angular CLIs
- Browser dev tools
- Lighthouse

### Control via Environment Variables
```bash
# Disable all toolchains
WITHOUT_TOOLCHAINS=true

# Disable specific toolchain
WITHOUT_DOCKER=true
WITHOUT_KUBERNETES=true

# Force enable specific toolchain (even if others disabled)
WITH_GO=true
WITH_WEB_DEVELOPMENT=true
```

---

## SOFTWARE GROUPS

Software is organized into groups that determine what gets installed:

### Standard
Core utilities and tools for any system. This is the base group.

### Standard-Desktop
Adds desktop applications and GUI tools when a desktop session is detected.
Automatically appended to "Standard" if GUI is detected.

### Work/Restricted
Modified behavior for managed/work environments:
- Skips certain personal tools
- Applies stricter security
- Respects corporate policies

---

## DEPRECATED/OPTIONAL SOFTWARE

Some software is marked as deprecated or optional and won't be installed by default:

### Deprecated (Not Installed)
- adobe-creative-cloud - Creates distracting boot window
- alt-tab - Unnecessary on modern macOS
- altair - Deprecated in favor of Postman
- amethyst - Replaced by AeroSpace
- apt-cacher-ng - Use Sonatype Nexus instead
- astronvim - Replaced by NvChad
- arduino-ide - Outdated cask
- appium-desktop - Unneeded
- appium-inspector - Unneeded
- audacity - Unneeded
- betwixt - Deprecated
- And others marked with `_deprecated: true`

---

## BROWSER EXTENSIONS & PLUGINS

Browser configurations may include:
- Extension installation scripts
- Browser profile creation
- Developer tools setup
- Privacy-focused extensions
- Ad blockers
- Password manager extensions
- Dark mode extensions
- Tab managers

---

## FONTS INSTALLED

Multiple font families for programming and general use:
- **Nerd Fonts** - Patched fonts with icons
  - FiraCode Nerd Font
  - JetBrainsMono Nerd Font
  - Hack Nerd Font
  - Meslo Nerd Font
  - SourceCodePro Nerd Font
- **FiraCode** - Font with ligatures
- **JetBrains Mono** - JetBrains programming font
- **Hack** - Typeface for source code
- **Source Code Pro** - Adobe monospaced font
- **Meslo LG** - Customized Menlo
- **Cascadia Code** - Microsoft programming font
- **IBM Plex Mono** - IBM monospaced font
- **Victor Mono** - Programming font with cursive italics

---

## FLATPAK APPLICATIONS (Linux Desktop)

The `_misc-flatpaks` group includes 30+ applications:
- **bottles** - Windows app compatibility layer
- **cockpit-client** - Cockpit remote management
- **connections** - Remote desktop client
- **dconf-editor** - GNOME configuration editor
- **deja-dup** - Backup utility
- **dialect** - Translation app
- **drawing** - Drawing application
- **flatseal** - Flatpak permission manager
- **forklift** - File manager
- **gnome-calendar** - Calendar application
- **gnome-document-viewer** - PDF viewer
- **gnome-extension-manager** - GNOME extensions
- **gnome-eyedropper** - Color picker
- **gnome-file-roller** - Archive manager
- **gnome-image-viewer** - Image viewer
- **gnome-network-displays** - Screen sharing
- **gnome-passwords-keys** - Keyring manager
- **gnome-photos** - Photo manager
- **gnome-sound-recorder** - Audio recorder
- **gnome-video-player** - Video player (Totem)
- **gnome-weather** - Weather application
- **junction** - Application chooser
- **kooha** - Screen recorder
- **newsflash** - RSS reader
- **pinapp** - Pin websites as apps
- **vup** - Video uploader
- **warp-transfer** - File transfer
- **web-font-generator** - Font generator
- **what-ip** - IP address viewer
- **live-captions** - Live captioning
- **libre-menu-editor** - Menu editor
- **iso-image-writer** - ISO writer
- **trayscale** - Tailscale system tray

---

## NAUTILUS EXTENSIONS (GNOME File Manager)

If using GNOME/Nautilus, these extensions enhance functionality:
- **nautilus-brasero** - CD/DVD burning integration
- **nautilus-gtkhash** - Checksum calculator
- **nautilus-gsconnect** - KDE Connect for GNOME
- **nautilus-image-converter** - Resize/rotate images
- **nautilus-python** - Python extensions support
- **nautilus-seahorse** - Encryption integration
- **nautilus-search-tool** - Enhanced search
- **nautilus-share** - Easy folder sharing
- **nautilus-wipe** - Secure file deletion

---

## KDE PLASMA INTEGRATION

If using KDE Plasma desktop:
- **kde-plasma-desktop** - Plasma desktop environment
- **kdeplasma-addons** - Extra widgets
- **kvantum** - Theme engine
- Plasma configuration in `~/.config/plasma*`
- KDE global settings
- Konsole terminal configuration
- KWin window manager settings
- KDE shortcuts and hotkeys

---

## GNOME INTEGRATION

If using GNOME desktop:
- **gnome** - GNOME desktop meta-package
- **gnome-tweaks** - GNOME customization
- **gnome-extension-manager** - Manage extensions
- **chrome-gnome-shell** - Browser integration
- GNOME Shell extensions
- GTK theme configuration
- dconf settings
- GNOME keyboard shortcuts

---

## ENCRYPTION & SECRETS MANAGEMENT

### Age Encryption
- age key generation
- Encrypted chezmoi files
- Age recipient configuration

### GPG
- GPG key import/generation
- Git signing configuration
- Email encryption
- Password store encryption

### SSH
- SSH key generation
- SSH agent configuration
- SSH config management
- Multiple key support

### Secrets Tools
- chezmoi encryption
- vault (HashiCorp)
- sops (Mozilla)
- git-secret
- git-crypt
- blackbox
- keybase
- bitwarden-cli
- pass/gopass
- 1password-cli

---

## BACKUP & SYNC STRATEGIES

### Dotfiles
- **chezmoi** - Primary dotfile manager
- **mackup** - Application settings backup
- **yadm** - Alternative dotfile manager

### Cloud Storage
- **rclone** - Universal cloud sync (70+ cloud providers)
- **gdrive** - Google Drive CLI
- **google-drive** - Google Drive client
- **nextcloud** - Self-hosted cloud
- **seafile-client** - Seafile sync

### Backup Tools
- **restic** - Fast, secure backups
- **rustic** - Restic in Rust
- **autorestic** - Automated restic
- **borg** - Deduplicating backups
- **duplicity** - Encrypted backups
- **timeshift** - System snapshots (Linux)
- **time machine** - macOS backups
- **deja-dup** - Simple backups (GNOME)

### File Sync
- **syncthing** - Continuous sync
- **unison** - Bi-directional sync
- **lsyncd** - Live sync daemon

### Specialized
- **gphotos-sync** - Google Photos backup
- **sanoid** - ZFS snapshot management
- **zfs-auto-snapshot** - Automatic ZFS snapshots

---

## IMPORTANT NOTES

### 1. Conditional Installation
**Not all software is installed by default.** Installation depends on:

- **Operating System**
  - macOS (darwin)
  - Linux (Arch, Debian, Ubuntu, Fedora, CentOS, Alpine)
  - Windows
  - FreeBSD
  - Qubes OS

- **Software Group**
  - Standard (base tools)
  - Standard-Desktop (+ GUI applications)
  - Custom groups via `SOFTWARE_GROUP` env var

- **Toolchains** (enabled/disabled)
  - CLI-Extras
  - Docker
  - Go
  - Kubernetes
  - Web-Development

- **Hardware Detection**
  - Laptop vs Desktop vs Server
  - CPU cores/threads (for parallel operations)
  - Display server (X11/Wayland)

- **Environment**
  - Work vs Personal (`WORK_ENVIRONMENT`)
  - Headless vs Desktop session
  - Container vs Bare metal
  - Ephemeral (Codespaces, VS Code Remote, Docker)

### 2. Package Manager Preferences

Installation priority varies by OS:

**macOS (darwin):**
```
whalebrew > cask > brew > go > cargo > npm > pipx > pip > gem > pkg-darwin > script > ansible > binary
```

**Linux (apt-based):**
```
flatpak > snap > whalebrew > apt > brew > go > cargo > npm > pipx > pip > gem > appimage > script > ansible > binary
```

**Linux (Arch):**
```
flatpak > snap > whalebrew > pacman > brew > yay > go > cargo > npm > pipx > pip > gem > appimage > script > ansible > binary
```

**Windows:**
```
choco > scoop > winget > go > cargo > npm > pipx > gem > script > ansible > binary
```

### 3. Deprecated & Optional Items
- Items marked `_deprecated: true` are NOT installed by default
- Items with `_when:` conditions only install if condition is met
- Some packages have alternatives (e.g., amethyst → aerospace)

### 4. Post-Installation Scripts
Many packages have `_post:` scripts that run after installation to:
- Configure the application
- Set up services
- Apply permissions
- Start daemons
- Import settings
- Create symbolic links
- Register with the system

### 5. Service Management
Services may be configured to:
- **Start on boot** (systemd, launchd, Windows services)
- **Run as user** (systemd user services)
- **Run as root** (system services)
- **Auto-restart** on failure
- **Log to** system journal or specific log files

### 6. Preload Feature
The `task preload` command installs commonly-used software marked with `_preload: true`:
- Core utilities
- Essential development tools
- Performance utilities
- System monitoring
This allows faster provisioning on subsequent runs.

---

## APPENDIX: COMPLETE ALPHABETICAL SOFTWARE LIST

All 1,180 software packages defined in software.yml:

_envchaindeps      | act                 | aerospace           | airtable
_kde               | adobe-creative-cloud| ai-shell            | airtame
_misc-flatpaks     | ack                 | aiac                | alda
_nautilus-extensions | aider             | aicommits           | allure
aifiles            | alt-tab             | altair              | amazon-q
amethyst           | android-commandlinetools | android-platform-tools | android-studio
angular-cli        | ansible             | ansible-lint        | ansibleconnect
ansibler           | ansifilter          | anythingllm         | apctest
apktool            | appflowy            | appium              | appium-desktop
appium-inspector   | appnest-readme      | apprise             | apt
apt-cacher-ng      | aqua                | arc                 | arduino-ide
argc               | argo-cli            | aria2               | ariang
arping             | asciinema           | asdf                | assh
astronvim          | atuin               | audacity            | auto-install
autodoc            | autokey             | automake            | autorestic
avifquicklook      | aws-shell           | awscli              | awxcli
axel               | azure-cli           | azure-functions     | backup
balenaetcher       | bandwhich           | bane                | barrier
bash-completion    | bashly              | basictex            | bat
bat-extras         | bats                | bazelisk            | beekeeper-studio
beets              | betwixt             | bfg                 | bin
binwalk            | bismuth             | bitly               | bitwarden
bitwarden-cli      | bivac               | blackhole           | blender
block-goose        | block-goose-cli     | blocky              | blueutil
boilr              | boringtun           | bottles             | bottom
brasero            | brave-browser       | brew-gem            | brew-pkg
broot              | browser-sync        | browserosaurus      | budibase-cli
buildkite-agent    | bun                 | bundler             | bzip2
cabextract         | caddy               | cakebrew            | caniuse
capacitor          | captain             | carapace            | carbon-now
carthage           | catfs               | catlight            | ccat
ceph               | cerebro             | certbot             | cf-terraforming
cfssl              | charm               | chatgpt             | chatgpt-nofwl
cheat              | chef-workstation    | chezmoi             | chrome-cli
chrome-gnome-shell | chrome-remote-desktop-host | chromium   | clair
clamav             | clangd              | clipboard           | cloc
clocker            | clop                | cloudflare-cli      | cloudflared
cmake              | cmctl               | cockpit             | cockpit-client
cocoapods          | cod                 | code2prompt         | codeclimate
codeedit           | coder               | cointop             | commitizen
commitlint         | composer            | confd               | connections
consul-cli         | consul-template     | container-structure-test | cookiecutter
copilot-for-xcode  | cordova             | coreutils           | croc
crunch             | crush               | cryptomator         | csvkit
ctop               | cumulus             | cups                | curator
curl               | curlie              | cursor              | cutter
cyberduck          | cyberduck-cli       | d2vm                | dagger
dagu               | darwin              | dasel               | dat
dconf-editor       | debsecan            | deja-dup            | delta
delve              | deno                | desed               | desk
deta               | devbox              | devpod              | devspace
devtoys            | devtoys-windows     | dframe              | dialect
dialog             | difftastic          | direnv              | discord
distrobox          | dive                | dnf                 | dnsmasq
docker             | docker-credential-helper | docker-desktop | docker-images
docker-langserver  | docker-plugins      | docker-pushrm       | docker-slim
dockfmt            | dockle              | dockly              | dockutil
doctl              | dog                 | doitlive            | dokany
dotenv-linter      | dotenv-vault        | dotnet              | dprint
drawing            | drawio              | drone-cli           | dua
duf                | dust                | duti                | eartrumpet
easyengine         | editly              | eget                | ejs
electron           | element             | emma                | emoj
emplace            | empty-trash         | endlessh            | enola
envchain           | envconsul           | envio               | eslint
eslint-dashboard   | eslint-interactive  | eslintd             | espanso
esprint            | etcd                | ettercap            | eul
exa                | exiftool            | expect              | eza
fabric             | fail2ban            | fastify             | fastlane
fcp                | fd                  | fdupes              | feathers
ferdium            | ffmpeg              | ffsend              | fiddler
fig                | figlet              | figma               | filebrowser
filezilla          | findutils           | firebase            | firefox
firefox-profile    | firewall-applet     | firewall-config     | firewalld
fiscript           | fission             | fixkey              | fkill
flake8             | flameshot           | flatseal            | fleetctl
flipper            | flow-launcher       | flutter             | fly
flyctl             | fm                  | follow              | footloose
forever            | forklift            | fpm                 | fpmdeps
fq                 | freebsd             | fritzing            | frpc
frps               | fselect             | fuego               | fury
fuse               | fx                  | fzf                 | gawk
gcc                | gcloud              | gcsf                | gdbgui
gdown              | gdrive              | gemini-cli          | generator-ngx-rocket
genymotion         | gfi                 | gh                  | ghcup
ghorg              | gifsicle            | gimp                | gist
git                | git-branchless      | git-bug             | git-extras
git-filter-repo    | git-jump            | git-lfs             | git-notify
git-open           | git-secret          | git-stats           | git-subrepo
git-town           | gitdock             | gitfs               | github-desktop
gitify             | gitkraken           | gitlab-runner       | gitlabform
gitleaks           | gitmoji-cli         | gitomatic           | gitql
gitui              | gixy                | glab                | glances
glen               | glow                | glusterfs           | gnome
gnome-boxes        | gnome-calendar      | gnome-document-viewer | gnome-extension-manager
gnome-eyedropper   | gnome-file-roller   | gnome-image-viewer  | gnome-network-displays
gnome-passwords-keys | gnome-photos      | gnome-sound-recorder | gnome-text-editor
gnome-tweaks       | gnome-video-player  | gnome-weather       | gnu
gnu-indent         | gnu-sed             | gnu-tar             | gnutls
go                 | go-chromecast       | go-outline          | goaccess
gojq               | golangci-lint       | gomodifytags        | gomplate
goofys             | google-assistant    | google-chrome       | google-drive
google-web-designer | gopass             | gopkgs              | gopls
goreleaser         | gotests             | gphotos-sync        | gping
gpt-engineer       | gradle              | graphql-playground  | grep
grex               | gron                | grype               | gtop
guacamole          | gulp                | gum                 | gup
hadolint           | hammerspoon         | handbrake           | handlr
haproxy            | has                 | hbs-cli             | hclq
helix              | helm                | helm-docs           | helmfile
heroku-cli         | hexyl               | hey                 | hiddenbar
himalaya           | hishtory            | hoard               | holehe
homeassistant-cli  | hostctl             | howdoi              | hss
hstr               | htmlhint            | htmlq               | htop
http-prompt        | http-toolkit        | httpie              | httpstat
hub                | hugo                | hurl                | husky
hyper              | hyperfine           | hyperkit            | i3
ideviceinstaller   | iina                | imagemagick         | imageoptim
imageoptim-cli     | imagine             | imgur-uploader      | impl
infracost          | inkscape            | intellij-idea-ce    | invoice
iodine             | ionic               | ios-deploy          | ios-sim
ipfs               | ipfs-deploy         | ipfs-desktop        | ipmitool
iproute2mac        | iredis              | irssi               | is-up
iso-image-writer   | isort               | iterm2              | java
jc                 | jenv                | jest                | jiq
jitsi-meet         | jo                  | john                | jpegoptim
jq                 | jqp                 | json-server         | juicefs
juju               | junction            | just                | k9s
kap                | kasmvnc             | kcpassword          | kdash
kde-plasma-desktop | kdenlive            | kdeplasma-addons    | keybase
keycastr           | kitty               | kn                  | kodi
koodo-reader       | kooha               | korkut              | krew
krita              | ksnip               | kube-shell          | kubectx
kubekey            | kubenav             | kubernetes-cli      | kubernetes-kompose
kubeval            | kustomize           | kvantum             | kvm
langchain          | langflow            | langgraph-cli       | langgraph-studio
languagetool       | lapce               | lazygit             | ledger-live
lens               | lepton              | lexicon             | libguestfs-tools
libimobiledevice   | libre-menu-editor   | libreoffice         | librewolf
license            | lighthouse          | lightproxy          | limitless
linkerd2           | linkliar            | liquidjs            | litecli
live-captions      | local               | localtunnel         | logcli
logi-options-plus  | logi-tune           | logitech-presentation | lolcat
lollypop           | loop                | lpass               | lsd
lsyncd             | lua                 | lulu                | lux
lxc                | lxd                 | lxd-ui              | lxdc
m-cli              | maas                | mackup              | macprefs
macvim             | mage-ai             | magic-wormhole      | mailcatcher
mailspring         | mailsy              | majestic            | makeself
malwarebytes       | mambaforge          | manta               | mariadb
mark-text          | markdownlint-cli    | markmap             | marp
mas                | mask                | masscan             | masscode
mc                 | mcfly               | medis               | medusa
meetingbar         | meld                | meta                | meta-package-manager
metasploit         | micromamba          | microsoft-edge      | microsoft-git
microsoft-office   | microsoft-remote-desktop | microsoft-teams | microsoft-todo
miller             | minikube            | mise                | mitmproxy
mjml               | mjml-app            | mkcert              | mockoon
modern-flyouts     | mods                | mole                | molecule
monero             | monero-cli          | mongodb             | mongodb-atlas
mongodb-compass    | monitorcontrol      | mono                | moon
mosh               | motrix              | mpg123              | mpv
mqttx              | msty                | mudlet              | muffet
mullvad-vpn        | multi-gitter        | multipass           | mutagen
mycli              | mymonero            | nativefier          | nativescript
nautilus-brasero   | nautilus-gsconnect  | nautilus-gtkhash    | nautilus-image-converter
nautilus-python    | nautilus-seahorse   | nautilus-search-tool | nautilus-share
nautilus-wipe      | navi                | nb                  | ncc
ndb                | nebula              | nectar              | neofetch
neovide            | neovim              | neovim-node-host    | nest
netcat             | netdata             | networkmanager      | newman
newsflash          | nextcloud           | nginx               | nginx-unit
ngrok              | ngxtop              | ninja               | nitroshare
nmap               | nnn                 | node                | node-prune
nodemon            | nomad               | nomino              | normit
notion             | np                  | npkill              | npm-check
npm-check-updates  | ntfy                | ntl                 | nuclear
nugetpackageexplorer | nushell           | nve                 | nx
obs-studio         | obsidian            | obsidian-cli        | oclif
octosql            | oh-my-posh          | ollama              | onionshare
onlykey            | onlykey-agent       | onlykey-cli         | onlykey-cli-deps
opencode           | opencommit          | openinterminal      | openjdk
openshift-cli      | openssh-server      | openssl             | openssl-osx-ca
openvpn            | opn-cli             | oq                  | orbstack
osquery            | osx-sign            | ots                 | p7zip
package-size       | packer              | pacman              | page-fetch
pageres            | pake                | pandoc              | papertrail
parallels          | pass                | pastel              | patch-package
pay-respects       | pb                  | peco                | peek
percol             | pfsense-fauxapi     | pgcli               | php
php-extensions     | phpmon              | pick                | pidcat
pieces             | pieces-cli          | pieces-os           | pigz
pika               | pinapp              | pipedream-cli       | pipelight
pipx               | pkg                 | pkgx                | platformio
playwright         | please              | plex                | plex-htpc
plex-media-server  | plumber             | plymouth            | pm2
pnpm               | pnpm-lock-export    | pock                | podman
poetry             | polybar             | pony                | poppler
portal             | porter              | portmaster          | postfix
postgresql         | postman             | powerline           | powershell
pppc-utility       | pre-commit          | prefsniff           | prettier
prettierd          | pretzel             | prezi-video         | privaxy
privileges         | privoxy             | procs               | profilecreator
progress           | projen              | prompt-declaration-language | proto
protonmail-bridge  | protonmail-import-export | protonvpn      | protonvpn-cli
provisionql        | proxyman            | psi                 | psscriptanalyzer
psu                | pueue               | pulumi              | pup
pushpin            | pv                  | pwnat               | python
python2            | pywhat              | pywin32             | qbittorrent
qlcolorcode        | qlmarkdown          | qlplugins           | qlprettypatch
qlstephen          | qlvideo             | qpdf                | quark-engine
quasar             | quickemu            | quickgui            | quicklook-csv
quicklook-json     | quicklookapk        | quicktype           | ramda
rancher-cli        | rancher-desktop     | rar                 | raspberry-pi-imager
raycast            | rclone              | recoverpy           | recuva
redis              | redis-desktop-manager | redis-insight     | reek
remmina            | remote-desktop      | repo                | repomix
responsively       | restic              | resume              | ripgrep
ripgrep-all        | rivet               | rkhunter            | rm-improved
robotframework     | rofi                | rsync               | rsyslog
rtop               | rubocop             | ruby                | ruff
runitor            | runjs               | rust                | rustdesk
rustic             | rustscan            | rusty               | s-search
s5cmd              | sad                 | safe-rm             | sail
sake               | samba               | sanctum             | sanoid
santa              | sapling             | scap-security-guide | schema
scrcpy             | scrcpy-gui          | sd                  | sddm
sdkman-cli         | seafile-client      | search-gpt          | secretive
semantic-release   | sentry-cli          | serve               | serverless
sftpgo             | sftpgo-plugin-auth  | share               | sharewifi
sharex             | sharp               | shc                 | shdoc
sheldon            | shell-gpt           | shellcheck          | shfmt
shml               | shotcut             | shotwell            | shuttle
shx                | sidekick            | signal              | skaffold
skate              | skhd                | skm                 | skype
slack              | slack-term          | slides              | sloth
snapcraft          | snapd               | snitch              | social-analyzer
soduto             | soft-serve          | solargraph          | solidity
spacedrive         | sparkleshare        | speed-test          | speedtest-cli
sphinx             | spotdl              | sql-language-server | sqlectron
sqlite             | squid               | ssh-vault           | sshfs
sshpass            | sshs                | sshuttle            | ssl-proxy
stacer             | standard-notes      | starred             | statcode
staticcheck        | stats               | steam               | steampipe
stegcloak          | storybook           | sttr                | stubby
supervisor         | surge               | svgo                | swiftbar
swiftformat        | swifty              | swimat              | switchhosts
sync-ssh-keys      | syncpack            | syncthing           | synp
syntax-highlight   | sysbench            | sysdig              | sysget
sysz               | t                   | t-rec               | tabby
tailscale          | talksheet           | taplo               | tart
task               | taskwarrior         | teamviewer          | telegram
teleport           | teller              | temps               | terminal-notifier
terminalizer       | termius             | terraform           | terraform-ls
textql             | tfenv               | tflint              | tfsec
tgpt               | the-unarchiver      | thefuck             | thunderbird
tig                | tigervnc            | tilt                | timeshift
timewarrior        | tinypng             | tldr                | tmate
tmux               | tmuxinator          | tokei               | tomcat
toml-sort          | tor                 | tor-browser         | tradingview
trae               | translate           | trayscale           | tree
tree-sitter        | trellis             | trivy               | trufflehog
trunk              | ts2c                | tunnelblick         | turbo
typescript         | typescript-to-lua   | ubuntu              | ugm
ultra              | unace               | unar                | unbuffer
unikraft           | unison              | up                  | upscayl
upt                | upx                 | usql                | util-linux
utm                | vagrant             | vagrant-manager     | vagrant-vmware-utility
vale               | vault               | vdirsyncer          | vector
velero             | vermin              | vhs                 | vidmerger
vim                | virtualbox          | virtualenv          | visual-studio
vivaldi            | vlc                 | vmware              | volta
volum              | vscode              | vscodium            | vup
w3m                | wails               | wallpaper-cli       | warp
warp-terminal      | warp-transfer       | watchexec           | watchman
waypoint           | wazuh               | web-ext             | web-font-generator
webpquicklook      | websocat            | webtorrent          | wego
wetty              | wget                | whalebrew           | what-ip
whereami           | wifi-password       | windows             | windows-adk
windows-admin-center | windows-app       | windows-power-toys  | winrm-cli
winui-gallery      | wipe-modules        | wireguard-client    | wireguard-tools
wireshark          | wishlist            | wkhtmltopdf         | wordops
wordpresscom       | wordpressify        | wp-cli              | wpfui
wrangler           | wrk                 | wsl                 | x64dbg
xcode              | xcodeinstall        | xcodes              | xcodes-app
xcpretty           | xdotool             | xh                  | xhyve
xpanes             | xpra                | xrdp                | xsv
xurls              | xxh                 | xz                  | yamllint
yank               | yapf                | yarn                | yarnhook
yazi               | yj                  | you-get             | youtube-dl
youtube-music      | yq                  | yt-dlp              | yubikey-agent
yubikey-authenticator | yubikey-manager  | yubikey-manager-qt  | zap
zaproxy            | zenity              | zola                | zoom
zoxide             | zpaq                | zsh                 | zsh-completions
zstd               | zx                  | zypper              |

---

## HOW TO USE THIS INVENTORY

To request removal of software, you can:

### 1. Remove by Category
```
Remove all AI tools
Remove all gaming platforms
Remove communication apps
Remove all container tools except Docker
```

### 2. Remove Specific Packages
```
Remove: obsidian, notion, logseq, joplin
Remove: slack, discord, zoom, teams
Remove: gimp, inkscape, blender
```

### 3. Keep Only Specific Items
```
Keep only: vscode, git, docker, kubernetes-cli, terraform
Keep browsers: firefox, chrome only
Keep terminals: kitty, alacritty only
```

### 4. Remove Entire Toolchains
```
Remove Kubernetes toolchain
Remove Web-Development toolchain
Disable Docker toolchain
```

### 5. Remove by Platform/Type
```
Remove all macOS-specific tools
Remove all GNOME applications
Remove all Flatpak applications
Remove all database tools
```

### 6. Combination Approach
```
Keep:
- Core dev tools (git, vscode, vim)
- Docker and Kubernetes
- Python and Go

Remove:
- All AI/LLM tools
- All communication apps
- All music/video editors
- All gaming platforms
```

---

**Generated**: Mon Nov 18 16:35:42 UTC 2024
**Total Packages**: 1,180
**Total Configurations**: 120+
**Total Scripts**: 15
**Total Tasks**: 103
