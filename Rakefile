desc "Homebrew taps setup"
task :homebrew_taps do
  # Caskroom
  `brew tap caskroom/cask`
  # Neovim
  `brew tap neovim/homebrew-neovim`
  # Alternate Cask software versions
  `brew tap caskroom/versions`
end

desc "Homebrew package install & update"
task homebrew: %i(homebrew_update homebrew_upgrade)  do
  Rake::Task["homebrew_install_packages"].invoke
end

task :homebrew_install_packages do
  BREWS.each do |package|
    `brew install #{package}`
  end

  CASKS.each do |package|
    `brew cask install #{package}`
  end

  Rake::Task["homebrew_cleanup"].invoke
end

task :homebrew_cleanup do
  `brew cleanup`
end

task :homebrew_update do
  `brew update`
end

task :homebrew_upgrade do
  `brew upgrade`
end

########################################

BREWS = [
  # Ruby
  ## Tool for installing Ruby from source
  "ruby-build",
  ## Ruby version manager
  "chruby",
  ## Featherweight gemset-like provider
  "--HEAD https://raw.github.com/postmodern/gem_home/master/homebrew/gem_home.rb",

  # Cache
  ## Memory-based object store
  "memcached",

  # DB
  ## Small, embedded database
  "sqlite",
  ## Solid ORDBMS
  "postgresql",

  # Dev stuff
  ## Editor
  "neovim",
  ## The DVCS
  "git --with-brewed-openssl --with-brewed-svn",
  ## Terminal multiplexer. Split console windows and stuff
  "tmux",
  ## OS X specific trick to allow copy/pastes work from CLI
  "reattach-to-user-namespace --with-wrap-pbcopy-and-pbpaste",
  ## Fuzzy file content searcher, like grep only 1000x faster
  "the_silver_searcher",
  ## Tag creator. Keeps index of definitions
  "ctags",
  ## TLS toolkit
  "openssl",
  ## Compiler system
  "gcc",
  ## Dependecy library, parsing options in command lines
  "popt",
  ## Old school revision control system
  "svn",
  ## Alternate revision control system
  "hg",
  ## Solid web server & reverse proxy
  "nginx",
  ## Scripting programming language. Version 3 is sometimes needed as dependency
  "python3",
  ## GNU coreutils on a vacation in macOS. Contains, e.g. readlink(1) with sane `-f` option flag
  "coreutils",
  ## Git diff prettifier script
  "diff-so-fancy",

  # JS
  ## Compressor and linter
  "closure-compiler",
  ## Node version manager
  "nvm",

  # Misc
  ## wget(1) on steroids
  "aria2",
  ## Graphics toolkit
  "imagemagick",
  ## Periodical command execution
  "watch",
  ## .rpm extraction
  "rpm2cpio",
  ## Password generator
  "pwgen",
  ## Assorted pack of various small Unix utilities
  "moreutils",
  ## top(1) on steroids
  "htop-osx",
  ## Random git utilities
  "git-extras",
  ## Speed up directory traversal
  "z",
  ## Retrieval of files across various protocols
  "wget",
  ## CLI hex viewer
  "dhex",
  ## CLI disk usage viewer
  "ncdu",
  ## Adequate (and OSS) version of Cisco AnyConnect VPN software
  "openconnect",
  ## Taskwarrior, to-do tracker
  "task",
  ## Taskwarrior shell
  "tasksh",
  ## nc(1) on steroids
  "socat",
  ## Terminal based YouTube player and downloader
  "mps-youtube",
]

CASKS = [
  # Dev stuff
  ## LDAP workhorse
  "apache-directory-studio",
  ## Documentation HUD
  "dash",
  ## GUI frontend to PostgreSQL
  "pgadmin4",
  ## GUI frontend to SQLite
  "sqlitestudio",
  ## Virtual development environment management
  "vagrant",
  ## OS virtualization package
  "virtualbox",
  ## Packet analyzer
  "wireshark",

  # macOS
  ## IM client (using dev branch; v1.6)
  "adium-nightly16",
  ## Utility for tracking battery capacity changes over time
  "coconutbattery",
  ## Disk space analyzer/treemap viewer
  "disk-inventory-x",
  ## DNS encryption. Secure lookups against first-hop MITM's (e.g. public access points messing with/blocking some sites)
  "dnscrypt",
  ## Clipboard manager
  "flycut",
  ## Mac OS X build of Chromium
  "freesmug-chromium",
  ## Lossy compressor for PNG
  "imagealpha",
  ## Various image format optimizer/compressor
  "imageoptim",
  ## Tool for disabling idle/lid OS sleep
  "insomniax",
  ## Keyboard mapping customizer. macOS 10.12 compatible.
  "karabiner-elements",
  ## File archiver. Happily munges through all popular and obscure formats (e.g. RAR)
  "keka",
  ## Display of CPU temperature and fan speed in menubar
  "smcfancontrol",
  ## Menubar status insights (for OS X 10.11+)
  "yujitach-menumeters",
  ## X11 for Mac
  "xquartz",

  # Misc
  ## E-book library management
  "calibre",
  ## Free diagram builder [Visio]
  "dia",
  ## Automatic display color management
  "flux",
  ## Free 2D raster graphics editor [Photoshop]
  "gimp",
  ## Free vector graphics editor [Illustrator]
  "inkscape",
  ## Free office suite [Office]
  "libreoffice",
  ## Fast and easy 3D modelling
  "sketchup",
  ## IM client
  "skype",
  ## Desktop sharing/remote control
  "teamviewer",
  ## Media player, hadling anything thrown at it
  "vlc",
]
