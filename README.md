# Agent skills (multi-skill repo)

`SKILL.md` files for **Cursor, Codex, Claude Code**, and other agents that load the skills format.

**Layout:** one folder per skill under `skills/<slug>/SKILL.md`.

## Install

Interactive picker (point at this repository’s URL when published):

```bash
npx skills add <org-or-user>/<repo>
```

Install one skill:

```bash
npx skills add <org-or-user>/<repo> --skill agentic-oriented-programming
npx skills add <org-or-user>/<repo> --skill enterprise-boardroom
npx skills add <org-or-user>/<repo> --skill stark-lime-ui
npx skills add <org-or-user>/<repo> --skill warm-pastel-bakery
npx skills add <org-or-user>/<repo> --skill skills-sh
```

## Visual design (brand-neutral)

These are **aesthetic baselines** only — no tie to any specific company or trademark.

| Slug | When to use |
| --- | --- |
| `enterprise-boardroom` | **Default** for professional / B2B / institutional marketing (hierarchy, stoneware neutrals, compliance-friendly). |
| `stark-lime-ui` | Dark stage, sharp geometry, single **lime** accent, minimal industrial product UI. |
| `warm-pastel-bakery` | Cream paper, rose / mint / powder, soft radii, warm retail and food DTC. |

The **website-agent** service (in the repo that consumes this submodule) embeds all three in the system prompt, with **enterprise-boardroom** as the default when the user has not specified another vibe.

## Other skills

| Slug | Role |
| --- | --- |
| `agentic-oriented-programming` | Architecture doctrine for codebases edited by agents (boundaries, invariants, narrow interfaces). |
| `skills-sh` | How multi-skill repos and the public skills index fit together. |

## License

MIT. Third-party text used as a **starting point** for one skill is noted in [NOTICE](NOTICE) with upstream license (MIT).
