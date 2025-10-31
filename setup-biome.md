
```jsonc
// biome.jsonc
{
  "$schema": "https://biomejs.dev/schemas/2.3.2/schema.json",
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
      "tailwindDirectives": true
    }
  },
  "files": {
    "ignoreUnknown": false,
    "includes": ["**", "!**/package.json"]
  },
  "formatter": {
    "indentStyle": "space"
  },
  "javascript": {
    "formatter": {
      "quoteStyle": "double",
      "semicolons": "asNeeded"
    }
  },
  "linter": {
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
