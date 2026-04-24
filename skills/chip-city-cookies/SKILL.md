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

### Colors (measured from production CSS)

**Source:** [chipcitycookies.com](https://chipcitycookies.com/) main stylesheet (`/_next/static/css/*.css`, Next.js + Tailwind). These are the real `cc*` design tokens (not approximations).

```css
/* Site tokens (rgb in production) */
--ccBackground:     #faf5eb;  /* page / header — warm paper */
--ccBackgroundDarker: #f4efd9; /* “newsletter” card / tinted panels */
--ccPink:   #f09fb1;  /* primary CTA fill, key brand */
--ccBlue:   #bcdce5;  /* secondary button (e.g. Find a Location) */
--ccGreen:  #95dbb8;  /* newsletter / insider actions */
--ccYellow: #f8dd81;  /* supporting accent in system */
--ccBlack:  #231f20;  /* type, dark fills, borders with brand */
```

**Vibe:** **pastel bakery** — pink + mint + powder blue on **cream** paper, **soft** not neon. Product photography and cookie-illustration SVGs; hero uses full-bleed cookie photography (`choc-chip*.webp`).

**Usage**

- On **light** sections: `ccBackground` / `ccBackgroundDarker`, text on `ccBlack`. Primary action: **pink** button (`ccPink` + white text); secondary: **black** fill or **blue** outline pill.
- **Borders** often `border-ccBlack` at 1px with rounded-full / rounded-lg (playful, not Anduril-sharp).
- Avoid Anduril-style **lime** on black — wrong category (Chip City is confectionery DTC, not defense UI).

### Typography (measured + observed)

- **Body / UI:** [Mulish](https://fonts.google.com/specimen/Mulish) variable from Google Fonts (`family=Mulish:ital,wght@0,200..1000;1,200..1000`) — loaded on the live site.
- **Display / marketing headlines:** `font-gooper` in components (e.g. H1 *Chip City Cookies*, section H2s) — **Gooper** is the expressive rounded face; load the same font files/weights if you match the brand.
- **H1 treatment:** `special-text` class on hero (outlined / stacked display treatment over photography).
- Headings: friendly, **not** Anduril-thin; section titles use Gooper at large sizes (`text-4xl`–`text-6xl` range on homepage).
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

- Production pattern: `bg-ccPink` + `border border-ccBlack` + **uppercase** + **rounded-full** (see homepage *Order Now*). Text often **white** on hero; elsewhere pair with `ccBlack` for contrast as built.
- Hover: site uses `hover:bg-ccPink/80` (or similar). Respect `focus-visible:ring` on the shared button primitive.

**Secondary button**

- Example: `bg-ccBlue` + `border-ccBlack` + `text-ccBlack` (e.g. *Find A Location* pill).

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

- Live site: **Next.js** + **Tailwind** + **Radix**-style primitives (e.g. `Dialog` for modals, `button` with `ring-offset-background`).
- Map tokens to the production names: `ccBackground`, `ccPink`, `ccBlue`, `ccBlack`, `ccGreen`, `ccBackgroundDarker` in Tailwind `extend`.

---

## Reference

- [chipcitycookies.com](https://chipcitycookies.com/) — tone, structure, Next.js + Tailwind implementation.

**Audit note:** Color tokens in this file were **extracted** from the published CSS bundle; fonts confirmed via `<link href="...Mulish...">` and `font-gooper` class usage. Re-crawl if the CSS fingerprint (`cdaa9ac2…css` etc.) changes after deploys.
