Multiple Git identities (using GitHub)

```bash
brew install gh

# brew upgrade gh

gh --version
```

```bash
gh auth login --hostname github.com --git-protocol https

# ? Where do you use GitHub? GitHub.com
# ? What is your preferred protocol for Git operations on this host? HTTPS
# ? Authenticate Git with your GitHub credentials? Yes
# ? How would you like to authenticate GitHub CLI? Paste an authentication token
# Tip: you can generate a Personal Access Token here https://github.com/settings/tokens
# The minimum required scopes are 'repo', 'read:org', 'workflow'.
# ? Paste your authentication token: ****************************************
# - gh config set -h github.com git_protocol https
# ✓ Configured git protocol
# ✓ Logged in as {{ GITHUB_USERNAME }}
```

```bash
gh auth status
# github.com
#   ✓ Logged in to github.com account {{ USER_1 }} (keyring)
#   - Active account: true
#   - Git operations protocol: https
#   - Token: ghp_************************************
#   - Token scopes: 'read:org', 'repo', 'workflow'

#   ✓ Logged in to github.com account {{ USER_2 }} (keyring)
#   - Active account: false
#   - Git operations protocol: https
#   - Token: ghp_************************************
#   - Token scopes: 'read:org', 'repo', 'workflow'

gh auth switch
```

```yml
# ~/.config/gh/hosts.yml
github.com:
  git_protocol: https
  users:
    USER_1:
    USER_2:
  user: USER_1
```
