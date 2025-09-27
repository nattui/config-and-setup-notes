# Next.js Setup

Last updated: `2025/06/20`

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

bun update && bun install

bun install @nattui/react-components
bun install @nattui/tailwind-tokenless
bun install lucide-react

bun install -D eslint-plugin-better-tailwindcss
bun install -D eslint-plugin-perfectionist
bun install -D eslint-plugin-react-you-might-not-need-an-effect
bun install -D eslint-plugin-unicorn
bun install -D eslint-plugin-unused-imports
bun install -D prettier
bun install -D prettier-plugin-css-order
bun install -D prettier-plugin-packagejson
bun install -D prettier-plugin-sort-json

# Application
bun install bcryptjs
bun install drizzle-orm
bun install jose
bun install postgres
bun install radix-ui
bun install zod
bun install zustand

bun install -D drizzle-kit
```

```yaml
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

# Fix eslint error where failed to load plugin 'react-hooks' declared in
# eslint-config-next/core-web-vitals
#
# Reference: https://github.com/vercel/next.js/issues/78813#issuecomment-2908051088
publicHoistPattern:
  - "@next/eslint-plugin-next"
  - "eslint-plugin-react-hooks"
```

`package.json`

```json
"scripts": {
  "build": "next build --turbopack",
  "check": "pnpm check:format && pnpm check:lint && pnpm check:type",
  "check:fix": "pnpm check:format:fix && pnpm check:lint:fix && pnpm check:type",
  "check:format": "prettier --check .",
  "check:format:fix": "prettier --write .",
  "check:lint": "eslint .",
  "check:lint:fix": "eslint --fix .",
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
  "update": "pnpx npm-check-updates --upgrade"
},
```

`eslint.config.mjs`

```jsx
import { FlatCompat } from "@eslint/eslintrc"
import pluginBetterTailwindcss from "eslint-plugin-better-tailwindcss"
import pluginPerfectionist from "eslint-plugin-perfectionist"
import pluginReactYouMightNotNeedAnEffect from "eslint-plugin-react-you-might-not-need-an-effect"
import pluginUnicorn from "eslint-plugin-unicorn"
import pluginUnusedImports from "eslint-plugin-unused-imports"

const compat = new FlatCompat({ baseDirectory: import.meta.dirname })

const eslintConfig = [
  ...compat.extends("next/core-web-vitals", "next/typescript"),
  pluginPerfectionist.configs["recommended-natural"],
  pluginReactYouMightNotNeedAnEffect.configs["recommended"],
  pluginUnicorn.configs["all"],
  {
    plugins: {
      "better-tailwindcss": pluginBetterTailwindcss,
      "unused-imports": pluginUnusedImports,
    },
    rules: {
      "@next/next/no-img-element": "off",
      "@typescript-eslint/no-empty-object-type": [
        "error",
        {
          allowInterfaces: "with-single-extends",
        },
      ],
      "better-tailwindcss/enforce-consistent-class-order": "warn",
      "better-tailwindcss/enforce-consistent-important-position": "warn",
      "better-tailwindcss/enforce-consistent-line-wrapping": "warn",
      "better-tailwindcss/enforce-consistent-variable-syntax": "warn",
      "better-tailwindcss/enforce-shorthand-classes": "warn",
      "better-tailwindcss/no-conflicting-classes": "error",
      "better-tailwindcss/no-deprecated-classes": "warn",
      "better-tailwindcss/no-duplicate-classes": "warn",
      "better-tailwindcss/no-restricted-classes": "error",
      "better-tailwindcss/no-unnecessary-whitespace": "warn",
      "perfectionist/sort-imports": [
        "error",
        {
          newlinesBetween: "never",
          sortSideEffects: true,
        },
      ],
      "unicorn/consistent-function-scoping": "off",
      "unicorn/no-keyword-prefix": "off",
      "unicorn/no-unused-properties": "warn",
      "unicorn/prevent-abbreviations": "off",
      "unused-imports/no-unused-imports": "error",
    },
    settings: {
      "better-tailwindcss": {
        entryPoint: "styles/global.css",
        tailwindConfig: "tailwind.config.js",
      },
    },
  },
  {
    ignores: [
      ".next/**",
      "build/**",
      "next-env.d.ts",
      "node_modules/**",
      "out/**",
    ],
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
  "cssDeclarationSorterOrder": "alphabetical",
  "jsonRecursiveSort": true,
  "plugins": [
    "prettier-plugin-css-order",
    "prettier-plugin-packagejson",
    "prettier-plugin-sort-json"
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
