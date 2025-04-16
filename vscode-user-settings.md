# VSCode User Settings

Last updated: `2025/04/06`

```jsonc
{
  "accessibility.signalOptions.volume": 25, // Volume level for accessibility sound signals
  "accessibility.signals.format": { "sound": "always" }, // Makes a sound on format
  "accessibility.signals.save": { "sound": "always" }, // Makes a sound on save
  "cursor.composer.shouldChimeAfterChatFinishes": true, // Play a sound when a chat response is completed
  "diffEditor.hideUnchangedRegions.enabled": true, // Shows unchanged regions
  "diffEditor.ignoreTrimWhitespace": false, // Keep whitespace in diffs
  "editor.codeActionsOnSave": { "source.fixAll.eslint": "explicit" }, // On save, fix all eslint errors
  "editor.defaultFormatter": "esbenp.prettier-vscode", // Prettier extension
  "editor.fontFamily": "CommitMono Nerd Font", // Editor font
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
  "extensions.ignoreRecommendations": true, // Ignore recommendations extensions
  "files.associations": { "*.css": "tailwindcss" }, // Fixes `Unknown at rule @tailwindpostcss(unknownAtRules)`
  "files.eol": "\n", // Default EOL
  "files.insertFinalNewline": true, // Insert final newline
  "files.trimFinalNewlines": true, // Trim final newlines
  "files.trimTrailingWhitespace": true, // Trim trailing whitespace
  "git.autofetch": true, // Commits will automatically be fetched
  "git.autofetchPeriod": 180, // Duration in seconds between each automatic git fetch
  "git.confirmSync": false, // Disable automatic git fetch
  "git.enableSmartCommit": true, // Commit all changes when there are no staged changes
  "javascript.suggest.names": false, // Disable suggesting names (e.g. pressing tab on `log` would not do console.log) Reference: https://www.youtube.com/watch?v=-ALLgIoAgcw
  "javascript.updateImportsOnFileMove.enabled": "always", // Automatically update imports
  "scm.defaultViewMode": "tree", // Shows file tree in the source control sidebar tab
  "terminal.integrated.fontFamily": "CommitMono Nerd Font", // Terminal font
  "typescript.preferences.autoImportFileExcludePatterns": ["lucide-react"], // Change the autocompletion (e.g. import { Link } from "lucide-react") Reference: https://lucide.dev/guide/advanced/aliased-names#choosing-import-name-style
  "typescript.preferences.importModuleSpecifier": "non-relative", // Prefers a non-relative import based
  "typescript.updateImportsOnFileMove.enabled": "always", // Automatically update imports
  "window.commandCenter": false, // Turns off the editor top section
  "window.nativeTabs": true, // Enables macOS Sierra window tabs
  "workbench.activityBar.orientation": "vertical", // Editor (Cursor) activity bar on side
  "workbench.colorTheme": "Cute", // Editor color theme
  "workbench.editor.customLabels.patterns": {
    // Custom tab labels for Next.js projects
    "**/app/**/page.tsx": "${dirname}/${filename}", // route.ts
    "**/app/**/layout.tsx": "${dirname}/${filename}" // layout.tsx, page.tsx, template.tsx
  },
  "workbench.iconTheme": "material-icon-theme", // Editor file icon theme
  "workbench.productIconTheme": "fluent-icons", // Editor product icon theme
  //
  //
  //
  //
  // Spellcheck
  "cSpell.ignorePaths": ["node_modules", "package-lock.json", "pnpm-lock.yaml"],
  "cSpell.userWords": [
    "Adblockers",
    "addgroup",
    "adduser",
    "Apaz",
    "Asar",
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
    "cdylib",
    "Cgxq",
    "chpt",
    "clsx",
    "codehike",
    "Comeau's",
    "compat",
    "contenteditable",
    "contentlayer",
    "cookieconsent",
    "craco",
    "craftjs",
    "crunker",
    "datetime",
    "dbaeumer",
    "devsafe",
    "doikdnkglb",
    "domhandler",
    "dotenv",
    "drei",
    "Dribbble",
    "editorjs",
    "eede",
    "elif",
    "esac",
    "esbenp",
    "eslintcache",
    "Etags",
    "Farcaster",
    "fastify",
    "FKZK",
    "fluidframework",
    "fontsource",
    "Frontmatter",
    "fullhuman",
    "genstats",
    "getifaddr",
    "Gleap",
    "GLTF",
    "GOCSPX",
    "googleusercontent",
    "grayscale",
    "groq",
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
    "icns",
    "iconify",
    "iframes",
    "ignorecase",
    "importmap",
    "isbot",
    "iterm",
    "ivjn",
    "jagplbtsj",
    "Jefit",
    "jetbrains",
    "jscoverage",
    "jspm",
    "jsrsasign",
    "jsxs",
    "kibibytes",
    "killall",
    "KINDE",
    "kleur",
    "konva",
    "ldrs",
    "libass",
    "libc",
    "lockb",
    "Logomark",
    "lucide",
    "Luma",
    "mapbox",
    "mapboxgl",
    "mdxts",
    "mechvibes",
    "Monokai",
    "Natt",
    "nattui",
    "nattwasm",
    "neondatabase",
    "nextjs",
    "nftychat",
    "NGKD",
    "njsproj",
    "nodelib",
    "nomodule",
    "nord",
    "noreferrer",
    "npath",
    "nprogress",
    "nraptor",
    "ntvs",
    "nums",
    "nuxt",
    "nvim",
    "Okcoin",
    "oklch",
    "openpanel",
    "overscroll",
    "pageview",
    "Palo",
    "papaparse",
    "paralleldrive",
    "payloadcms",
    "photoeditorsdk",
    "picocolors",
    "pids",
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
    "querybuilder",
    "QVAHLYopgx",
    "raindropio",
    "reactflow",
    "Rebond",
    "recma",
    "REFF",
    "registrator",
    "rehype",
    "Reimagining",
    "relocator",
    "resizer",
    "rgba",
    "rideshare",
    "rlib",
    "roadmaps",
    "rodio",
    "roseville",
    "rsbuild",
    "RZABFA",
    "seedrandom",
    "sema",
    "serde",
    "shadcn",
    "shiki",
    "shikijs",
    "shottr",
    "signin",
    "signout",
    "signup",
    "Sjsu",
    "snowshift",
    "sonner",
    "sslmode",
    "staticlib",
    "statsig",
    "stega",
    "stylelint",
    "stylelintrc",
    "stylesheet",
    "subroutes",
    "supabase",
    "SXGA",
    "tailwindcss",
    "tailwindpostcss",
    "tanstack",
    "tauri",
    "testheadless",
    "testonly",
    "todos",
    "tokenless",
    "Topbar",
    "trivago",
    "trunc",
    "tsec",
    "tsup",
    "tulare",
    "turbopack",
    "turborepo",
    "Txuxzcc",
    "uiball",
    "umami",
    "unfetch",
    "uploadthing",
    "uuidv",
    "valibot",
    "vercel",
    "vercelignore",
    "versionlens",
    "vinxi",
    "vite",
    "vuepress",
    "Waitlist",
    "watchpack",
    "wavesurfer",
    "WCAG",
    "wicg",
    "wscript",
    "yoyo",
    "zipf",
    "zustand"
  ]
}
```
