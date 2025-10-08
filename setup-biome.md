
```jsonc
// biome.jsonc
{
  "$schema": "https://biomejs.dev/schemas/2.2.5/schema.json",
  "assist": {
    "actions": {
      "source": {
        "useSortedAttributes": "on",
        "useSortedKeys": "on",
        "useSortedProperties": "on"
      }
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
        "useUniqueElementIds": "off"
      },
      "nursery": {
        "useSortedClasses": "error"
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
