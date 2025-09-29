# Npm package

Configuration for publishing a npm package

## Minimum

```ts
// tsdown.config.ts
import { defineConfig } from "tsdown"

export default defineConfig({
  entry: "src/index.ts",
  format: ["cjs", "esm"],
})
```

## React package

```ts
// tsdown.config.ts
import { defineConfig } from "tsdown"

export default defineConfig({
  clean: true,
  dts: {
    sourcemap: true,
  },
  entry: "src/index.ts",
  external: ["react", "react-dom"],
  format: ["cjs", "esm"],
  platform: "neutral",
  sourcemap: true,
  treeshake: true,
})
```

### React CSS modules package

```ts
// tsup.config.ts
import { defineConfig } from "tsup"

export default defineConfig({
  clean: true,
  dts: true,
  entry: ["src/index.ts"],
  external: ["react", "react-dom"],
  format: ["cjs", "esm"],
  loader: { ".css": "copy" },
  sourcemap: true,
  splitting: true,
  treeshake: true,
})
```
