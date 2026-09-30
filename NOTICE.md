# NOTICE

The `my-skills` plugin **vendors** skills from the upstream projects below.
Each skill remains under its original license and copyright. Full license texts
are in [`licenses/`](licenses/).

Skills are **snapshots** pinned to the commits recorded here — upstream fixes do
not reach this repo automatically. To refresh one, re-copy from its upstream at a
newer commit and update the SHA below.

## Provenance

### obra/superpowers

- **License:** MIT — [`licenses/superpowers-MIT.txt`](licenses/superpowers-MIT.txt)
- **Commit:** `8ca22dba9a94f28898bbce59f2537ff4d87c747d`
- **Upstream path:** `skills/<name>/`
- **Skills vendored (8):** `brainstorming`, `writing-plans`, `executing-plans`, `test-driven-development`, `systematic-debugging`, `verification-before-completion`, `requesting-code-review`, `using-git-worktrees`

### addyosmani/agent-skills

- **License:** MIT — [`licenses/agent-skills-MIT.txt`](licenses/agent-skills-MIT.txt)
- **Commit:** `2686b620fc1fed2e8f60c704839c766b8594c6b6`
- **Upstream path:** `skills/<name>/`
- **Skills vendored (10):** `api-and-interface-design`, `code-review-and-quality`, `security-and-hardening`, `performance-optimization`, `observability-and-instrumentation`, `ci-cd-and-automation`, `git-workflow-and-versioning`, `documentation-and-adrs`, `context-engineering`, `spec-driven-development`

### DietrichGebert/ponytail

- **License:** MIT — [`licenses/ponytail-MIT.txt`](licenses/ponytail-MIT.txt)
- **Commit:** `e3ba2aa6f1e6f0bc4d69eb09c9f0d0a93af56156`
- **Upstream path:** `skills/<name>/`
- **Skills vendored (2):** `ponytail`, `ponytail-review`

### JuliusBrussee/caveman

- **License:** MIT — [`licenses/caveman-MIT.txt`](licenses/caveman-MIT.txt)
- **Commit:** `2fd153c67988e980fb0b2455c90832159a6a5a25`
- **Upstream path:** `skills/<name>/`
- **Skills vendored (4):** `lean-build`, `surgical-patch`, `safe-refactor`, `investigate-first`

### nextlevelbuilder/ui-ux-pro-max-skill

- **License:** MIT — [`licenses/ui-ux-pro-max-MIT.txt`](licenses/ui-ux-pro-max-MIT.txt)
- **Commit:** `09170eec67eefd46a7ae85de61b40c194020f997`
- **Upstream path:** `.claude/skills/<name>/`
- **Skills vendored (2):** `ui-ux-pro-max`, `ui-styling`

### Egonex-AI/Understand-Anything

- **License:** MIT — [`licenses/understand-anything-MIT.txt`](licenses/understand-anything-MIT.txt)
- **Commit:** `b05cc3b20990afca537b4fc0a49b4d7fbdc65bb0`
- **Upstream path:** `understand-anything-plugin/skills/<name>/`
- **Skills vendored (1):** `understand`

### tt-a1i/archify

- **License:** MIT — [`licenses/archify-MIT.txt`](licenses/archify-MIT.txt)
- **Commit:** `d5a1333d7447c866a765adac7d4d062f2f02e4d2`
- **Upstream path:** `archify/`
- **Skills vendored (1):** `archify`

### pbakaus/impeccable

- **License:** Apache-2.0 — [`licenses/impeccable-Apache-2.0.txt`](licenses/impeccable-Apache-2.0.txt)
- **Commit:** `0d6b47ea19b63afe15e3f93a44d5d9fbbc6fd275`
- **Upstream path:** `.claude/skills/impeccable/`
- **Skills vendored (1):** `impeccable`

### Graphify-Labs/graphify

- **License:** Apache-2.0 — [`licenses/graphify-Apache-2.0.txt`](licenses/graphify-Apache-2.0.txt)
- **Commit:** `1cd9a36c0c57a661d2d2234bc3207e887e1ba104`
- **Upstream path:** `graphify/skill.md (branch v8)`
- **Skills vendored (1):** `graphify`

## Modifications

Apache-2.0 section 4(b) requires stating changes. Changes made to vendored files:

- **`graphify`** — upstream ships the skill as `graphify/skill.md` with its Claude
  reference files at `graphify/skills/claude/references/`. Renamed to `SKILL.md`
  and the references moved alongside it at `skills/graphify/references/` to match
  the standard skill layout. File contents unmodified.
- **`impeccable`** — upstream duplicates one skill across 24 per-agent directories
  (`.claude/`, `.cursor/`, `.gemini/`, …). Only the `.claude/` copy is vendored.
  File contents unmodified.

Changes to MIT-licensed files (no statement required, recorded for completeness):

- **`archify`** — the `test/` directory (3.7 MB) is omitted. All runtime files
  (`bin/`, `references/`, `schemas/`, `examples/`, `assets/`, `renderers/`) are
  vendored intact; the package has no npm dependencies and runs as-is.
- **`ui-ux-pro-max`** — vendored from `.claude/skills/`; the duplicate copies under
  `cli/assets/skills/` are omitted.

## Deliberate exclusions

- **`caveman`** — the `caveman` and `caveman-compress` skills are *not* vendored.
  They depend on caveman's engine/proxy, which is licensed **BSL-1.1**, not MIT.
  Only the standalone MIT methodology skills are included.
- **`ComposioHQ/awesome-claude-skills`** — excluded entirely. It has **no LICENSE
  file**, so no redistribution is granted, and it is a curated list of links to
  other projects rather than a coherent skill pack.
