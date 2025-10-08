# Next.js setup

```bash
pnpx create-next-app@latest

Progress: resolved 1, reused 0, downloaded 1, added 1, done
✔ What is your project named? … next-2024-12-24
✔ Would you like to use TypeScript? … No / [Yes]
✔ Would you like to use ESLint? … No / [Yes]
✔ Would you like to use Tailwind CSS? … No / [Yes]
✔ Would you like your code inside a `src/` directory? … [No] / Yes
✔ Would you like to use App Router? (recommended) … No / [Yes]
✔ Would you like to use Turbopack for `next dev`? … No / [Yes]
✔ Would you like to customize the import alias (`@/*` by default)? … [No] / Yes
Creating a new Next.js app in /Users/snowshift/Documents/github/next-2024-12-24.

# Open project in VSCode

# 1. Delete README.md contents

# 1. package.json

# Remove name, version, private

pnpm update && pnpm install

pnpm install @nattui/react-components
pnpm install @nattui/tailwind-tokenless
pnpm install lucide-react

pnpm install -D @biomejs/biome
pnpm install -D taze


# Application
pnpm install drizzle-orm
pnpm install postgres
pnpm install radix-ui
pnpm install zod
pnpm install zustand

pnpm install -D drizzle-kit
```

For pnpm workspace configuration (monorepo setup), see [setup-pnpm.md](./setup-pnpm.md)

`package.json`

```json
"scripts": {
  "build": "next build --turbopack",
  "check": "biome check",
  "check:fix": "biome check --unsafe --write",
  "check:package": "sh scripts/sort-package-json.sh",
  "check:type": "next typegen && tsc --noEmit",
  "db:generate": "drizzle-kit generate --config=drizzle.config.ts",
  "db:introspect": "drizzle-kit introspect --config=drizzle.config.ts",
  "db:migrate": "drizzle-kit migrate --config=drizzle.config.ts",
  "db:push": "drizzle-kit push --config=drizzle.config.ts",
  "db:studio": "drizzle-kit studio --config=drizzle.config.ts --verbose",
  "dev": "next dev --port 3001 --turbopack",
  "docker": "pnpm docker:build && pnpm docker:run",
  "docker:build": "docker build --tag next-docker .",
  "docker:run": "docker run --publish 3001:3001 next-docker",
  "start": "next start --port 3001",
  "update": "taze --recursive"
},
```

`styles/global.css`

```css
/* Order matters */
@import "tailwindcss";
@import "@nattui/tailwind-tokenless/styles/10/index.css";
@import "@nattui/tailwind-tokenless/styles/colors/reset.css";
@import "@nattui/tailwind-tokenless/styles/colors/gray/mauve.css";
@import "@nattui/tailwind-tokenless/styles/colors/gray/mauve-alpha.css";
@import "@nattui/tailwind-tokenless/styles/colors/primary/crimson.css";

html {
  font-size: 10px;
}
```

`.vscode/settings.json`

```tsx
  "tailwindCSS.rootFontSize": 10
```
