---
name: chip-city-cookies
description: Opinionated UI constraints for Chip City Cookies web experiences — warm bakery aesthetic aligned with chipcitycookies.com.
---

# Chip City Cookies design system

When invoked, apply these constraints for marketing sites, apps, and landing pages that should feel on-brand for [Chip City Cookies](https://chipcitycookies.com/): warm, indulgent, playful, and “ooey-gooey” without looking cheap or childish.

Reference the live site for copy tone (locations, shipping, catering, weekly flavors, newsletter).

## How to use

- `/chip-city-cookies` — Apply these constraints to UI work in this conversation.
- `/chip-city-cookies <file>` — Review the file for violations, explain why, and suggest concrete fixes.

---

## Design system: Chip City

### Brand voice (copy)

- Friendly, celebratory, slightly nostalgic — not corporate.
- Hero lines can be short and punchy; body copy can mention rotation (e.g. weekly flavors), shipping, and local stores when relevant.
- Use “ooey-gooey” and flavor-forward language sparingly; avoid stacking superlatives.

### Colors

**Core palette** (tune to match production CSS if the site palette shifts)

```css
/* Backgrounds */
--bg-cream: #fbf6f0;        /* warm bakery light */
--bg-sugar: #fff8f2;         /* alt section */
--bg-ink: #1c1410;           /* deep brown-black — footer / strong contrast */
--bg-white: #ffffff;

/* Text */
--text-primary: #1c1410;     /* body on light */
--text-secondary: #5c4a42;
--text-muted: #7d6b62;
--text-on-dark: #fbf6f0;

/* Brand / accent (sprinkle-pink, primary CTAs) */
--accent-pink: #e85a8a;      /* primary button / key links on light */
--accent-pink-hover: #d14a7a;
--accent-sprinkle: #f4a6c1;  /* soft highlights, badges, chips less critical than CTA */

/* “Chocolate” (secondary actions, icon strokes) */
--chocolate: #3d2c26;

/* Semantic */
--color-error: #c42d2d;
--color-error-bg: #fff5f5;
--color-success: #2d6a4f;
--color-success-bg: #edf7f1;

/* Borders (soft, bakery — not sharp tech grey) */
--border-soft: #e8ded4;
--border-warm: #d4c4b8;
```

**Tailwind-style tokens** (if using Tailwind)

```js
colors: {
  chip: {
    cream: '#fbf6f0',
    sugar: '#fff8f2',
    ink: '#1c1410',
    pink: '#e85a8a',
    'pink-hover': '#d14a7a',
    sprinkle: '#f4a6c1',
    chocolate: '#3d2c26',
  }
}
```

**Usage**

- On **light** sections: `cream` / `sugar` backgrounds, `ink` text, `accent-pink` for one primary CTA per viewport where emphasis is needed.
- On **dark** (footers, promos): `ink` or near-black; use `text-on-dark` and `accent-pink` or white-outline buttons; keep contrast **WCAG AA** minimum.
- Avoid Anduril-style **neon/lime** — Chip City is warm and confectionery, not defense-tech.

### Typography

- Prefer a **rounded humanist** stack for marketing: system UI rounded feel or `Nunito`, `DM Sans`, `Plus Jakarta Sans` — **only if the project has no brand font**; if the product already loads a font, align with the live site.
- Headings: friendly, **medium** weight (500–600) — not ultra-light like Anduril, not extra-bold poster type unless the art direction explicitly asks.
- **Sentence case** for most UI strings; **title case** for short nav labels is OK.
- Avoid all-caps blocks except small labels (e.g. “NATIONWIDE SHIPPING”) — keep `letter-spacing` subtle (`0.02em`–`0.04em`), not the wide Anduril nav tracking unless matching the reference site.
- Base body: `16px`–`18px` on marketing pages, `line-height` ~1.5–1.6.

### Spacing & layout

- Generous **padding**; cookie photography and whitespace sell the product.
- Content width: `max-width` around **1100px–1200px** for text-heavy sections; let hero and flavor grids breathe.
- Card grids for products: **consistent** gaps (`16px`–`24px`); on mobile, single column with full-width images.

### Shape & surface (Chip City vs. Anduril)

- **Prefer soft radii** (`8px`–`16px`) on cards and buttons — this differs from Anduril’s **sharp-only** rule; match the approachable bakery look.
- **Subtle** shadows for elevated cards: soft, low blur — not harsh drop-shadow UI chrome.
- **Gradients**: only if very subtle (cream → white) to separate sections; **no** multi-hue “rainbow mesh” unless it’s a deliberate full-bleed art piece.
- Cookie and lifestyle **imagery**: warm lighting; avoid cold blue tint over food photography.

### Components

**Primary button**

- Background: `accent-pink`, text: white, `font-weight: 500`–`600`, comfortable padding.
- Hover: `accent-pink-hover` (or `brightness` / `filter`), respect `focus-visible` ring in **ink** or **pink** with sufficient contrast.
- `border-radius`: match cards (e.g. `9999px` pill or `12px` rounded — **pick one system and reuse**).

**Secondary button**

- Outline: `1–2px solid` chocolate or `border-warm`, background transparent or cream.

**Cards (flavor tiles, promos)**

- White or warm background, soft border **or** light shadow, rounded corners, clear label + short descriptor.
- If showing nutrition or legal text, smaller type with adequate contrast; don’t dim below readable grey.

**Forms (newsletter signup)**

- Large tap targets, inline validation, success toast with warm green — not system-default red only.

### Motion

- Same **performance** discipline as the Anduril-style skill: prefer **transform/opacity**; cap UI feedback under **~250ms**; **respect `prefers-reduced-motion`**.
- Optional: gentle **hover scale** (1.02) on product cards — not aggressive bounce.

### Accessibility

- `aria-label` on icon-only controls; meaningful link text (not just “click here”).
- Don’t rely on **pink** alone for state — add icon or text for errors/success.
- Color contrast: especially pink on white; use darker pink or ink for small text on light backgrounds.

### Stack alignment (if engineering)

- Prefer project primitives first; if none, accessible foundations (e.g. Radix / React Aria / Base UI) with Chip City theming.
- **Tailwind**: extend theme with `chip.*` colors above; use `cn` / `clsx` + `tailwind-merge` for variants.

---

## Reference

- [chipcitycookies.com](https://chipcitycookies.com/) — tone, structure (Order, locations, shipping, catering, flavors, social).

**Note:** This skill describes a **plausible, cohesive** system consistent with a warm, modern cookie brand. Re-snapshot the production site and adjust exact hex values if the published CSS changes.
