# agent-skills

A collection of OpenClaw skills. Source of truth lives here; published copies
go to [ClawHub](https://clawhub.ai).

## Skills

| Skill | Description |
| ----- | ----------- |
| [arr-cli](./skills/arr-cli) | Read-only CLI for Jellyfin / Radarr / Sonarr / Maintainerr / Seerr |
| [forktree](./skills/forktree) | Stdlib-only Python CLI wrapping `git worktree` with safety pre-flights and a strict stdout/stderr contract |

## Layout

```
agent-skills/
  skills/
    <skill-name>/
      SKILL.md
```

Each skill lives in its own folder under `skills/<skill-name>/` with a
`SKILL.md` at minimum. Auxiliary files (`scripts/`, `references/`,
`assets/`) belong alongside it.

## Adding a new skill

1. Create `skills/<new-skill-name>/SKILL.md`
2. Add a row to the skills table above
3. Commit + push; publish via `clawhub skill publish ./skills/<new-skill-name>`

## Publish

The repo is the source of truth; published copies go to ClawHub.

```bash
clawhub login                                          # one-time
clawhub skill publish ./skills/arr-cli                 # auto-bump version
clawhub skill publish ./skills/arr-cli --version 0.1.0 # explicit
```
