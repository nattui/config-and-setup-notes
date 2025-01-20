# New Mac Setup

Last updated: `2025/01/19`

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

# install fonts
# brew tap homebrew/cask-fonts
# brew install --cask font-jetbrains-mono-nerd-font
# brew install --cask font-inter

# install software
brew install --cask iterm2
brew install --cask visual-studio-code
brew install --cask brave-browser
brew install --cask raycast
brew install --cask figma
brew install --cask shottr
brew install --cask raindropio
brew install --cask spotify

# EG Oreo 75 volume
brew install --cask mechvibes

# install starship
brew install starship

code ~/.zshrc
# Documentation: https://starship.rs/#zsh
# Add this line to ~/.zshrc
# eval "$(starship init zsh)"

brew install zsh-autosuggestions
```
