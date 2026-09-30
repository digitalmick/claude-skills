# my-skills

30 curated skills for Claude Code, vendored from nine upstream projects.

```
/plugin marketplace add digitalmick/claude-skills
/plugin install my-skills@claude-skills
```

Restart Claude Code or run `/reload-plugins` afterwards.

Skills live in `skills/<name>/SKILL.md`. Each is self-contained apart from
`graphify`, which drives a separately installed CLI
(`uv tool install graphifyy`).

For the full skill list, provenance, commit pins, and licensing see the
[repository README](../../README.md) and [NOTICE.md](../../NOTICE.md).
