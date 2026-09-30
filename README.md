# claude-skills

A personal [Claude Code](https://claude.com/claude-code) marketplace. One plugin,
**30 curated skills**, one install command.

## Install

```
/plugin marketplace add digitalmick/claude-skills
/plugin install my-skills@claude-skills
```

Then restart Claude Code (or run `/reload-plugins`). That's it — all 30 skills
are available. Adding a skill later means committing it here and running
`/plugin update`; there is never a per-skill install.

## What's inside

Skills are curated, not exhaustive: one skill per job, no duplicates, nothing
that needs a paid backend. They come from nine upstream projects — see
[NOTICE.md](NOTICE.md) for exact provenance and commit pins.

### Workflow (8) — from [obra/superpowers](https://github.com/obra/superpowers)
`brainstorming` · `writing-plans` · `executing-plans` · `test-driven-development`
· `systematic-debugging` · `verification-before-completion` ·
`requesting-code-review` · `using-git-worktrees`

### Engineering practice (10) — from [addyosmani/agent-skills](https://github.com/addyosmani/agent-skills)
`api-and-interface-design` · `code-review-and-quality` · `security-and-hardening`
· `performance-optimization` · `observability-and-instrumentation` ·
`ci-cd-and-automation` · `git-workflow-and-versioning` · `documentation-and-adrs`
· `context-engineering` · `spec-driven-development`

### Lean / simplicity (6)
`ponytail` · `ponytail-review` — [DietrichGebert/ponytail](https://github.com/DietrichGebert/ponytail)
`lean-build` · `surgical-patch` · `safe-refactor` · `investigate-first` — [JuliusBrussee/caveman](https://github.com/JuliusBrussee/caveman)

### Design (3)
`impeccable` — [pbakaus/impeccable](https://github.com/pbakaus/impeccable)
`ui-ux-pro-max` · `ui-styling` — [nextlevelbuilder/ui-ux-pro-max-skill](https://github.com/nextlevelbuilder/ui-ux-pro-max-skill)

### Comprehension / diagrams (3)
`archify` — [tt-a1i/archify](https://github.com/tt-a1i/archify) · self-contained, needs Node
`graphify` — [Graphify-Labs/graphify](https://github.com/Graphify-Labs/graphify) · **requires the CLI** (below)
`understand` — [Egonex-AI/Understand-Anything](https://github.com/Egonex-AI/Understand-Anything)

## External dependencies

Most skills are pure instructions and need nothing. Two exceptions:

| Skill | Needs | Install |
|---|---|---|
| `graphify` | `graphify` CLI (separate Python package) | `uv tool install graphifyy` or `pipx install graphifyy` |
| `archify` | Node.js | already vendored; zero npm dependencies |
| `understand` | Node.js | already vendored |

## Heads-up: superpowers overlap

8 of these skills are vendored from `superpowers`. If you also have
`superpowers@claude-plugins-official` installed, you will get **two copies** of
`brainstorming`, `test-driven-development`, and the rest. Pick one source —
either uninstall the official plugin, or drop those 8 directories from here.

## Licensing

Every vendored skill keeps its original license (MIT or Apache-2.0). Full texts
are in [`licenses/`](licenses/); per-skill provenance, commit pins, and a
statement of modifications are in [NOTICE.md](NOTICE.md).

Skills are **snapshots** — upstream fixes do not flow here automatically.
NOTICE.md records the exact commit each one came from so refreshing is a
deliberate step.

## Layout

```
.claude-plugin/marketplace.json   marketplace manifest
plugins/my-skills/
  .claude-plugin/plugin.json      plugin manifest
  skills/<name>/SKILL.md          30 skills
licenses/                         upstream license texts
NOTICE.md                         provenance + modifications
```
