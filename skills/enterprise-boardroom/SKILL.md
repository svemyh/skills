---
name: enterprise-boardroom
description: Enterprise marketing — hierarchy, boardroom tone, forest/sage on stoneware neutrals. Brand-neutral; no third-party mark required.
---

# Enterprise boardroom web design

When building or reviewing marketing and product surfaces that should read as **precise, confident, and institutionally credible** (not consumer flash), apply these constraints.

## How to use

- `/enterprise-boardroom` — apply these layout, type, and copy rules in this session.
- `/enterprise-boardroom <file>` — review the file for hierarchy, tone, and fit; list violations and fixes.
- The **website-agent** runtime (text site builder) embeds this doc as the **default** visual baseline.

## Audience

- Expect **skeptical, time-poor, exacting** readers. Treat them as **experienced**; avoid beginner explainers and filler.
- **Partnership framing** — human judgment plus tooling speed and precision; not replacement hype. Copy and visuals should reinforce **collaboration** and **outcomes** (review, draft, research, workflow), not gimmicks.
- **Enterprise scale** — visuals should read as **boardroom-safe**, not startup-cute.

## Visual language

**Shape and surface**

- **Restraint over decoration** — communicate capability through **structure and hierarchy**, not illustrations of robots or "AI sparkles" unless art direction explicitly demands it.
- Prefer **generous whitespace**, clear **section breaks**, and **predictable** scroll rhythm: hero → value → pillars → verticals/segments → vision → trust/compliance → proof → CTA.
- **Corners:** subtle radii (e.g. `4px`–`12px`) or sharp; avoid toy-like **oversized** rounded everything.
- **Shadows:** minimal; when used, **soft and low** — enterprise SaaS, not DTC e-commerce.
- **No** rainbow gradients, **no** neon accents, **no** playful block UI unless the brand explicitly is that.

**Color (reference palette for this aesthetic)**

- **Page shell:** deep **charcoal / near-black** text and UI tokens mixed with **off-white / paper** section backgrounds. Non-exhaustive reference neutrals:
  - **Neutrals / type:** `#0A0A0A`, `#181614`, `#191614`, `#1c221c`, `#2d2d2d`, `#363636`, `#474747`, `#6b6b6b`, `#989898`, `#c3c3c3`, `#d0d0d0`
  - **Light surfaces:** `#FBFBF9`, `#FEFEFC`, `#f4f4f0`, `#f2f2ee`, `#ecece7`, `#e0e0dc`, `#e1dfdb` — **warm, stone-like** off-whites (not pure white everywhere)
  - **Accents (brand-adjacent):** `#a1c699` (sage), `#edfedc` / `#d0f289` (luminous lime highlights), `#bdd4f0` (cool sky for secondary emphasis), `#e68846` (terracotta for warmth), `#967868` (muted mauve/brown for subtle contrast), `#98a7aa` (slate for secondary text on light)
  - **Deep / forest:** `#00301e` (very dark **green** for high-contrast moments)
- **Vibe:** "serious practice + calm tech" — **forest/sage** + **sage-lime** energy on **stoneware** backgrounds; use **one** strong accent per scroll region; compliance rows stay on **subdued** neutrals.
- **Trust blocks (e.g. ISO, SOC, GDPR):** **sober** neutrals, icon + short line of copy.

**Typography**

- **Display / editorial:** a high-contrast serif (e.g. a Playfair-class face) for **hero/brand moments** and premium headline rhythm.
- **Hand-written emphasis:** a handwriting-adjacent face (e.g. a Kalam-class) — **sparingly** (marketing highlights, not body).
- **Mono / data / system:** a clean monospace (e.g. a Fragment-style) for technical, compliance, or "lab note" text.
- **Subheads / section intros:** **short**, declarative — outcome-led. Pair display serif with a calm sans in body.
- Re-check computed styles when pixel-matching; prefer loading fonts from a stable public CDN.

**Imagery**

- If photography: **real professionals** or **abstract** architectural detail — not repetitive stock handshakes.
- If product UI: **real** document flows with **tasteful** chrome — not fake glassmorphism for its own sake.

## Page architecture (typical)

1. **Hero** — aspirational H1, short supporting line, **two** clear actions: primary (e.g. book a call) and secondary (e.g. learn more).
2. **Value** — connect **time** back to **strategic** work.
3. **Pillars** — three or four **parallel** capabilities with **equal** weight; icons optional and **minimal**.
4. **Segments** — practice or industry as **scannable** lists or cards.
5. **Vision** — dignified narrative; avoid hype.
6. **Security and compliance** — dedicated, **serious** row: short lines per cert; this block is **expected** for enterprise trust.
7. **Proof** — named quotes with **role, org, region**; numbers only if true and credible.
8. **Closing CTA** — repeat primary conversion with **tight** copy.

## Copy voice

- **Confident, precise, human** — short sentences, **active** verbs, **no** buzzword pile-up.
- For law-adjacent products: do not misstate *practice of law* vs *tooling*; when in doubt, be **conservative** (not legal advice).
- **CTAs:** book a call / learn more / log in — **plain** B2B phrasing.

## Interaction and motion

- **Subtle** hover; **no** bouncy micro-interactions on compliance sections.
- Respect **`prefers-reduced-motion`**. If motion exists: **opacity** / **transform** only; keep durations **short** and **purposeful**.

## Anti-patterns (fails this style)

- Consumer-DTC or **playful** toy metaphors, **gamer** neon, or blocky "game" UI in the same category.
- Feature walls with **no** outcome framing.
- Unverifiable metrics.
- **Burying** security and compliance **below** long gimmick content.
- **Over-light** grey on white for body copy.

**Disclaimer:** palette samples reflect **typical enterprise marketing exports**; live sites may update. Re-check in DevTools when matching pixels exactly.
