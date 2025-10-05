```js
// eslint.config.mjs for next.js project

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
