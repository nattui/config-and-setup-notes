# Next.js Setup

Last updated: `2025/04/05`

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

# pnpm install @phosphor-icons/react
pnpm install lucide-react
pnpm install @nattui/tailwind-tokenless

pnpm install -D eslint-plugin-perfectionist
pnpm install -D eslint-plugin-unicorn
pnpm install -D eslint-plugin-unused-imports
pnpm install -D prettier
pnpm install -D prettier-plugin-css-order
pnpm install -D prettier-plugin-packagejson
pnpm install -D prettier-plugin-sort-json
pnpm install -D prettier-plugin-tailwindcss

# Application
pnpm install bcryptjs
pnpm install drizzle-orm
pnpm install jose
pnpm install postgres
pnpm install radix-ui
pnpm install zod
pnpm install zustand

pnpm install -D drizzle-kit
```

`package.json`

```json
"scripts": {
  "build": "next build --turbopack",
  "check": "pnpx npm-run-all --parallel check:format check:lint",
  "check:fix": "pnpx npm-run-all --parallel check:format:fix check:lint:fix",
  "check:format": "prettier --check .",
  "check:format:fix": "prettier --write .",
  "check:lint": "next lint",
  "check:lint:fix": "next lint --fix",
  "db:generate": "drizzle-kit generate --config=drizzle.config.ts",
  "db:introspect": "drizzle-kit introspect --config=drizzle.config.ts",
  "db:migrate": "drizzle-kit migrate --config=drizzle.config.ts",
  "db:push": "drizzle-kit push --config=drizzle.config.ts",
  "db:studio": "drizzle-kit studio --config=drizzle.config.ts --verbose",
  "dev": "next dev --port 3001 --turbopack",
  "docker": "pnpm docker:build && pnpm docker:run",
  "docker:build": "docker build --tag next-docker .",
  "docker:run": "docker run --publish 3001:3001 next-docker",
  "start": "next start --port 3001 --turbopack",
  "update": "pnpx npm-check-updates --upgrade"
},
```

`eslint.config.mjs`

```jsx
import { FlatCompat } from "@eslint/eslintrc"
import perfectionist from "eslint-plugin-perfectionist"
import unicorn from "eslint-plugin-unicorn"
import unusedImports from "eslint-plugin-unused-imports"
import { dirname } from "node:path"
import { fileURLToPath } from "node:url"

const __filename = fileURLToPath(import.meta.url)
const __dirname = dirname(__filename)

const compat = new FlatCompat({ baseDirectory: __dirname })

const eslintConfig = [
  ...compat.extends("next/core-web-vitals", "next/typescript"),
  perfectionist.configs["recommended-natural"],
  unicorn.configs["all"],
  {
    plugins: {
      "unused-imports": unusedImports,
    },
    rules: {
      "@next/next/no-img-element": "off",
      "@typescript-eslint/no-empty-object-type": [
        "error",
        {
          allowInterfaces: "with-single-extends",
        },
      ],
      "perfectionist/sort-imports": [
        "error",
        {
          newlinesBetween: "never",
          sortSideEffects: true,
        },
      ],
      "unicorn/consistent-function-scoping": "off",
      "unicorn/import-style": "off",
      "unicorn/no-keyword-prefix": "off",
      "unicorn/no-unused-properties": "warn",
      "unicorn/prevent-abbreviations": "off",
      "unused-imports/no-unused-imports": "error",
    },
  },
]

export default eslintConfig
```

`.prettierignore`

```
pnpm-lock.yaml
```

`.prettierrc`

Don’t use `prettier.config.js` with Next.js https://prettier.io/docs/en/configuration

```json
{
  "jsonRecursiveSort": true,
  "plugins": [
    "prettier-plugin-css-order",
    "prettier-plugin-packagejson",
    "prettier-plugin-sort-json",
    "prettier-plugin-tailwindcss"
  ],
  "semi": false
}
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

---

---

---

---

---

> [!WARNING]
> Old

`.eslintrc.json` old

```json
{
  "extends": [
    "eslint:recommended",
    "next/core-web-vitals",
    "plugin:@typescript-eslint/strict",
    "plugin:@typescript-eslint/stylistic-type-checked",
    "plugin:perfectionist/recommended-natural-legacy",
    "plugin:unicorn/all",
    "prettier"
  ],
  "parser": "@typescript-eslint/parser",
  "parserOptions": {
    "project": ["./tsconfig.json"]
  },
  "plugins": ["@typescript-eslint"],
  "root": true,
  "rules": {
    "perfectionist/sort-imports": "off",
    "semi": "off",
    "unicorn/no-keyword-prefix": "off",
    "unicorn/prevent-abbreviations": [
      "error",
      {
        "replacements": {
          "params": false,
          "props": false,
          "ref": false
        }
      }
    ]
  }
}
```

> [!WARNING]
> Old

`tailwind.config.ts`

```tsx
import type { Config } from "tailwindcss"
import {
  borderRadius10 as borderRadius,
  boxShadow,
  colors,
  fontFamily,
  fontSize10 as fontSize,
  fontWeight,
  screens10 as screens,
  spacing10 as spacing,
} from "@nattui/tailwind-theme-config"

const config: Config = {
  content: [
    "./app/**/*.{js,ts,jsx,tsx,mdx}",
    "./components/**/*.{js,ts,jsx,tsx,mdx}",
    "./pages/**/*.{js,ts,jsx,tsx,mdx}",
  ],
  darkMode: "class",
  theme: {
    borderRadius,
    boxShadow,
    colors,
    extend: {
      colors: {
        border: "var(--mauve-a4)",
      },
      fontSize: {
        "10": "1rem",
        "13": "1.3rem",
        "15": "1.5rem",
      },
      lineHeight: {
        reading: "1.875",
      },
    },
    fontFamily,
    fontSize,
    fontWeight,
    screens,
    spacing,
  },
}

export default config
```
