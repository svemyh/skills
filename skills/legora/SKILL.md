---
name: legora
description: UI and content patterns for Legora-style enterprise legal-AI marketing sites — confident hierarchy, lawyer-native tone, compliance-forward (see legora.com).
---

# Legora-style web design

When building or reviewing marketing and product surfaces that should feel like [Legora](https://legora.com/) — collaborative AI for exceptional lawyers — apply these constraints. Legora’s public site (repositioned with [Most Studios](https://moststudios.com/casestudy/legora) for global enterprise) aims for **precision, confidence, and institutional credibility**, not consumer flash.

## How to use

- `/legora` — Apply these constraints to layout, typography, and copy in this conversation.
- `/legora <file>` — Review the file for hierarchy, tone, and enterprise-fit issues; suggest concrete fixes.

---

## Brand & audience

- **Who reads this:** partners, practice leads, legal ops, security — often **skeptical, time-poor, and exacting**. The site should treat them as **experienced**; avoid beginner explainers and filler.
- **Promise:** *Lawyers bring judgment; AI brings speed, scale, and precision* — **partnership**, not replacement. Copy and visuals should reinforce **collaboration** and **outcomes** (review, draft, research, workflow), not gimmicks.
- **Positioning:** Category-defining **legal AI platform** at **enterprise** scale — visuals should read as **boardroom-safe**, not startup-cute.

## Visual language

**Shape & surface**

- **Restraint over decoration** — communicate capability through **structure and hierarchy**, not illustrations of robots or “AI sparkles” unless art direction explicitly demands it.
- Prefer **generous whitespace**, clear **section breaks**, and **predictable** scroll rhythm (hero → value prop → product pillars → verticals → vision/story → trust/compliance → social proof → CTA).
- **Corners:** subtle radii (e.g. `4px`–`12px`) or sharp; avoid toy-like **oversized** rounded everything.
- **Shadows:** minimal; when used, **soft and low** — enterprise SaaS, not DTC e-commerce.
- **No** rainbow gradients, **no** neon accents, **no** playful brick/blocks — that is a different brand entirely.

**Color & stack (measured from [legora.com](https://legora.com/) Framer export)**

- **Stack:** [Framer](https://www.framer.com/) — inline `data-framer-font-css` + **Framer Cloud** assets (not a hand-rolled GitHub design system in the open).
- **Page shell:** deep **charcoal / near-black** text and UI tokens mixed with **off-white / paper** section backgrounds. Hex values present in the shipped HTML/CSS include (non-exhaustive):
  - **Neutrals / type:** `#0A0A0A`, `#181614`, `#191614`, `#1c221c`, `#2d2d2d`, `#363636`, `#474747`, `#6b6b6b`, `#989898`, `#c3c3c3`, `#d0d0d0`
  - **Light surfaces:** `#FBFBF9`, `#FEFEFC`, `#f4f4f0`, `#f2f2ee`, `#ecece7`, `#e0e0dc`, `#e1dfdb` — **warm, stone-like** off-whites (not pure `#fff` everywhere)
  - **Accents (brand-adjacent):** `#a1c699` (sage), `#edfedc` / `#d0f289` (luminous **lime** highlights), `#bdd4f0` (cool **sky** for secondary emphasis), `#e68846` (terracotta for warmth), `#967868` (muted mauve/brown for subtle contrast), `#98a7aa` (slate for secondary text on light)
  - **Deep / forest:** `#00301e` (very dark **green** for high-contrast moments)
- **Vibe:** “**Serious law + calm tech**” — **forest/sage** + **sage-lime** energy on **stoneware** backgrounds; use **one** strong accent per scroll region; compliance rows stay on **subdued** neutrals.
- **Trust blocks (ISO, SOC, GDPR):** **sober** neutrals, no illustration spam — icon + short line of copy; same Framer component language as the rest of the page.

**Typography (measured from `fonts.gstatic` + Framer in-page `font-family` rules)**

- **Display / editorial:** [Playfair Display](https://fonts.google.com/specimen/Playfair+Display) (multiple weights, loaded for Latin + Cyrillic in their bundle) — use for **hero/brand moments** and premium headline rhythm.
- **Hand-drawn / emphasis accents:** [Kalam](https://fonts.google.com/specimen/Kalam) (handwriting-adjacent) — **sparingly** (marketing highlights, not body).
- **Mono / data / system:** [Fragment Mono](https://fonts.google.com/specimen/Fragment+Mono) — technical, compliance, or “lab note” text if matching their pattern.
- **Proprietary / brand:** at least one **Framer-uploaded** `.woff2` (e.g. `framerusercontent.com/assets/...woff2`) for lockups; **check Network → Font** in DevTools for the exact **family** name in CSS.
- **Subheads / section intros:** **short**, declarative — *Smarter tools, better outcomes* — outcome-led; pair Playfair with a calm sans from their stack in body (Framer’s CSS maps components to the families above; body copy in browser often lands on a **neutral sans** — verify in Computed styles when pixel-matching).

**Imagery**

- If photography: **real firms / professionals** or **abstract** architectural detail — not stock “handshake” clichés on repeat.
- If product UI: **real** surfaces (Word, email, document flows) with **tasteful** chrome — not fake glassmorphism for its own sake.

## Page architecture patterns (from legora.com)

1. **Hero** — Aspirational H1 (e.g. *Collaborative AI for exceptional lawyers*), short supporting line, **two** clear actions: primary (e.g. *Book a demo*) and secondary (e.g. *Learn more*). Optional brand line (*Law just got, more attractive.*) only if the tone matches a controlled marketing beat — keep it **sharp**, not cutesy.
2. **Value block** — Outcome copy: *Spend less time on routine…* — connect **time back** to **strategic** work.
3. **Pillars** — Three or four **parallel** capabilities (e.g. Review, Draft, Research) with **equal** visual weight; icons optional and **minimal**.
4. **“Where you are”** — **Practice / industry** segments (Litigation, M&A, Tax, etc.) as **scannable** lists or cards — not dense tables on the homepage.
5. **Vision** — Foundational narrative: *judgment + creativity* **with** *speed, scale, precision* — keep **dignified**, non-hype.
6. **Security & compliance** — Dedicated, **serious** treatment: **ISO, SOC, GDPR** with **one sentence each**; this block is **non-optional** for enterprise trust.
7. **Proof** — Named **quotes** with **role, firm, geography**; numbers only if **true** and **credible**.
8. **Closing CTA** — Repeat the **same** primary conversion (e.g. *Book a demo*) with **tight** copy.

## Copy voice

- **Confident, precise, human** — short sentences, **active** verbs, **no** buzzword pile-up (*synergistic next-gen AI paradigm*).
- **Legal-adjacent accuracy** — don’t misstate *practice of law* vs *tooling*; when in doubt, be **conservative** (not legal advice).
- **CTAs:** *Book a demo* / *Learn more* / *Log in* — **plain**, familiar for B2B buyers.

## Interaction & motion

- **Subtle** hover on links and buttons; **no** bouncy micro-interactions on compliance sections.
- Respect **`prefers-reduced-motion`**. If motion exists: **opacity** / **transform** only; keep durations **short** and **purposeful**.

## Anti-patterns (fails a Legora-style review)

- Consumer-DTC or **playful** toy metaphors, **gamer** neon, or **Minecraft**/**LEGO** block UI — wrong category.
- Walls of **feature** bullets with **no** outcome framing.
- Fake **metrics** or unverifiable claims.
- **Hiding** security and compliance **below the fold** of a long gimmick page.
- **Over-light** grey text on white for body copy.

## Reference

- [legora.com](https://legora.com/) — live hierarchy, copy, and compliance presentation.
- [Most Studios — Legora case study](https://moststudios.com/casestudy/legora) — *enterprise scale* brand + site as one system, *audience is experienced*.

**Disclaimer:** Copy and **hex samples** are from a **crawl of public Framer export HTML**; Framer may update tokens without notice. Re-check in DevTools (Computed color + **Network → Font**) when pixel-matching. Not a trademark claim; official brand books beat this doc.
