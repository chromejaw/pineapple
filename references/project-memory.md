# Project Memory: DESIGN.md

A skill loads only when a request matches it. Small follow-up requests like "add a settings toggle" can therefore drift from the system you built. A short `DESIGN.md` at the project root keeps the system durable for people and for any agent. This serves Apple's **Familiarity** principle: same look, same behavior, same place, across every screen and every session.

---

## 1. When to Read, Write, or Offer

| Situation | Do |
| :--- | :--- |
| Any design or build task in an existing project | **Read first:** `DESIGN.md`, the token sources (CSS custom properties, Tailwind config, theme files), and 2–3 representative screens. The committed system beats Pineapple's defaults. |
| You created a design system, or changed tokens (colors, type, radii, spacing, motion) | **Write or update `DESIGN.md`** from what you actually built: values taken from the code, not intentions. |
| Audit, review, or a small fix | **Don't write files unless asked.** Note any drift from `DESIGN.md` in the report. |
| `DESIGN.md` exists, and the project's agent-instructions file (`CLAUDE.md`, `AGENTS.md`, `.cursor/rules`) doesn't point to it | **Offer** to add the pointer block in §3. Edit that file only with the person's OK: it's loaded into every future session. |

**No `DESIGN.md` doesn't mean no system.** Consistent screens are a system. Document what exists instead of inventing a replacement.

---

## 2. DESIGN.md Template

Keep it under about 120 lines, factual, and derived from the code.

```markdown
# Design System — <Product>

Surfaces: app = Operate · marketing site = Persuade · docs = Read
Appearance: light + dark, follows the system setting

## Principles
- What this product optimizes for, in plain words ("calm, fast, keyboard-first").

## Tokens — source of truth: `src/styles/tokens.css`
| Role | Light | Dark | Increased contrast (light / dark) |
| --- | --- | --- | --- |
| Action tint: icons, selection, large glyphs | #0088FF | #0091FF | #1E6EF4 / #5CB8FF |
| Link and small tinted text | #1E6EF4 | #5CB8FF | #1E6EF4 / #5CB8FF |
| Filled button with a white label | #1E6EF4 | #1E6EF4 | same |
| Background / grouped | #FFFFFF / #F2F2F7 | #000000 / #1C1C1E | — |
| Label / secondary label (text) | #000 / rgba(60,60,67,.75) | #FFF / rgba(235,235,245,.6) | — |

- Type: `-apple-system, system-ui, "Segoe UI", Roboto, sans-serif`. Scale: Title 1 28/34 · Headline 17/22 semibold · Body 17/22 · Footnote 13/18
- Spacing: 4-pt base: 4 8 12 16 20 24 32 48
- Radii: controls = capsule · cards 12 · sheets 20 (nested radius = outer − padding)
- Depth: content opaque; top bar and sheets translucent; shadow `0 1px 3px rgb(0 0 0 / .08), 0 8px 24px rgb(0 0 0 / .06)`
- Motion: springs critically damped; small UI 150 ms ease-out; never animate keyboard shortcuts or list navigation

## Components & patterns
- Buttons: one primary per view; labels are verbs; every state from the state matrix.
- Forms, tables, navigation, empty states: the conventions actually in use.

## Voice
- Terminology, capitalization, the error-message pattern ("what happened + how to fix").

## Decisions & exceptions
- 2026-09-28: dense 32 px table rows on admin screens; 44 px everywhere else.
```

---

## 3. Agent-Instructions Pointer (offer; ≤ 12 lines)

```markdown
<!-- pineapple:start -->
## UI conventions
- Design system: DESIGN.md (tokens in src/styles/tokens.css). Use tokens, never raw hex values.
- Every UI change: visible labels and :focus-visible; touch targets ≥ 44 px; text ≥ 4.5:1;
  all states (hover, pressed, focus, disabled, loading, error, empty) without layout shift.
- Motion: none on keyboard shortcuts or list navigation; small UI ≤ 150 ms ease-out; respect prefers-reduced-motion.
- No decorative gradients, glow halos, cards nested in cards, icon tiles, or emoji icons.
- Theme ::selection, caret-color, accent-color, and panel scrollbars from tokens.
- For design, build, or audit work, use the pineapple skill.
<!-- pineapple:end -->
```

Rules:
- **Update the block in place** between its markers instead of appending duplicates.
- **Keep it short.** It costs context in every session.
- **Never overwrite** a person's own instructions; add alongside them.
- **Keep it current.** When tokens change, update `DESIGN.md` in the same change.
