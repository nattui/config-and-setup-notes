# New Mac setup

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
brew install gh

brew tap oven-sh/bun
brew install bun

# install fonts
# https://formulae.brew.sh/cask-font
brew install --cask font-commit-mono-nerd-font
brew install --cask font-geist
brew install --cask font-google-sans-code
brew install --cask font-inter
brew install --cask font-inter-tight
brew install --cask font-jetbrains-mono-nerd-font

# install software
brew install --cask ghostty
brew install --cask cursor
brew install --cask figma
brew install --cask shottr
brew install --cask raindropio
brew install --cask spotify
brew install --cask the-unarchiver
brew install --cask applite
brew install --cask steam
brew install --cask raycast

Maybe
brew install --cask slack
brew install --cask google-chrome

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
brew install zsh-syntax-highlighting
```
