# mediblt

**M**y **e**very**d**ays **i**s **b**e **l**ike **t**his: small [Claude Code](https://claude.com/claude-code) skills I actually use every day.

## Install

```
/plugin marketplace add GallowBell/mediblt
/plugin install commit-msg@mediblt
```

## Skills

| Plugin | What it does |
|---|---|
| `commit-msg` | Reads your staged diff and writes a Conventional Commit message in your repo's style. Ask "write a commit message" or "commit this". |

## Add a skill

1. Create `plugins/<name>/.claude-plugin/plugin.json` and `plugins/<name>/skills/<name>/SKILL.md`.
2. Add an entry to `.claude-plugin/marketplace.json`.
3. Run `claude plugin validate .`
