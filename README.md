# @nilmuse/tsconfig-base

Shared TypeScript compiler settings for the `nilmuse` npm packages. Extend the base and keep
source paths and build-specific settings in your project's config.

[![npm](https://img.shields.io/npm/v/@nilmuse/tsconfig-base.svg?colorB=brightgreen)](https://www.npmjs.com/package/@nilmuse/tsconfig-base)
[![NPM Downloads](https://img.shields.io/npm/dm/@nilmuse/tsconfig-base.svg?style=flat)](https://www.npmjs.com/package/@nilmuse/tsconfig-base)

---

## Installation

```bash
npm install -D @nilmuse/tsconfig-base
```

## Quick start

Create `tsconfig.json` in your project. Adjust `include` to match your source and config files:

```json
{
  "extends": "@nilmuse/tsconfig-base/tsconfig.json",
  "compilerOptions": {
    "rootDir": ".",
    "outDir": "dist"
  },
  "include": ["src", "tsdown.config.ts"]
}
```

TypeScript inherits the shared compiler options and uses the paths from your own config.

## Configuration

The base targets ES2022, uses ESNext modules with `bundler` resolution, and includes the
ES2022, DOM, and DOM.Iterable libraries. It enables strict checking, `isolatedModules`,
`verbatimModuleSyntax`, `esModuleInterop`, `forceConsistentCasingInFileNames`, and
`resolveJsonModule`, with `skipLibCheck: true`.

Set `rootDir`, `outDir`, `include`, and declaration output in your project's config.
`noUnusedLocals` and `noUnusedParameters` are opt-in settings.

### Build config

For a build that reads source files from `src`, add `tsconfig.build.json` alongside
`tsconfig.json`:

```json
{
  "extends": "./tsconfig.json",
  "compilerOptions": { "rootDir": "src", "declarationMap": false },
  "include": ["src"]
}
```

## License

MIT
