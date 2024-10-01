# development-setup

_Installation overview:_

- [Show hidden files](#show-hidden-files)
- [Xcode and Command Line Tools](#install-xcode-and-command-line-tools)
- [Homebrew](#install-homebrew)
- [Node](#install-node-with-node-version-manager-two_hearts) (version manager) and/or [asdf](#install-asdf-multiple-runtime-version-management) (multiple runtime version management)

## Show hidden files

```sh
defaults write com.apple.Finder AppleShowAllFiles true
killall Finder
```

## Install Xcode and Command Line Tools

- App store: search for "Xcode"
- Apple documentation [website](https://developer.apple.com/xcode/).

Install Command Line Tools:

```sh
# Already installed?
xcode-select --version

# If not, install:
xcode-select --install
```

## Install Homebrew

Awesome package manager for macOS.
Docs: [https://brew.sh/](https://brew.sh/)

```sh
# Install
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# Restart the terminal. Successful? Following command should print a version number.
brew --version

# 'doctor' command helps with potential macOS issues
brew doctor
```

## Install Node (with Node version manager) :two_hearts:

Docs: [nvm](https://github.com/nvm-sh/nvm), is a node version manager for [node.js](https://nodejs.org/en/), which will save us a lot of version troubles in the future. :sparkles:

Pre-check for [latest install script](https://github.com/nvm-sh/nvm#installing-and-updating).

```sh
# Install
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.3/install.sh | bash

# Restart the terminal. Successful? Following command should print a version number.
nvm --version

# macOS 10.15.x and above have the Z Shell (zsh) as default, so nvm source lines should be present in zsh config file `~/.zshrc`, search for the NVM_DIR export: `export NVM_DIR`

# List, install latest node LTS version and set it as default:
nvm ls-remote

# Install v12.16.1, for example:
nvm install 12.16.1

# Use it:
nvm use 12.16.1

# Set it as default
nvm alias default 12.16.1

# node and npm version check
node --version && npm --version

# Will print
v12.16.1
6.13.4
```

## Install asdf (multiple runtime version management)

Docs: [https://asdf-vm.com/](https://asdf-vm.com/)
