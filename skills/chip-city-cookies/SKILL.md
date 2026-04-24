---
name: chip-city-cookies
description: Chip City Cookies UI — full pastel spectrum (pink, powder blue, cream, mint) on warm paper; chipcitycookies.com aligned.
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

### Colors — full pastel spectrum (not “pink + brown only”)

**Source:** Aligned with [chipcitycookies.com](https://chipcitycookies.com/) production `cc*` tokens (Next.js + Tailwind). The brand reads as a **four-pastel system** on warm paper — use **all** of them in layout, not a single hero color.

**Canonical pastels (use across UI, sections, and components)**

| Token | Hex | Role |
| --- | --- | --- |
| **Pink** | `#f09fb1` | Primary CTAs, key links, “hero” emphasis, selected chips |
| **Powder blue** | `#bcdce5` | Secondary actions, info panels, “Find a location”-style pills, cool relief next to pink |
| **Cream** | `#f4efda` | Section bands, cards, modals, newsletter/insider shells — **large** fields of color (not only white) |
| **Mint** | `#96dbb8` | Success/positive, insider signup, “fresh batch” energy, alternate buttons or badge fills |

**Supporting (from live CSS — typography, borders, extra punch)**

```css
--ccBackground:     #faf5eb;   /* default page / header when not on cream band */
--ccYellow:         #f8dd81;  /* small highlights, icon fills, rare emphasis */
--ccBlack:          #231f20;  /* type, strong borders, icon strokes — not the only “dark” with pastels */
```

**Vibe:** **Full-spectrum bakery pastel** — rotate **pink, blue, cream, mint** through the page: alternating section backgrounds, multi-color **icon** or **illustration** accents, flavor tags, and cards. **Do not** reduce the brand to “pink CTA on brown text”; that underuses the system.

**Usage rules**

- **Sections:** alternate **cream `#f4efda`** with **default paper `#faf5eb`** or a **tinted row** (e.g. mint at 15–20% opacity or a strip of **powder blue** behind a quote) so the scroll feels **colorful**, not one flat beige.
- **CTAs:** primary can stay **pink**; place **blue** and **mint** on **equal** footing for secondary, tertiary, and context-specific actions (shipping vs. local vs. insider).
- **Cards & modules:** at least one **non-pink** pastel on large surfaces per viewport (cream band + blue **or** mint header strip, etc.).
- **Borders / chrome:** `border-ccBlack` (or soft warm grey) on pills — keep **playful** radii, not Anduril-sharp.
- **Photography:** food photos stay warm; **UI chrome** can use the **full pastel set** around them.
- Avoid defense-style **lime-on-black** or **neon** — this is a **soft** DTC palette.

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

**Buttons (spread pastels; don’t default everything to pink)**

- **Primary (order / main goal):** `bg-[#f09fb1]` + `border border-ccBlack` + **uppercase** + **rounded-full** — *Order Now* pattern. Text **white** or `ccBlack` per contrast on background.
- **Secondary / wayfinding:** `bg-[#bcdce5]` + `border-ccBlack` + `text-ccBlack` — e.g. *Find a location*.
- **Positive / insider / “join”:** `bg-[#96dbb8]` + `border-ccBlack` — e.g. newsletter / *Sign up*; pairs well on **`#f4efda`** panels.
- Hover: opacity or `/90` tints; keep **focus-visible** rings visible on all variants.

**Cards, bands, and promos**

- **Surface** large areas with **`#f4efda`** or **`#faf5eb`**; add **left border**, **top strip**, or **icon blob** in **blue** or **mint** so every block isn’t “cream + black text only.”
- Flavor tiles: rotate **pink / blue / mint** for **accents** (tags, small fills) — not only pink.
- **Typography** stays mostly `ccBlack` on pastels; check **contrast** (especially blue text on blue fill — often **black** for button labels).

**Forms (newsletter signup)**

- **Panel:** `bg-[#f4efda]` or mint-tint; **submit** can be **green** or **pink**; validation success leans **mint** (`#96dbb8`), not generic system green.

### Motion

- Same **performance** discipline as the Anduril-style skill: prefer **transform/opacity**; cap UI feedback under **~250ms**; **respect `prefers-reduced-motion`**.
- Optional: gentle **hover scale** (1.02) on product cards — not aggressive bounce.

### Accessibility

- `aria-label` on icon-only controls; meaningful link text (not just “click here”).
- Don’t rely on a **single** pastel for state — use **icon + text**; success can lean **mint**; errors use a **clear** semantic red separate from the marketing palette.
- Contrast: small text on **`#bcdce5`** or **`#96dbb8`** may need **ccBlack** or a darker border — verify WCAG for body copy and buttons.

### Stack alignment (if engineering)

- Live site: **Next.js** + **Tailwind** + **Radix**-style primitives (e.g. `Dialog` for modals, `button` with `ring-offset-background`).
- In Tailwind `extend`, map `#f09fb1`, `#bcdce5`, `#f4efda`, `#96dbb8` (e.g. as `ccPink`, `ccBlue`, `ccCream`, `ccGreen`) **plus** `ccBackground` / `ccBlack` for parity with the live `cc*` scale.

---

## Reference

- [chipcitycookies.com](https://chipcitycookies.com/) — tone, structure, Next.js + Tailwind implementation.

**Audit note:** Color tokens in this file were **extracted** from the published CSS bundle; fonts confirmed via `<link href="...Mulish...">` and `font-gooper` class usage. Re-crawl if the CSS fingerprint (`cdaa9ac2…css` etc.) changes after deploys.
