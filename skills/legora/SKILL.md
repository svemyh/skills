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

**Color (token-style — verify against live [legora.com](https://legora.com/) CSS as the brand evolves)**

- **Backgrounds:** near-white and warm off-white (paper-like), with **optional** deep sections for contrast (charcoal / near-black) for hero or footer — keep **contrast** WCAG AA+ for all text.
- **Text:** near-black body; **muted** secondary for supporting lines (not illegible light grey on white).
- **Primary accent:** one **disciplined** accent (often warm **gold/amber** or a **refined** brand color) — use for **one** primary CTA per view and key links, not scattered highlights.
- **Trust blocks:** compliance badges (ISO, SOC, GDPR) should read as **sober** — icon + label, no carnival styling.

**Typography**

- **Sans-serif, enterprise-grade** (e.g. class of grotesk / neo-grotesk with good legibility) — **match the live site** if a font is already defined in the product.
- **Headlines:** confident, often **tight** line-height on large type; **avoid** comedic or overly casual phrasing in H1s.
- **Subheads / section intros:** **short**, declarative — *Smarter tools, better outcomes* energy: outcome-led, not feature laundry lists in the hero.
- **Body:** comfortable reading size (`16px`+), **calm** line length (`max-width` for long prose).
- **Labels / nav:** clear, often **title case** or **sentence case**; avoid all-caps walls except small UI chrome.

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

**Disclaimer:** This skill distills **observable** marketing patterns and public case-study language — not a trademark claim. Re-check **legora.com** and brand guidelines when matching production tokens.
