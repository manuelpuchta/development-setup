# development-setup

My macOS development setup.

Insallation overview:

- Xcode and Command Line Tools
- Homebrew
- Node (version manager)
- Ruby (version manager)

## Install Xcode and Command Line Tools

Search within the app store for Xcode or visit the [website](https://developer.apple.com/xcode/).

Install Command Line Tools:

```sh
# Already installed?
xcode-select --version

# If not, install:
xcode-select --install
```

## Install Homebrew

Docs: [https://brew.sh/](https://brew.sh/)

```sh
# Install
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"

# Restart your terminal. Successful? Following command should print a version number.
brew --version

# The doctor command will help you to fix any macOS issues
brew doctor
```

## Install Node (with Node version manager) :two_hearts:

Docs: [nvm](https://github.com/nvm-sh/nvm), is a node version manager for [node.js](https://nodejs.org/en/), which will save us a lot of version troubles in the future. :sparkles:

```sh
# Install [latest install script](https://github.com/nvm-sh/nvm#installing-and-updating)
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.3/install.sh | bash

# Restart your terminal. Successful? Following command should print a version number.
nvm --version

# macOS 10.15.x and above have the Z Shell (zsh) as default, so nvm source lines should be present in your zsh config file `~/.zshrc`, search for the NVM_DIR export: `export NVM_DIR`

# List, install latest node LTS version and set it as default:
nvm ls-remote

# Install v12.16.1, for example:
nvm install 12.16.1

# Use it:
nvm use 12.16.1

# Set it as default
nvm alias default 12.16.1

# Now you should be able to use and log the defined node and npm version
node --version && npm --version

# Will print
v12.16.1
6.13.4
```

## Install Ruby version manager

Ruby comes with a fresh macOS installation. I also prefer to install a version manager for Ruby, as it won't install any Ruby related software globally (no `sudo`, yay) and helps us to keep our working machines clean, to prevent any errors.

Docs: [https://rvm.io/](https://rvm.io/)

```sh
# Optional GPG key install ([GNU Privacy Guard](https://en.wikipedia.org/wiki/GNU_Privacy_Guard))
gpg2 --recv-keys 409B6B1796C275462A1703113804BB82D39DC0E3 7D2BAF1CF37B13E2069D6956105BD0E739499BDB

# Install RVM with default Ruby and Rails
curl -sSL https://get.rvm.io | bash -s stable --rails

# Restart your terminal. Successful? Following command should print something like 'rvm is a shell function'.
type rvm | head -n 1
```
