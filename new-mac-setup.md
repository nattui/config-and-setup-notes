# New Mac Setup

Last updated: `2025/05/24`

## Show hidden files

To show hidden files globally on a Mac and have it persist, run the following commands in the Terminal:

```bash
defaults write com.apple.Finder AppleShowAllFiles true
killall Finder
```

## Software

```
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
brew install oven-sh/bun/bun
brew install gh

# install fonts
brew install --cask font-commit-mono-nerd-font
brew install --cask font-jetbrains-mono-nerd-font

# install software
brew install --cask ghostty
brew install --cask cursor
brew install --cask figma
brew install --cask shottr
brew install --cask raindropio
brew install --cask spotify

Maybe
brew install --cask raycast

# Keyboard sounds
# NK Cream 85 volume
brew install --cask mechvibes

# install Starship
brew install starship

code ~/.zshrc
# Documentation: https://starship.rs/#zsh
# Add this line to ~/.zshrc
# eval "$(starship init zsh)"

brew install zsh-autosuggestions
```
