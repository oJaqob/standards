# Changelog

Each release lists what a project must change when it updates. Versions follow
Semantic Versioning; while on 0.x, a breaking change bumps the minor number.

## Unreleased

- Adds the `apple-motion` agent skill in `skills/`. Nothing to change in a project; install it with the command in the README.
- `knip.base.json` is removed. Knip has no `extends`, and no project used it.

## v0.3.0

Breaking: new lint errors.

- `noProcessEnv`, `useAwait` and `noEmptyBlockStatements` are errors. Read the
  environment through one module, drop `async` from functions that never
  `await` (or add a `biome-ignore` with the reason where the signature must
  return a promise), and put a comment inside intentionally empty blocks.
- `useConsistentObjectDefinitions` is an error.
- `noMisleadingCharacterClass` is off.
- Test files are exempt from `noProcessEnv`, `useAwait` and
  `noEmptyBlockStatements`.

## v0.2.0

Breaking: stricter TypeScript.

- `strict` adds four flags: `noImplicitOverride`, `noFallthroughCasesInSwitch`,
  `noImplicitReturns` and `noUncheckedSideEffectImports`. Add `override`
  modifiers and return on every path.
- `tsconfig.node.json` targets ES2024.

## v0.1.1

- `tsconfig.bundler.json` no longer sets `types`; each project lists its own.

## v0.1.0

First release: Biome, tsconfig presets, knip base, Renovate preset and the
reusable Gate workflow.
