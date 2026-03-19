# THEME.md — triyambak.in Design System
_Reference for maintaining visual consistency across all future updates_

---

## Core Aesthetic
**Dark Glassmorphism** — deep dark backgrounds with frosted glass panels, subtle light effects, and minimal typography. Professional, premium, understated.

---

## Colour Palette

| Role | Value |
|---|---|
| Background (primary) | `#0A0A0F` |
| Background (secondary) | `#111118` |
| Surface / Card | `rgba(255,255,255,0.05)` |
| Surface border | `rgba(255,255,255,0.08)` |
| Text (primary) | `#F0F0F0` |
| Text (secondary) | `#8A8A9A` |
| Accent (glow / highlight) | `rgba(255,255,255,0.15)` |
| Accent (blue, use sparingly) | `#4A9EFF` |

---

## Typography

| Role | Spec |
|---|---|
| Headings | Light or Regular weight, wide letter-spacing (`0.05em`) |
| Body | 16px, line-height 1.7, `#8A8A9A` |
| Labels / Caps | Uppercase, `0.1em` tracking, small size |
| Font stack | `'Inter', sans-serif` or system UI |

---

## Glassmorphism Rules

```css
/* Standard glass card */
background: rgba(255, 255, 255, 0.05);
backdrop-filter: blur(20px);
-webkit-backdrop-filter: blur(20px);
border: 1px solid rgba(255, 255, 255, 0.08);
border-radius: 16px;

/* Elevated glass card */
background: rgba(255, 255, 255, 0.08);
backdrop-filter: blur(30px);
box-shadow: 0 8px 32px rgba(0, 0, 0, 0.4);
```

---

## Light Effects

- **Spotlight beam** — radial gradient from a focal point, white/warm white, low opacity (`0.06–0.12`)
- **Edge glow** — `box-shadow: inset 0 0 0 1px rgba(255,255,255,0.1)` on cards
- **Subtle halo** — large blurred radial gradient behind hero elements
- **No harsh shadows** — all shadows use black at low opacity (`rgba(0,0,0,0.3–0.5)`)

---

## Components

| Component | Rule |
|---|---|
| Buttons | Pill-shaped (`border-radius: 999px`), glass surface or solid dark |
| Cards | Rounded corners (`16–24px`), glass background, subtle border |
| Nav | Minimal, spaced, light weight text — no heavy bars |
| Icons | Thin/outline style, white or silver |
| Images | Circular crop for profile photos, subtle border ring |
| Dividers | `rgba(255,255,255,0.06)` — barely visible |

---

## Spacing & Layout

- Generous whitespace — sections breathe, never cramped
- Max content width: `1100px`, centred
- Section padding: `80–120px` vertical
- Card padding: `24–32px`

---

## What to Avoid

- Flat/material design — no solid coloured buttons in primary palette
- Bright white backgrounds
- Heavy drop shadows with colour
- Decorative gradients with multiple colours (keep monochrome)
- Cluttered layouts — less is more

---

## Reference Images
See `design-references/` folder — 6 inspiration images used to generate the original site.

---

_When asking Claude to update this website, say: "Follow THEME.md for design consistency."_
