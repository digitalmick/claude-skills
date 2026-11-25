# claude-skills

A personal [Claude Code](https://claude.com/claude-code) marketplace. One main
plugin with **37 curated skills**, plus an optional creative-writing plugin.

## Install

```
/plugin marketplace add digitalmick/claude-skills
/plugin install my-skills@claude-skills
```

Then restart Claude Code (or run `/reload-plugins`). That's it — all 37 skills
are available. Adding a skill later means committing it here, then running this
in a terminal; there is never a per-skill install:

```
claude plugin marketplace update claude-skills
claude plugin update my-skills@claude-skills
```

## What's inside

Skills are curated, not exhaustive: one skill per job, no duplicates, nothing
that needs a paid backend. They come from nine upstream projects — see
[NOTICE.md](NOTICE.md) for exact provenance and commit pins.

### Workflow (15) — from [obra/superpowers](https://github.com/obra/superpowers)
`brainstorming` · `writing-plans` · `executing-plans` · `test-driven-development`
· `systematic-debugging` · `verification-before-completion` ·
`requesting-code-review` · `using-git-worktrees` · `subagent-driven-development`
· `dispatching-parallel-agents` · `receiving-code-review` ·
`finishing-a-development-branch` · `writing-skills` · `using-superpowers` ·
`diagnosing-superpowers`

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

## Optional: creative-writing-skills

[haowjy/creative-writing-skills](https://github.com/haowjy/creative-writing-skills)
— 25 skills and 17 agents for fiction projects. Start with the `muse` agent.
It is a **separate plugin** that this marketplace *links to* at upstream release
`v0.9.11`; nothing is copied into this repo. Install it only in projects where
you write:

```
claude plugin install creative-writing-skills@claude-skills --scope project
```

It is kept separate because its parts reference each other as
`creative-writing-skills:<name>` (that only resolves under its own plugin name),
and because 15 of its parts come from `haowjy/meridian-base`, which has no
license and so can't be vendored here.

## External dependencies

Most skills are pure instructions and need nothing. Two exceptions:

| Skill | Needs | Install |
|---|---|---|
| `graphify` | `graphify` CLI (separate Python package) | `uv tool install graphifyy` or `pipx install graphifyy` |
| `archify` | Node.js | already vendored; zero npm dependencies |
| `understand` | Node.js | already vendored |

## Heads-up: superpowers overlap

All 15 `superpowers` skills are vendored here. If you also have
`superpowers@claude-plugins-official` installed, you will get **two copies** of
`brainstorming`, `test-driven-development`, and the rest. This marketplace is
meant to be the single source: don't install the official plugin alongside it
(`claude plugin uninstall superpowers@claude-plugins-official --scope project`
removes a project-level copy).

`archify` runs a bounded update check when it finishes a diagram and may print
an update notice. It never installs updates itself; refresh it here instead.

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
  skills/<name>/SKILL.md          37 skills
licenses/                         upstream license texts
NOTICE.md                         provenance + modifications
```
