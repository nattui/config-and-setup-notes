# New Mac setup

## Show hidden files

To show hidden files globally on a Mac and have it persist, run the following commands in the Terminal:

```bash
defaults write com.apple.Finder AppleShowAllFiles true
killall Finder
```

## Software

```bash
# install Homebrew
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# During the installing enter in your MacOS password and continue with `enter`
# It will download Command Line Tools for Xcode which will take very long

# Homebrew opt out of analytics
brew analytics off

# Must-haves
brew install git
brew install node
brew install pnpm
brew install gh
brew install oven-sh/bun/bun

# install fonts
# https://formulae.brew.sh/cask-font
brew install --cask font-commit-mono-nerd-font
brew install --cask font-jetbrains-mono-nerd-font

# install software
brew install --cask applite # Homebrew UI
brew install --cask cursor
brew install --cask figma
brew install --cask ghostty # Terminal
brew install --cask iina # Video player
brew install --cask pika # Color picker
brew install --cask raindropio # Bookmarks
brew install --cask raycast # Launcher
brew install --cask shottr # Screenshot
brew install --cask spotify
brew install --cask steam
brew install --cask the-unarchiver
brew install --cask brave-browser # Browser

Maybe
brew install --cask google-chrome
brew install --cask productdevbook/tap/portkiller
brew install --cask slack

# Keyboard sounds
# NK Cream 85 volume
brew install --cask mechvibes

# install Starship
brew install starship

brew install eza
brew install fastfetch
brew install zoxide
brew install zsh-autosuggestions
brew install zsh-syntax-highlighting
brew install --cask nikitabobko/tap/aerospace
```
