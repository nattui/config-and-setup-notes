# Vite

`eslint.config.js`

```js
/** @type {import('eslint').Linter.Config[]} */

import js from "@eslint/js"
import perfectionist from "eslint-plugin-perfectionist"
import react from "eslint-plugin-react"
import unicorn from "eslint-plugin-unicorn"
import unused from "eslint-plugin-unused-imports"
import globals from "globals"
import ts from "typescript-eslint"

export default [
  ...ts.configs.recommended,
  js.configs.recommended,
  perfectionist.configs["recommended-natural"],
  react.configs.flat.recommended,
  unicorn.configs["flat/all"],
  {
    files: ["**/*.{js,mjs,cjs,ts,jsx,tsx}"],
    languageOptions: {
      globals: globals.browser,
    },
    plugins: {
      "unused-imports": unused,
    },
    rules: {
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
      "react/react-in-jsx-scope": "off",
      "unicorn/consistent-function-scoping": "off",
      "unicorn/import-style": "off",
      "unicorn/no-keyword-prefix": "off",
      "unicorn/prevent-abbreviations": "off",
      "unused-imports/no-unused-imports": "error",
    },
  },
]
```
