# Biome setup for Next.js

Remember to rename `.json` to `.jsonc`.

```jsonc
// biome.jsonc
{
  "$schema": "https://biomejs.dev/schemas/2.3.10/schema.json",
  "assist": {
    "actions": {
      "source": {
        "useSortedAttributes": "on",
        "useSortedKeys": "on",
        "useSortedProperties": "on"
      }
    }
  },
  "css": {
    "parser": {
      "cssModules": true,
      "tailwindDirectives": true
    }
  },
  "files": {
    "ignoreUnknown": true,
    "includes": ["**", "!.next", "!build", "!dist", "!node_modules"]
  },
  "formatter": {
    "attributePosition": "multiline",
    "indentStyle": "space",
    "lineWidth": 100
  },
  "javascript": {
    "formatter": {
      "quoteStyle": "double",
      "semicolons": "asNeeded"
    }
  },
  "linter": {
    "domains": {
      "next": "recommended",
      "react": "recommended"
    },
    "rules": {
      "a11y": {
        "noLabelWithoutControl": "off",
        "useAriaPropsSupportedByRole": "off"
      },
      "complexity": {
        "noImportantStyles": "off",
        "noUselessFragments": "off"
      },
      "correctness": {
        "noUnknownProperty": "off",
        "noUnusedImports": {
          "fix": "safe",
          "level": "error"
        },
        "useUniqueElementIds": "off"
      },
      "nursery": {
        "useSortedClasses": {
          "fix": "safe",
          "level": "error"
        }
      },
      "performance": {
        "noImgElement": "off",
        "noReExportAll": "error"
      },
      "recommended": true,
      "style": {
        "noDescendingSpecificity": "off"
      },
      "suspicious": {
        "noArrayIndexKey": "off",
        "noUnknownAtRules": "off"
      }
    }
  },
  "vcs": {
    "clientKind": "git",
    "enabled": true,
    "useIgnoreFile": true
  }
}
```
