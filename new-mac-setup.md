# New Mac Setup

Last updated: `2025/01/19`

## Show hidden files

To show hidden files globally on a Mac and have it persist, run the following commands in the Terminal:

```bash
defaults write com.apple.Finder AppleShowAllFiles true
killall Finder
```
