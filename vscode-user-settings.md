Last updated: `2024/12/26`

```json
{
  "accessibility.signals.format": { "sound": "always" }, // Makes a sound on format
  "accessibility.signals.save": { "sound": "always" }, // Makes a sound on save
  "diffEditor.ignoreTrimWhitespace": false, // Keep whitespace in diffs
  "editor.codeActionsOnSave": { "source.fixAll.eslint": "explicit" }, // On save, fix all eslint errors
  "editor.defaultFormatter": "esbenp.prettier-vscode", // Prettier extension
  "editor.fontFamily": "CommitMono", // Editor font
  "editor.fontSize": 12, // Editor font size
  "editor.formatOnPaste": true, // On paste, format
  "editor.formatOnSave": true, // On save, format
  "editor.guides.bracketPairs": true, // Show bracket pairs
  "editor.lineHeight": 1.625, // Slight increase from default 1.5
  "editor.minimap.enabled": false, // Disable minimap
  "editor.renderWhitespace": "boundary", // Render whitespace characters
  "editor.stickyScroll.enabled": true, // Editor sticky scroll enabled
  "editor.tabSize": 2, // Default tab size
  "editor.wordWrap": "on", // Editor wrap lines
  "eslint.validate": [
    // ESLint extension
    "html",
    "javascript",
    "javascriptreact",
    "typescriptreact"
  ],
  "explorer.sortOrder": "default", // Default file and folder order
  "files.associations": { "*.css": "tailwindcss" }, // Fixes `Unknown at rule @tailwindpostcss(unknownAtRules)`
  "files.eol": "\n", // Default EOL
  "files.insertFinalNewline": true, // Insert final newline
  "files.trimFinalNewlines": true, // Trim final newlines
  "files.trimTrailingWhitespace": true, // Trim trailing whitespace
  "javascript.suggest.names": false, // Disable suggesting names (e.g. pressing tab on `log` would not do console.log) Reference: https://www.youtube.com/watch?v=-ALLgIoAgcw
  "javascript.suggest.paths": true, // Enable suggestions for paths in import
  "javascript.updateImportsOnFileMove.enabled": "always", // Automatically update imports
  "scm.defaultViewMode": "tree", // Shows file tree in the source control sidebar tab
  "terminal.integrated.fontFamily": "JetBrainsMono Nerd Font", // Terminal font
  "window.commandCenter": false, // Turns off the editor top section
  "window.nativeTabs": true, // Enables macOS Sierra window tabs
  "workbench.colorTheme": "GitHub Dark Default", // Editor color theme
  "workbench.editor.customLabels.patterns": {
    // Custom tab labels for Next.js projects
    "**/app/**/page.tsx": "${dirname}/${filename}", // route.ts
    "**/app/**/layout.tsx": "${dirname}/${filename}" // layout.tsx, page.tsx, template.tsx
  },
  "workbench.iconTheme": "material-icon-theme", // Editor file icon theme
  //
  //
  //
  //
  // Spellcheck
  "cSpell.ignorePaths": ["node_modules", "package-lock.json", "pnpm-lock.yaml"],
  "cSpell.userWords": [
    "Adblockers",
    "Apaz",
    "autodocs",
    "autofetch",
    "autoincrement",
    "autoprefixer",
    "biomejs",
    "Bluesky",
    "bmsh",
    "bocbwb",
    "Bottombar",
    "buildspace",
    "bunchee",
    "bunfig",
    "bunx",
    "caniuse",
    "cdpath",
    "Cgxq",
    "chpt",
    "clsx",
    "codehike",
    "Comeau's",
    "compat",
    "contentlayer",
    "datetime",
    "doikdnkglb",
    "drei",
    "Dribbble",
    "eede",
    "esbenp",
    "Etags",
    "Farcaster",
    "fastify",
    "FKZK",
    "fontsource",
    "Frontmatter",
    "fullhuman",
    "genstats",
    "getifaddr",
    "Gleap",
    "GLTF",
    "GOCSPX",
    "googleusercontent",
    "Grotesk",
    "gsap",
    "gtin",
    "Hackathon",
    "happydom",
    "Hbwwmpp",
    "headlessui",
    "Hfcy",
    "Highcharts",
    "hono",
    "hookform",
    "iconify",
    "iframes",
    "ignorecase",
    "ivjn",
    "jagplbtsj",
    "Jefit",
    "jetbrains",
    "jsxs",
    "kibibytes",
    "kleur",
    "ldrs",
    "lockb",
    "Logomark",
    "lucide",
    "Luma",
    "mapbox",
    "mapboxgl",
    "mdxts",
    "Monokai",
    "Natt",
    "nattui",
    "nattwasm",
    "neondatabase",
    "nextjs",
    "nftychat",
    "NGKD",
    "nodelib",
    "nomodule",
    "nord",
    "noreferrer",
    "npath",
    "nprogress",
    "nraptor",
    "nums",
    "Okcoin",
    "openpanel",
    "overscroll",
    "pageview",
    "Palo",
    "paralleldrive",
    "picocolors",
    "Pirsch",
    "pirschjs",
    "pixrem",
    "pkgjs",
    "placekitten",
    "Plaiceholder",
    "planetscale",
    "playfair",
    "pnav",
    "pnpx",
    "postbuild",
    "postcss",
    "posthog",
    "prebuild",
    "preid",
    "prepass",
    "Progressbar",
    "pscale",
    "psdb",
    "pseudoelements",
    "pslgjhh",
    "QVAHLYopgx",
    "Rebond",
    "recma",
    "registrator",
    "rehype",
    "Reimagining",
    "relocator",
    "rideshare",
    "roadmaps",
    "rsbuild",
    "RZABFA",
    "seedrandom",
    "sema",
    "shadcn",
    "shiki",
    "shikijs",
    "signin",
    "signout",
    "signup",
    "Sjsu",
    "snowshift",
    "sonner",
    "sslmode",
    "stylelint",
    "stylelintrc",
    "stylesheet",
    "subroutes",
    "supabase",
    "SXGA",
    "tailwindcss",
    "tailwindpostcss",
    "tanstack",
    "testheadless",
    "testonly",
    "todos",
    "Topbar",
    "trivago",
    "trunc",
    "tsec",
    "tsup",
    "turbopack",
    "turborepo",
    "Txuxzcc",
    "uiball",
    "umami",
    "unfetch",
    "uuidv",
    "valibot",
    "vercel",
    "vercelignore",
    "versionlens",
    "Waitlist",
    "watchpack",
    "wicg",
    "yoyo",
    "zustand"
  ]
}
```
