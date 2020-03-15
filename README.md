# development-setup

_Installation overview:_

- [Xcode and Command Line Tools](#install-xcode-and-command-line-tools)
- [Homebrew](#install-homebrew)
- [Node (version manager)](#install-node-with-node-version-manager-two_hearts)
- [Ruby (version manager)](#install-ruby-version-manager)

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

Docs: [https://brew.sh/](https://brew.sh/)

```sh
# Install
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"

# terminal restart. Successful? Following command should print a version number.
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

# terminal restart. Successful? Following command should print a version number.
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

## Install Ruby version manager

Ruby comes with a fresh macOS installation. I also prefer to install a version manager for Ruby, as it won't install any Ruby related software globally (no `sudo`, yay) and helps to keep the working machine clean, to prevent any errors.

Docs: [https://rvm.io/](https://rvm.io/)

GPG ([GNU Privacy Guard](https://en.wikipedia.org/wiki/GNU_Privacy_Guard)) key installation isn't required, but security is important, more [infos](https://rvm.io/rvm/security).

```sh
# Optional GPG key install
gpg2 --recv-keys 409B6B1796C275462A1703113804BB82D39DC0E3 7D2BAF1CF37B13E2069D6956105BD0E739499BDB

# RVM install with default Ruby and Rails
curl -sSL https://get.rvm.io | bash -s stable --rails

# terminal restart. Successful? Following command should print something like 'rvm is a shell function'.
type rvm | head -n 1

# Installed ruby and gem version check
which ruby && gem --version

# Will print
/Users/username/.rvm/rubies/ruby-2.6.3/bin/ruby
3.0.8
```
