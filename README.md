# standards

Shared Biome, TypeScript, Renovate and CI configuration for TypeScript projects. Public so projects can install it without credentials.

Install, pinned to a tag so Renovate can propose upgrades:

```
pnpm add -D github:oJaqob/standards#v0.3.0
```

| What | How a project uses it |
| --- | --- |
| Biome | `biome.json`: `{ "extends": ["@ojaqob/standards/biome.json"] }` plus its own `files` and rule overrides |
| TypeScript | `tsconfig.json`: `{ "extends": "@ojaqob/standards/tsconfig.node.json" }` or `tsconfig.bundler.json`; `tsconfig.strict.json` is the shared base |
| Renovate | `renovate.json`: `"extends": ["github>oJaqob/standards"]` (`default.json`); project rules go after it |
| CI | `uses: oJaqob/standards/.github/workflows/gate.yml@v0.3.0` for the Gate job |

| Agent skills | `pnpm dlx skills add oJaqob/standards -s apple-motion -a claude-code -y`: springs instead of timed animations, and Apple's rubber band (`skills/apple-motion`) |

Not shared on purpose: the CI setup action (it differs per project), `SECURITY.md`,
`CODE_OF_CONDUCT.md` and `AGENTS.md` (they name the product), `.node-version`,
and each project's workspace and entry-point maps.

## Changing a rule

Edit it here, tag a new version, and let Renovate open the bump in each project.
A change to Biome's formatting reformats every project, so run the formatter
in each one before merging the bump.
