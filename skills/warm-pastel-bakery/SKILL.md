---
name: warm-pastel-bakery
description: Warm cream, rose and mint and powder pastels, soft radii, indulgent retail. Brand-neutral; no third-party mark required.
---

# Warm pastel — bakery and indulgent DTC

When building marketing pages that should feel **warm, indulgent, playful, and "treat"** without looking cheap or childish, apply these constraints. Use **retail, food, or local** tone in copy — not any single trademark or borrowed headline.

## How to use

- `/warm-pastel-bakery` — apply this palette, type, and shape language in this session.
- `/warm-pastel-bakery <file>` — review for color clashes, accessibility, and "wrong category" (e.g. dark lime industrial).
- The website-agent runtime also embeds this as an alternate to the default enterprise baseline.

Use this for DTC, food, local retail, and "soft" consumer landing pages. Watch for neon, wrong-category accents, and contrast on pastel fills.

## Copy voice

- Friendly, celebratory, slightly nostalgic — not corporate.
- Short punchy hero lines; body can mention shipping, local presence, and rotating promos when relevant.
- "Indulgent" and flavor-forward language **sparingly**; avoid stacking superlatives.

## Colors (design tokens for this aesthetic)

**Typical real-world stack:** React + Next.js + Tailwind; map tokens in `extend`. These names mirror common production patterns:

```css
--wpBackground:     #faf5eb;  /* page / header — warm paper */
--wpBackgroundDarker: #f4efd9; /* newsletter card / tinted panels */
--wpRose:   #f09fb1;  /* primary CTA fill, key brand */
--wpPowderBlue:   #bcdce5;  /* secondary action */
--wpMint:  #95dbb8;  /* newsletter / insider actions */
--wpButter: #f8dd81;  /* supporting accent */
--wpInk:  #231f20;  /* type, dark fills, borders with brand */
```

**Vibe:** **pastel bakery** — pink + mint + powder blue on **cream** paper, **soft** not neon. Product photography and illustration hero patterns are common; warm lighting over food.

**Usage**

- On **light** sections: `wpBackground` / `wpBackgroundDarker`, text on `wpInk`. Primary action: **rose** with sufficient contrast; secondary: **ink** fill or **powder** outline.
- **Borders** often `1px` ink on rounded-full / rounded-lg (playful, not zero-radius industrial).
- Avoid the **stark-lime-ui** category (signature lime on pure black) — different visual language; this guide is warm confectionery / retail.

## Typography

- **Body / UI:** a humanist sans (e.g. a Mulish-class variable) is typical.
- **Display / marketing headlines:** a **rounded, expressive** display font for hero and section H2s — if you do not have the exact files, use the closest **rounded, friendly** display in the stack.
- **H1** often gets a special display treatment (outline/stacked) over **photography** when that matches the reference.
- **Sentence case** for most UI; **title case** for short nav is OK. Avoid all-caps walls except small labels; keep `letter-spacing` subtle (`0.02em`–`0.04em`), not ultra-wide nav tracking.
- Base body: `16px`–`18px`, `line-height` ~1.5–1.6.

## Spacing and layout

- Generous **padding**; let photography and whitespace sell the product.
- Content width: `max-width` around **1100px–1200px** for text; let hero and grids breathe.
- Card grids: **consistent** gaps (`16px`–`24px`); on mobile, single column with full-width images.

## Shape and surface (vs. stark / industrial UIs)

- **Prefer soft radii** (`8px`–`16px`) on cards and buttons — differs from **sharp-only** zero-radius systems; match the approachable look.
- **Subtle** shadows: soft, low blur — not harsh drop-shadow chrome.
- **Gradients:** only if very subtle (cream → white) to separate sections; **no** multi-hue rainbow mesh unless a deliberate art piece.
- **Imagery:** warm lighting; avoid cold blue tint on food.

## Components

**Primary button**

- Pattern: rose fill + ink border + **uppercase** + **rounded-full** is common. Ensure focus-visible ring.
- Hover: e.g. `80%` opacity of rose. Respect `focus-visible:ring`.

**Secondary button**

- Example: powder blue + ink text + full pill.

**Cards (product tiles, promos)**

- White or warm background, soft border **or** light shadow, rounded corners, short label + descriptor. Nutrition or legal: smaller type with **adequate** contrast; do not dim to unreadable grey.

**Forms (e.g. newsletter)**

- Large tap targets, clear validation, success with warm **mint**-family tone — not only default system red.

## Motion

- Same discipline as other guides: **transform/opacity**; cap UI feedback under **~250ms**; **respect `prefers-reduced-motion`**.
- Optional: gentle **hover scale** (1.02) on product cards — not aggressive bounce.

## Accessibility

- `aria-label` on icon-only controls; meaningful link text.
- **Do not** rely on **pink** alone for state — add icon or text for errors/success.
- Contrast: especially small text on rose/white; favor darker ink for fine print.

**Audit note:** tokens follow common published patterns for this retail aesthetic; re-verify after any major CSS or theme change.
