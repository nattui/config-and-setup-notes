```yaml
# pnpm-workspace.yaml

# Catalog defines shared dependency versions across the workspace. This ensures
# consistent versions of dependencies are used throughout all packages in the
# monorepo.
#
# Documentation: https://pnpm.io/catalogs
catalog:
  "@biomejs/biome": "^2.2.5"

# Security feature that delays the installation of newly released dependencies
# to reduce the risk of installing compromised packages. When a new version
# of a dependency is published, pnpm will wait for the specified time period
# before allowing installation, giving the community time to identify and
# report any security issues with the release.
#
# Documentation:
# - https://pnpm.io/blog/releases/10.16#new-setting-for-delayed-dependency-updates
# - https://pnpm.io/settings#minimumreleaseage
minimumReleaseAge: 1440 # 1440 minutes = 1 day

# Defines which directories contain packages that should be included in your
# pnpm workspace (monorepo).
#
# Documentation: https://pnpm.io/workspaces#packages
#
# Example: Shared dependencies: Packages can reference each other using
# workspace protocol (e.g., "my-package": "workspace:*").
packages:
  - "apps/*"
  - "packages/*"

# Fix eslint error where failed to load plugin 'react-hooks' declared in
# eslint-config-next/core-web-vitals.
#
# Reference: https://github.com/vercel/next.js/issues/78813#issuecomment-2908051088
publicHoistPattern:
  - "@next/eslint-plugin-next"
  - "eslint-plugin-react-hooks"
```
