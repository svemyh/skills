---
name: stark-lime-ui
description: High-contrast dark UI, sharp geometry, single electric lime accent — brand-neutral; no third-party mark required.
---

# Stark lime — high-contrast industrial / product UI

When building interfaces that should feel **mechanical, confident, and minimal** with **sharp geometry** and a **single electric accent** on near-black, apply these constraints. This is a **simplified** UI kit; public sites in this category often add WebGL, video, and heavy motion — use this document for **tokens, type, and surface rules** unless the user explicitly wants a full cinematic build.

## How to use

- `/stark-lime-ui` — apply these UI constraints in this session.
- `/stark-lime-ui <file>` — review the file for violations, contrast, and structure; list fixes.
- The website-agent runtime also embeds this as an alternate to the default enterprise baseline.

Use this for "mission", hardware, dark-mode product, and high-end B2B marketing where **one** accent color stands out. **Never** use the signature lime on light backgrounds for small text or body.

## Design system

### Colors

**Core palette**

```css
/* Backgrounds */
--bg-black: #000000;        /* Pure black — dark mode primary */
--bg-dark: #1a1a1a;         /* Near black — dark mode secondary */
--bg-warm: #f5f3ef;         /* Warm off-white — light mode primary */
--bg-white: #ffffff;        /* Pure white — cards, inputs */

/* Text */
--text-primary: #010101;    /* Near black */
--text-inverse: #ffffff;    /* White on dark */
--text-muted: #666666;     /* Secondary text */
--text-subtle: #999999;    /* Tertiary text */

/* Brand accent */
--accent-lime: #DFF140;      /* Signature lime — primary accent */
--accent-lime-hover: #c8d93a;

/* Semantic */
--color-error: #FF3535;
--color-error-bg: #fef2f2;
--color-success: #16a34a;
--color-success-bg: #f0fdf4;
--color-info: #2563eb;
--color-info-bg: #eff6ff;
--color-warning: #f59e0b;
--color-warning-bg: #fffbeb;

/* Borders */
--border-light: #e5e5e5;
--border-default: #ddd;
--border-dark: #333333;
```

**Tailwind (example namespaced group)**

```js
colors: {
  stark: {
    black: '#000000',
    dark: '#1a1a1a',
    warm: '#f5f3ef',
    lime: '#DFF140',
    'lime-hover': '#c8d93a',
  }
}
```

**Usage**

- Use `--accent-lime` **sparingly** — one accent per view
- Dark mode: `--bg-black` background, `--accent-lime` for primary CTAs
- Light mode: `--bg-warm` background, `--text-primary` for primary actions (not lime on light for body text)
- **NEVER** use lime on light backgrounds for body or small type (poor contrast)
- Reserve `--color-error` for destructive actions

### Typography

- Default: `'Helvetica Neue', Helvetica, Arial, sans-serif` (or a **wide grotesk** in the same family if you need a closer match to dense marketing sites)
- Base: `15px`, weight `400`, line-height `1.5`
- Headers: `font-weight: 400` (not bold) for the classic look
- Labels: `11px`, `uppercase`, `letter-spacing: 0.05em`, `color: var(--text-muted)`
- Hero headings: `48px`, `font-weight: 400`, `line-height: 1.1`
- Navigation / header: `14px`, `uppercase`, `letter-spacing: 0.1em`
- On some public sites, `html` font size is ~14px up to a breakpoint, then a fluid `calc` — data-dense, responsive scale. Match if emulating "live" density.

### Spacing

- Cards: `padding: 32px`
- Main: `padding: 48px`, `max-width: 1200px`
- Header: `padding: 24px 48px`
- Form fields: `margin-top: 16px` between fields

### Components

**Cards:** `background: #ffffff` (in light), **no** borders, `border-radius: 0`, **no** box shadows in the minimal treatment.

**Buttons (light typical):** dark fill, inverse text, `1px` border, `12px 24px` padding, `border-radius: 0`, `font-weight: 400`, hover `opacity: 0.85`, disabled `opacity: 0.5`.

**Inputs:** `10px 12px` padding, `1px solid #ddd`, `border-radius: 0`, focus `border-color: var(--text-primary)` without an ugly default outline (use focus-visible pattern).

**Method / API badges (optional):** `font-family: monospace`, `11px`, `uppercase`, `letter-spacing: 0.05em`, `4px 8px` padding, semantic background/text pairs for POST/GET if applicable.

**Code or response blocks:** `background: var(--bg-warm)`, monospace, `12px` font size, semantic tints for error/success when needed.

## Stack (engineering)

- Prefer Tailwind defaults unless custom values already exist
- Use `motion/react` (or the project’s motion package) when JS animation is required; micro-entrance tools like `tw-animate-css` are common for polish
- Use a `cn` utility (`clsx` + `tailwind-merge`) for class logic

## Primitives and accessibility

- Use accessible component primitives (Base UI, React Aria, Radix, or what the project already has)
- Do not mix primitive systems on one surface
- `aria-label` on icon-only buttons
- `AlertDialog` (or equivalent) for destructive actions
- Use structural skeletons for loading; avoid `h-screen` — use `h-dvh`; respect `safe-area-inset` for fixed elements
- Do not block paste in inputs
- Do not hand-roll full keyboard or focus models on top of half-built primitives

## Animation

- **Do not** add animation unless requested or necessary for state
- Animate **transform** and **opacity** only; avoid animating **layout** properties (`width`, `height`, `margin`, `padding`, etc.) for interaction feedback
- Ease-out on entrance; cap interaction feedback at **~200ms**; respect **`prefers-reduced-motion`**

## Layout and type utilities

- `text-balance` on headings, `text-pretty` on body where supported
- `tabular-nums` for numeric data
- Fixed `z-index` scale, no arbitrary `z-[9999]` unless documented
- Avoid huge `blur()` or `backdrop-filter` animations

## This aesthetic — what to enforce

**Shape and surface**

- **No** border-radius in the strict variant — **sharp corners**
- **No** card shadows in the flat variant; **no** multi-stop gradients; **no** glow; **no** random purple or rainbow accents

**Color usage**

- Light: `--bg-warm` with dark text/actions
- Dark: `--bg-black` with **lime** primary CTA; **one** strong accent per view; semantic reds/greens for errors/success

**States**

- Empty: one clear next action
- Error: red on light red field; success: green on light green; disabled: `0.5` opacity, `not-allowed` cursor

## Reference to full-site builds

- Many public pages in this category add smooth scroll, **Three/WebGL** hero stages, and video — this skill is a **UI kit**; if the user wants a **"full cinematic"** page, align tokens and fonts with this doc, then add motion/canvas per task.

**Disclaimer:** tokens align with a common "black stage + lime + grotesk" public marketing look; re-check in DevTools for strict pixel work.
