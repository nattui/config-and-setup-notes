Last updated: `2024/12/26`

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

pnpm install @phosphor-icons/react
pnpm install @radix-ui/colors

pnpm install -D @nattui/tailwind-theme-config
pnpm install -D eslint-config-prettier
pnpm install -D eslint-plugin-perfectionist
pnpm install -D eslint-plugin-unicorn
pnpm install -D prettier
pnpm install -D prettier-plugin-css-order
pnpm install -D prettier-plugin-packagejson
pnpm install -D prettier-plugin-sort-json
pnpm install -D prettier-plugin-tailwindcss

```

`package.json`

```json
"scripts": {
  "build": "next build",
  "dev": "next dev --port 3000 --turbopack",
  "format": "prettier --check .",
  "format:fix": "prettier --write .",
  "lint": "next lint",
  "lint:fix": "next lint --fix",
  "start": "next start",
  "update": "pnpx npm-check-updates -u"
},
```

`eslint.config.mjs`

```jsx
import { FlatCompat } from "@eslint/eslintrc";
import prettier from "eslint-config-prettier";
import perfectionist from "eslint-plugin-perfectionist";
import unicorn from "eslint-plugin-unicorn";
import { dirname } from "node:path";
import { fileURLToPath } from "node:url";

const __filename = fileURLToPath(import.meta.url);
const __dirname = dirname(__filename);

const compat = new FlatCompat({ baseDirectory: __dirname });

const eslintConfig = [
  ...compat.extends("next/core-web-vitals", "next/typescript"),
  {
    plugins: {
      perfectionist,
      prettier,
      unicorn,
    },
    rules: {
      ...perfectionist.configs["recommended-natural"].rules,
      ...unicorn.configs["flat/all"].rules,
      "@next/next/no-img-element": "off",
      "perfectionist/sort-imports": [
        "error",
        {
          newlinesBetween: "never",
          sortSideEffects: true,
        },
      ],
      "unicorn/import-style": "off",
    },
  },
];

export default eslintConfig;
```

`.prettierignore`

```json
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

`tailwind.config.ts`

```tsx
import {
  borderRadius10 as borderRadius,
  colors,
  fontFamily,
  fontSize10 as fontSize,
  fontWeight,
  screens10 as screens,
  spacing10 as spacing,
} from "@nattui/tailwind-theme-config";
import type { Config } from "tailwindcss";

const config: Config = {
  content: [
    "./app/**/*.{js,ts,jsx,tsx,mdx}",
    "./components/**/*.{js,ts,jsx,tsx,mdx}",
    "./pages/**/*.{js,ts,jsx,tsx,mdx}",
  ],
  darkMode: "class",
  theme: {
    borderRadius,
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
};

export default config;
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

`.eslintrc.json` Old

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
