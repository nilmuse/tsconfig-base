# @nilmuse/tsconfig-base

Shared base `tsconfig.json` for the `nilmuse` npm portfolio. Encodes the TypeScript
compiler options fixed by the build standard (`assembly.md` §7) so packages inherit them
instead of copy-pasting.

---

## Installation

```bash
npm install -D @nilmuse/tsconfig-base
```

---

## Usage

In a package `tsconfig.json`:

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

The base sets only the shared compiler options (`target`, `module`, `moduleResolution`,
`strict`, `isolatedModules`, `verbatimModuleSyntax`, `lib`, `skipLibCheck`, etc.). Per-package
concerns — `rootDir`/`outDir`, `include`, declaration emit, and the opt-in
`noUnusedLocals`/`noUnusedParameters` (§7) — stay in the package's own config.

The companion `tsconfig.build.json` (public `src` only) is defined per package and extends
the package `tsconfig.json`:

```json
{
  "extends": "./tsconfig.json",
  "compilerOptions": { "rootDir": "src", "declarationMap": false },
  "include": ["src"]
}
```

---

## License

MIT
