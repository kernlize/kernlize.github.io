# API reference

The API reference is generated from source JSDoc by TypeDoc 0.28 with `entryPointStrategy: packages` over the four workspaces in `typedoc.json`. It is written to `docs/api/` and served next to this site at `/docs/api/`.

```bash
pnpm docs:api
```

Do not edit the generated files. Fix the JSDoc in `packages/*/src` and rerun. `treatWarningsAsErrors` is on, so an export without documentation, a broken `{@link}` or a missing git remote fails the build.

## Modules

| Package | Module page |
| --- | --- |
| `@kernl/guard` | [`_kernl_guard`](https://kernlize.github.io/docs/api/modules/_kernl_guard.html) |
| `@kernl/messaging` | [`_kernl_messaging`](https://kernlize.github.io/docs/api/modules/_kernl_messaging.html) |
| `@kernl/bridges` | [`_kernl_bridges`](https://kernlize.github.io/docs/api/modules/_kernl_bridges.html) |
| `@kernl/core` | [`_kernl_core`](https://kernlize.github.io/docs/api/modules/_kernl_core.html) |

The [index page](https://kernlize.github.io/docs/api/index.html) lists all four, and the [hierarchy page](https://kernlize.github.io/docs/api/hierarchy.html) shows type relationships across them.

## How to read it

- Each module page lists its exports by kind: interfaces, type aliases, functions, variables. Every entry has at least one `@example`.
- Reasons in thrown errors are documented as string literals (`denied:…`, `invalid:…`, `unavailable:…`) on the function that throws them.
- Types imported from `@kehto/*` or `@napplet/core` are linked to their names but not expanded; `excludeExternals` keeps the reference to kernl's own surface.
- The reference is HTML only. It has no Markdown twin and is not included in `llms-full.txt`; the [package pages](https://kernlize.github.io/docs/packages/index.md) carry the export lists in Markdown for agents.

## Audit

`scripts/audit-docs.mjs` asserts that `docs/api/modules/_kernl_<package>.html` exists for every `packages/*/package.json`, that each package page links to it, and that the built docs carry their Markdown twins. It runs as part of `pnpm docs:check`.
