---
name: skills-sh
description: Publish skills on GitHub, install and manage them with the skills CLI, and understand how skills.sh relates (discovery + install pages; not a separate registry API).
---

# Agent skills: GitHub, `npx skills`, and skills.sh

Use this when **authoring**, **publishing**, **installing**, or **managing** `SKILL.md` skills for Cursor, Claude Code, OpenClaw, Codex, and other supported agents.

## What skills.sh is (and is not)

- **[skills.sh](https://skills.sh/)** is a **discovery** and **documentation** surface: install pages like `https://skills.sh/<owner>/<repo>/<skill-slug>`, often **after** a public GitHub repo is indexed. There is **no** separate “upload to skills.sh” API in normal workflows — **publishing = public GitHub + correct layout + `git push`**.
- **New or updated repos** may show **404** on skills.sh for a while until the site re-indexes. **Install still works** via `npx skills add owner/repo` (it clones from GitHub).
- Curated lists (e.g. “trending”) are **separate** and may be auto-generated or hand-maintained — not the same as “being on skills.sh”.

## Repo layout (required for the `skills` CLI)

- **Monorepo:** `skills/<slug>/SKILL.md` at the root of a public repo. Each folder is one skill.
- **YAML frontmatter** at the top of `SKILL.md`:
  - `name` — usually matches the folder slug
  - `description` — one line, for pickers and search
- **Root `README.md`:** list each skill and how to install (helps humans; not always required for the CLI).
- **License:** e.g. MIT at repo root; if you **vendor** someone else’s `SKILL.md`, add a `NOTICE` or credit in README.

**One skill per repo** also works: same `skills/<name>/SKILL.md` tree, or some tools accept a single package (see **add-skill** below).

## Publish (ship to the world)

1. Put the skill(s) in a **public** GitHub repository (e.g. `github.com/you/skills`).
2. Commit and **push** to `main` (or your default branch).
3. Optional: set repo description, topics, and a clear README.
4. **Do not** wait for skills.sh to go green before sharing — share the **GitHub URL** and the **install command** below.

## Install (consumers and your other machines)

Primary tool: the **`skills`** CLI (see `npx skills --help`).

```bash
# Interactive: pick which skills from the repo
npx skills add owner/repo

# Install all skills from a monorepo, globally, no prompts (typical for “install everything”)
npx skills add owner/repo --yes --global
# Shorthand for “all skills, all agents, yes”:
npx skills add owner/repo --all
```

**Single skill** from a monorepo (flag is `--skill` / `-s`):

```bash
npx skills add owner/repo --skill my-skill --yes --global
```

**Only certain agents** (e.g. Cursor + Claude Code):

```bash
npx skills add owner/repo --agent claude-code cursor --skill my-skill --yes -g
```

**List what’s in a repo without installing:**

```bash
npx skills add owner/repo --list
```

### Other installer: `add-skill`

Some docs use **one-repo-one-skill** style:

```bash
npx add-skill owner/single-skill-repo
```

That is a **different** package/flow from `npx skills add`. Prefer **`npx skills add`** for monorepos and for the full **list / update / remove** experience.

## Where files land (global install)

- Global installs typically live under **`~/.agents/skills/<skill-name>/`**, with links into each agent’s expected config (e.g. Cursor, Claude Code, OpenClaw) — the installer prints a summary.
- **Project** installs: use the same `skills add` **without** `-g` from inside a project (see CLI help; may use a lockfile / project scope).

## Manage: list, update, remove

```bash
# List installed (global)
npx skills list --global
# or
npx skills ls -g

# Update all global skills to latest from source repos
npx skills update -g -y

# Update one
npx skills update my-skill -g -y

# Remove (interactive or by name)
npx skills remove my-skill -g -y
```

**Search** public skills (interactive or query):

```bash
npx skills find
npx skills find typescript
```

**Scaffold a new skill** (local file layout):

```bash
npx skills init my-skill
```

## skills.sh URL pattern (after indexing)

For repo `owner/repo` and skill slug `my-skill`:

`https://skills.sh/owner/repo/my-skill`

Example: `https://skills.sh/svemyh/skills/legora`  
If that returns **404**, the repo is still **installable** from GitHub.

## When helping users “get on skills.sh”

1. **Ship** a public repo with valid `skills/<name>/SKILL.md` files.  
2. **Verify** install: `npx skills add owner/repo -s <slug> -y -g` (or `--all`).  
3. **Expect** skills.sh pages to appear **on delay**; do not block on 404.  
4. For **trending**-style lists, those are **not** the same as publishing — follow each list’s own rules if any.

## Anti-patterns

- **Private** repo: others cannot `npx skills add` without auth; discovery breaks.  
- **Missing** frontmatter `name` / `description` on `SKILL.md`.  
- Telling users to “register on skills.sh” as if it were npm — it is not.

---

**This file is a living cheat sheet** — if `npx skills --help` changes, prefer the installed CLI for exact flags.
