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
- **Commit:** `22f0b463e7a5e579904dd6211a520321035526f7`
- **Upstream path:** `skills/<name>/`
- **Skills vendored (15, all of upstream's skills):** `brainstorming`, `writing-plans`, `executing-plans`, `test-driven-development`, `systematic-debugging`, `verification-before-completion`, `requesting-code-review`, `using-git-worktrees`, `subagent-driven-development`, `dispatching-parallel-agents`, `receiving-code-review`, `finishing-a-development-branch`, `writing-skills`, `using-superpowers`, `diagnosing-superpowers`

### addyosmani/agent-skills

- **License:** MIT — [`licenses/agent-skills-MIT.txt`](licenses/agent-skills-MIT.txt)
- **Commit:** `8c99fa36d90068c82d547f7c12a9d67a3e95f4ee`
- **Upstream path:** `skills/<name>/`
- **Skills vendored (10):** `api-and-interface-design`, `code-review-and-quality`, `security-and-hardening`, `performance-optimization`, `observability-and-instrumentation`, `ci-cd-and-automation`, `git-workflow-and-versioning`, `documentation-and-adrs`, `context-engineering`, `spec-driven-development`

### DietrichGebert/ponytail

- **License:** MIT — [`licenses/ponytail-MIT.txt`](licenses/ponytail-MIT.txt)
- **Commit:** `96608e078b2d5ea607c5c3b8b5a54d1c1fba6846`
- **Upstream path:** `skills/<name>/`
- **Skills vendored (2):** `ponytail`, `ponytail-review`

### JuliusBrussee/caveman

- **License:** MIT — [`licenses/caveman-MIT.txt`](licenses/caveman-MIT.txt)
- **Commit:** `2fd153c67988e980fb0b2455c90832159a6a5a25`
- **Note:** upstream has since relicensed to Apache-2.0. These four skills are
  byte-identical at upstream `a192894723a8f47e7f504c7b5041967ff1f18e55`
  (checked 2026-11-20), so they stay pinned to the MIT-licensed commit.
- **Upstream path:** `skills/<name>/`
- **Skills vendored (4):** `lean-build`, `surgical-patch`, `safe-refactor`, `investigate-first`

### nextlevelbuilder/ui-ux-pro-max-skill

- **License:** MIT — [`licenses/ui-ux-pro-max-MIT.txt`](licenses/ui-ux-pro-max-MIT.txt)
- **Commit:** `2de1134dc4d1cfe112934611ae5803ae17a1bd7e`
- **Upstream path:** `.claude/skills/<name>/`
- **Skills vendored (2):** `ui-ux-pro-max`, `ui-styling`

### Egonex-AI/Understand-Anything

- **License:** MIT — [`licenses/understand-anything-MIT.txt`](licenses/understand-anything-MIT.txt)
- **Commit:** `bb70fdb0489f8839ce55bf99dae0125ea067f712`
- **Upstream path:** `understand-anything-plugin/skills/<name>/`
- **Skills vendored (1):** `understand`

### tt-a1i/archify

- **License:** Apache-2.0 — [`licenses/archify-Apache-2.0.txt`](licenses/archify-Apache-2.0.txt).
  Upstream relicensed from MIT; its historical MIT notice is kept in
  [`licenses/archify-MIT.txt`](licenses/archify-MIT.txt) and in the vendored
  `LICENSE-MIT`. Upstream's `NOTICE` and `THIRD_PARTY_NOTICES.md` ship inside
  `skills/archify/` as Apache-2.0 section 4(d) requires.
- **Commit:** `44781293f38728baf04dbad33ce1a0cef8c39cca`
- **Upstream path:** `archify/`
- **Skills vendored (1):** `archify`

### pbakaus/impeccable

- **License:** Apache-2.0 — [`licenses/impeccable-Apache-2.0.txt`](licenses/impeccable-Apache-2.0.txt)
- **Commit:** `b49177d32788f2dc585c42831d845dacf1ebed2c`
- **Upstream path:** `.claude/skills/impeccable/`
- **Skills vendored (1):** `impeccable`

### Graphify-Labs/graphify

- **License:** Apache-2.0 — [`licenses/graphify-Apache-2.0.txt`](licenses/graphify-Apache-2.0.txt)
- **Commit:** `f51d46c63d6280a5906277b29b118dc2dd119991`
- **Upstream path:** `graphify/skill.md (branch v8)`
- **Skills vendored (1):** `graphify`

## Linked plugins (not vendored)

These are listed in `marketplace.json` but fetched from upstream at install
time. No files from them are redistributed in this repo.

### haowjy/creative-writing-skills

- **License:** Apache-2.0 (upstream `LICENSE`). Its bundled `meridian-base`
  parts (10 skills, 5 agents) come from `haowjy/meridian-base`, which has no
  license file — one reason this plugin is linked rather than vendored.
- **Source:** `git-subdir` at `plugin/claude/`, tag `v0.9.11`, commit
  `8d39b73661f4413984eef52b1d816e3788c979d9`. To move it forward, update `ref`,
  `sha`, and `version` in `.claude-plugin/marketplace.json`.
- **Contents at that commit:** 25 skills, 17 agents.

## Modifications

Apache-2.0 section 4(b) requires stating changes. Changes made to vendored files:

- **`graphify`** — upstream ships the skill as `graphify/skill.md` with its Claude
  reference files at `graphify/skills/claude/references/`. Renamed to `SKILL.md`
  and the references moved alongside it at `skills/graphify/references/` to match
  the standard skill layout. File contents unmodified.
- **`impeccable`** — upstream duplicates one skill across 24 per-agent directories
  (`.claude/`, `.cursor/`, `.gemini/`, …). Only the `.claude/` copy is vendored.
  File contents unmodified.

- **`archify`** — upstream's `archify/` package directory is vendored intact
  (it no longer contains `test/`). File contents unmodified. It has no runtime
  npm dependencies (only `ajv` and `simple-icons` as devDependencies).

Changes to MIT-licensed files (no statement required, recorded for completeness):

- **`ui-ux-pro-max`** — vendored from `.claude/skills/`; the duplicate copies under
  `cli/assets/skills/` are omitted.

## Deliberate exclusions

- **`superpowers` hooks** — upstream's `hooks/` (a SessionStart hook that injects
  `using-superpowers` into every session) is *not* vendored. `my-skills` is
  installed at user scope, so it would run in every project; `using-superpowers`
  is available as a normal skill instead.
- **`caveman`** — the `caveman` and `caveman-compress` skills are *not* vendored.
  They depend on caveman's engine/proxy, which is licensed **BSL-1.1**, not MIT.
  Only the standalone MIT methodology skills are included.
- **`ComposioHQ/awesome-claude-skills`** — excluded entirely. It has **no LICENSE
  file**, so no redistribution is granted, and it is a curated list of links to
  other projects rather than a coherent skill pack.
