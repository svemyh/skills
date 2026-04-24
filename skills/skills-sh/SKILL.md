---
name: skills-sh
description: How public agent skills are laid out on GitHub, installed with npx, and exposed on skills.sh (single-repo vs monorepo).
---

# Public agent skills (GitHub + skills.sh)

Use this when authoring or wiring **install** docs for Cursor / Claude Code / Codex style skills.

## Are skills always one repo per skill?

**No.** Two common patterns:

1. **One skill per public repo** — e.g. `adisinghstudent/anduril` with `skills/anduril/SKILL.md` (or a single `SKILL.md` at root in some tools). Install is often:
   ```bash
   npx add-skill owner/repo
   ```
2. **One public monorepo, many skills** — e.g. [Aradotso/trending-skills](https://github.com/Aradotso/trending-skills) with `skills/<slug>/SKILL.md` for each. Install one skill with:
   ```bash
   npx skills add Aradotso/trending-skills --skill <slug>
   ```
   (Exact CLI flags depend on the `skills` / `add-skill` version; check the package README if a command fails.)

## skills.sh install URL

For a monorepo `owner/skills` and skill slug `my-skill`, the usual page pattern is:

`https://skills.sh/owner/skills/my-skill`

Example: `https://skills.sh/svemyh/skills/chip-city-cookies`

## What must be public?

- The **GitHub repository** (or a fork) must be **public** for anonymous install and for skills.sh-style discovery.
- Each skill is typically a folder: `skills/<name>/SKILL.md` with YAML frontmatter:
  - `name` (slug, often matches folder)
  - `description` (short, for skill pickers)

## Optional

- Root `README.md` listing each skill and install lines.
- `LICENSE` (MIT is common) at repo root; if you **vendor** another project’s `SKILL.md`, keep a `NOTICE` or section crediting upstream and their license.

## What does not “submit” you to a directory automatically

Curated lists (e.g. “trending”) are often **generated** or hand-maintained elsewhere. Publishing a public repo + correct layout is the baseline; **indexing** on third-party roundups is separate.

When helping a user **publish**, prefer: public repo, clear `README`, stable `main`, and one install command that you have verified.
