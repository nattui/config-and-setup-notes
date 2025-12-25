# Zshrc

```bash
# Starship
# Install: brew install starship
# Reference: https://starship.rs/#zsh
eval "$(starship init zsh)"

# Zoxide
# Install: brew install zoxide
# Reference: https://formulae.brew.sh/formula/zoxide
eval "$(zoxide init zsh)"

# Autosuggestions
# Install: brew install zsh-autosuggestions
# Reference: https://formulae.brew.sh/formula/zsh-autosuggestions
source $HOMEBREW_PREFIX/share/zsh-autosuggestions/zsh-autosuggestions.zsh

# Syntax highlighting
# Install: brew install zsh-syntax-highlighting
# Reference: https://formulae.brew.sh/formula/zsh-syntax-highlighting
source $HOMEBREW_PREFIX/share/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh



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
alias bv="bun --version"
alias bx="bunx"
alias n="npm"
alias nb="npm run build"
alias nd="npm run dev"
alias ni="npm install"
alias np="npm publish"
alias nr="npm run"
alias ns="npm run start"
alias nu="npm update"
alias nv="npm --version"
alias nx="npx"
alias p="pnpm"
alias pa="pnpm add"
alias pb="pnpm run build"
alias pbs="pnpm run build && pnpm run start"
alias pd="pnpm run dev"
alias pi="pnpm install"
alias pn="pnpm run build && pnpm run start"
alias ppd="npm pack --dry-run"
alias ppp="npm publish --access=public"
alias ppr="pnpm publish --access=restricted"
alias pr="pnpm run"
alias ps="pnpm run start"
alias pu="pnpm update"
alias pv="pnpm --version"
alias px="pnpx"
# Git
alias g="git"
alias gc="git clone"
alias gl="git pull"
alias gp="git pull"
alias gph="git push"
alias gpl="git pull"
alias gs="gh auth switch"
# Zoxide: cd alternative
alias cd="z"
# eza: ls alternative
alias ls="eza --all --color=always --group-directories-first --hyperlink --icons=always --oneline"
# Database
alias dbm="pnpm run db:migrate"
alias dbp="pnpm run db:push"
alias dbs="pnpm run db:studio"
# Software
alias c.="cursor ."
alias c="cursor ."
# Process management
alias k='_k() { lsof -ti:$1 | xargs kill -9 2>/dev/null && echo "Killed process on port $1" || echo "No process found on port $1"; }; _k'
# Getting IP address
alias i="ipconfig getifaddr en0"
alias ip="ipconfig getifaddr en0"
# Information
alias info="fastfetch"
alias info-all="fastfetch --config all"
# System information
alias sys="btop"
# Reload `.zshrc`
alias r="source ~/.zshrc"
alias reload="source ~/.zshrc"
# Edit `.zshrc` file
alias s="cursor ~/.zshrc"
alias setting="cursor ~/.zshrc"
alias settings="cursor ~/.zshrc"
alias sg="cursor ~/.gitconfig"
# Host
alias h="sudo vim /etc/hosts"
alias host="sudo vim /etc/hosts"
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
