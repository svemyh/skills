# svemyh/skills

Public monorepo of [agent skills](https://skills.sh) for Cursor, Codex, Claude Code, and other `SKILL.md`-compatible agents.

**Layout:** one GitHub repo, each skill in `skills/<name>/SKILL.md`. This is the same **multi-skill** pattern as [Aradotso/trending-skills](https://github.com/Aradotso/trending-skills) — a skill does **not** have to be its own repository.

## Install (pick one skill)

```bash
# Interactive: choose from this repo
npx skills add svemyh/skills
```

Or install a specific skill:

```bash
npx skills add svemyh/skills --skill agentic-oriented-programming
npx skills add svemyh/skills --skill chip-city-cookies
npx skills add svemyh/skills --skill anduril
npx skills add svemyh/skills --skill skills-sh
```

## skills.sh install pages

| Skill | Page |
| --- | --- |
| `agentic-oriented-programming` | [skills.sh/…/agentic-oriented-programming](https://skills.sh/svemyh/skills/agentic-oriented-programming) |
| `chip-city-cookies` | [skills.sh/…/chip-city-cookies](https://skills.sh/svemyh/skills/chip-city-cookies) |
| `anduril` | [skills.sh/…/anduril](https://skills.sh/svemyh/skills/anduril) |
| `skills-sh` | [skills.sh/…/skills-sh](https://skills.sh/svemyh/skills/skills-sh) |

## Included skills

- **`agentic-oriented-programming`** — coding doctrine for agent-era software: locally simple, globally constrained, narrow boundaries.
- **`chip-city-cookies`** — UI constraints aligned with [chipcitycookies.com](https://chipcitycookies.com/) (warm bakery palette, marketing patterns).
- **`anduril`** — Anduril-style product UI constraints (vendored from [adisinghstudent/anduril](https://github.com/adisinghstudent/anduril), MIT; see [NOTICE](NOTICE)). You can also `npx add-skill adisinghstudent/anduril` for the upstream single-repo install.
- **`skills-sh`** — how GitHub + `npx` + [skills.sh](https://skills.sh) fit together (monorepo vs one skill per repo).

## License

MIT. The **anduril** skill text is third-party (MIT) — [NOTICE](NOTICE).
