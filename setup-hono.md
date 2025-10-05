# Setup hono

```bash
bun add --dev @eslint/js
bun add --dev eslint
bun add --dev eslint-plugin-perfectionist
bun add --dev eslint-plugin-unicorn
bun add --dev eslint-plugin-unused-imports
bun add --dev globals
bun add --dev typescript-eslint
```

```ts
// eslint.config.mts
import pluginJs from "@eslint/js"
import pluginPerfectionist from "eslint-plugin-perfectionist"
import pluginReact from "eslint-plugin-react"
import pluginUnicorn from "eslint-plugin-unicorn"
import pluginUnusedImports from "eslint-plugin-unused-imports"
import { defineConfig } from "eslint/config"
import globals from "globals"
import pluginTsEslint from "typescript-eslint"

export default defineConfig([
  {
    ignores: ["dist/"],
  },
  {
    extends: ["js/recommended"],
    files: ["**/*.{js,mjs,cjs,ts,mts,cts,jsx,tsx}"],
    languageOptions: {
      globals: globals.node,
    },
    plugins: {
      js: pluginJs,
    },
  },
  {
    extends: [
      pluginPerfectionist.configs["recommended-natural"],
      pluginTsEslint.configs["recommended"],
      pluginUnicorn.configs["all"],
    ],
    files: ["**/*.{js,mjs,cjs,ts,mts,cts,jsx,tsx}"],
    plugins: {
      react: pluginReact,
      "unused-imports": pluginUnusedImports,
    },
    rules: {
      "@typescript-eslint/no-empty-object-type": "off",
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
  },
])
```

```json
// tsconfig.json

{
  "compilerOptions": {
    "allowSyntheticDefaultImports": true,
    "esModuleInterop": true,
    "jsx": "react-jsx",
    "jsxImportSource": "hono/jsx",
    "strict": true
  }
}
```
