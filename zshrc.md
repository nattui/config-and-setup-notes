# Zshrc

Last updated: `2025/06/15`

```bash
# :: Notes ::
# Remember to add this
# git config --global core.ignorecase false
# cursor ~/.gitconfig

# Starship
# Install: brew install starship
# Reference: https://starship.rs/#zsh
eval "$(starship init zsh)"

# Autosuggestions
# Install: brew install zsh-autosuggestions
# Reference: https://formulae.brew.sh/formula/zsh-autosuggestions
source $(brew --prefix)/share/zsh-autosuggestions/zsh-autosuggestions.zsh

# pnpm
export PNPM_HOME="/Users/snowshift/Library/pnpm"
case ":$PATH:" in
  *":$PNPM_HOME:"*) ;;
  *) export PATH="$PNPM_HOME:$PATH" ;;
esac
# pnpm end

# nvm
  export NVM_DIR="$HOME/.nvm"
  [ -s "/opt/homebrew/opt/nvm/nvm.sh" ] && \. "/opt/homebrew/opt/nvm/nvm.sh"  # This loads nvm
  [ -s "/opt/homebrew/opt/nvm/etc/bash_completion.d/nvm" ] && \. "/opt/homebrew/opt/nvm/etc/bash_completion.d/nvm"  # This loads nvm bash_completion

# bun completions
[ -s "/Users/snowshift/.bun/_bun" ] && source "/Users/snowshift/.bun/_bun"

# bun
export BUN_INSTALL="$HOME/.bun"
export PATH="$BUN_INSTALL/bin:$PATH"

# Aliases
# JS package managers
alias b="bun"
alias bb="bun run build"
alias bbs="bun run build && bun run start"
alias bd="bun run dev"
alias bi="bun install"
alias br="bun run"
alias bs="bun run start"
alias bu="bun update"
alias bx="bunx"
alias n="npm"
alias nb="npm run build"
alias nd="npm run dev"
alias ni="npm install"
alias np="npm publish"
alias nr="npm run"
alias ns="npm run start"
alias nu="npm update"
alias nx="npx"
alias p="pnpm"
alias pa="pnpm add"
alias pb="pnpm run build"
alias pbs="pnpm run build && pnpm run start"
alias pd="pnpm run dev"
alias pi="pnpm install"
alias pn="pnpm run build && pnpm run start"
alias pp="pnpm run build && pnpm publish --no-git-checks --access=public"
alias pr="pnpm run"
alias ps="pnpm run start"
alias pu="pnpm update"
alias px="pnpx"
# Git
alias g="git"
alias gc="git clone"
alias gph="git push"
alias gpl="git pull"
alias gs="gh auth switch"
# Database
alias dbm="pnpm run db:migrate"
alias dbp="pnpm run db:push"
alias dbs="pnpm run db:studio"
# Software
alias c.="cursor ."
alias c="cursor ."
# Getting IP address
alias i="ipconfig getifaddr en0"
alias ip="ipconfig getifaddr en0"
# Reload `.zshrc`
alias r="source ~/.zshrc"
alias reload="source ~/.zshrc"
# Edit `.zshrc` file
alias s="cursor ~/.zshrc"
alias setting="cursor ~/.zshrc"
alias settings="cursor ~/.zshrc"
alias sg="cursor ~/.gitconfig"
# Zip folder
alias zipf="zip -er <FILE_NAME>.zip <FOLDER_NAME>"
# Quick navigation
alias god="cd /Users/snowshift/Documents/"
alias gog="cd /Users/snowshift/Documents/github"
alias cdd="cd /Users/snowshift/Documents/"
alias cdg="cd /Users/snowshift/Documents/github"
# Text editor
alias nvim="cursor"
alias vim="cursor"
# Generate a random token
# 128-bit (16-byte) Token: This length is commonly used for generating session tokens, API keys, or unique identifiers in various applications.
# 256-bit (32-byte) Token: Often used for generating security tokens, access tokens, or cryptographic keys for secure communications.
# 512-bit (64-byte) Token: This length is suitable for generating strong cryptographic keys or tokens for highly sensitive operations.
alias token="openssl rand -hex 32"
alias t="openssl rand -hex 32"

# Console Ninja
PATH=~/.console-ninja/.bin:$PATH
```
