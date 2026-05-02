# THEME.md — triyambak.in Design System

Human-readable index to `assets/site.css`. Source of truth for all values is `:root` in that file. Update this doc whenever a new shared component is added.

---

## Core Aesthetic

Dark glassmorphism — deep black background, frosted-glass panels, animated blur orbs, classical-display typography for emphasis, mono accents for technical/UI labels. Professional, premium, understated.

---

## Design Tokens (CSS Variables)

All defined in `:root` at the top of `assets/site.css`. Never invent new values; always extend with these.

### Colour
| Token | Value | Usage |
|---|---|---|
| `--bg` | `#070707` | Page background |
| `--card-bg` | `rgba(16,16,16,0.72)` | Glass card base |
| `--card-bg-h` | `rgba(24,24,24,0.85)` | Glass card hover |
| `--border` | `rgba(255,255,255,0.07)` | Default border / divider |
| `--border-h` | `rgba(255,255,255,0.13)` | Hover / accent border |
| `--t1` | `#e0e0e0` | Primary text |
| `--t2` | `rgba(224,224,224,0.52)` | Secondary text / body copy |
| `--t3` | `rgba(224,224,224,0.28)` | Tertiary text / labels |
| `--silver` | `rgba(200,200,200,0.8)` | Subtle accent text |

### Radius
| Token | Value |
|---|---|
| `--radius` | `18px` |
| `--radius-sm` | `10px` |

### Type
| Token | Stack | Role |
|---|---|---|
| `--font-d` | `'Cormorant Garamond', Georgia, serif` | Display / headings |
| `--font-b` | `'Inter', system-ui, sans-serif` | Body |
| `--font-m` | `'JetBrains Mono', 'Courier New', monospace` | Labels, eyebrows, technical |

### Motion
| Token | Value |
|---|---|
| `--ease` | `cubic-bezier(0.25,0.46,0.45,0.94)` |
| `--trans` | `0.35s var(--ease)` |

---

## Layout

- `main` — adds `padding-top: 62px` (clears fixed nav).
- `.container` — `max-width: 1140px`, centred, `0 36px` side padding.
- `section` — `108px 0` vertical padding (homepage). Tools detail pages use lighter `60px 0` per section since each page has many.
- Background ambience — `.bg-layer` with three blurred orbs (`.orb-1/2/3`), grid lines, plus a JS-driven `#cursor-glow`.

---

## Reusable Components

### Section headers
- `.eyebrow` — small mono label with leading dash. Goes above every section title.
- `.sec-title` — Cormorant headline (`clamp(38px, 5vw, 56px)`). Wrap the emphasis word in `<em>` for italic-grey styling.

### Cards
- `.glass` — frosted-glass card with **hover lift** (translateY + brighter bg + stronger shadow). Use for interactive items.
- `.glass-flat` — same surface, **no hover lift**. Use for static prose containers.

### Pills
- `.tag` — neutral pill chip, mono font. Used for category labels and metadata.
- `.btn` `.btn-primary` `.btn-ghost` — pill buttons. Primary is filled-translucent, ghost is outline-only.

### Status badges (used in content cards + tool hero)
| Class | Colour | Used for |
|---|---|---|
| `.s-completed` | green | Reading "Completed", Watch "Completed", **Tools "Published"** |
| `.s-watching` | neutral grey | Watch "Watching", **Tools "Beta"** |
| `.s-reading` | neutral grey | Reading "Reading" |
| `.s-queue` | violet | Reading/Watch "Queue", **Tools "Coming Soon"** |

Badge markup: `<span class="status-badge s-X"><span class="status-dot"></span>Label</span>`.

### Collections
- `.content-grid` — responsive 3 → 2 → 1 col grid.
- `.content-card` — flex column card with `.cat-tag`, `.cc-title`, `.cc-sub`, `.cc-notes`, `.cc-footer`.
- `.filter-row` + `.filter-btn` — pill-style filter buttons with `.active` state.
- `.empty-state` — dashed-border placeholder with `.es-icon`, `.es-title`, `.es-text`, optional `.es-code`.

### Animation
- `.reveal` — IntersectionObserver-driven fade-up. Apply per child; auto-staggered up to 6.
- Hero-only fade animations are inline in the hero CSS (`fadeUp` keyframes, declarative delays).

### Homepage-specific
- Hero: `.hero-inner`, `.hero-name`, `.hero-photo-frame`, etc.
- About: `.about-grid`, `.info-card`, `.about-text`, `.about-avatar`.
- Experience: `.timeline`, `.tl-item`, `.tl-card`, `.tl-bullets`.
- Practice: `.practice-grid`, `.practice-card`.
- Qualifications: `.qual-grid`, `.qual-card`, `.qual-row`.
- Skills: `.skills-grid`, `.skill-card`, `.tags-wrap`.
- Contact: `.contact-grid`, `.contact-card`, `.interest-chip`.

---

## Tools Section Additions

Components introduced for `/tools/` hub and `/tools/<slug>/` detail pages. All build on the tokens above.

| Class | Purpose |
|---|---|
| `.tool-card` | Anchor wrapper for hub grid cards — strips underline, inherits colour. |
| `.tool-tagline` | Cormorant italic, `--t2`, sits below the indicator title in the hero. |
| `.tool-meta-row` | Flex row with `gap: 12px` — holds status badge + category tag + "last updated". |
| `.tool-prose` | Long-form prose container, `max-width: 760px`, Inter 15px on `--t2`, line-height 1.85. Styles `h3`, `h4`, `p`, `ul/ol`, `code`, `a` for documentation copy. |
| `.callout` | Formula/methodology box: glass surface + subtle accent left-border. Use `<div class="formula">…</div>` inside for mono equation blocks. |
| `.input-table` | Input documentation table — mono headers, mono first two columns, thin row dividers. Collapses to stacked rows under 700px. |
| `.changelog` | Version-history list. Each entry is `<li class="cl-item">` containing `.cl-version`, `.cl-date`, `.cl-body`. `.cl-body ul` renders as a regular bulleted list. |

**Status mapping for Tools:** `published` → `s-completed`, `beta` → `s-watching`, `coming-soon` → `s-queue`.

---

## Light Effects (in use)

- Background orbs: three blurred radial gradients (`filter: blur(110px)`) drifting on long alternating animations.
- Cursor glow: `#cursor-glow` follows the mouse with a soft radial gradient.
- Card highlight: `inset 0 1px 0 rgba(255,255,255,0.07)` on every `.glass`/`.glass-flat`.
- Hero spotlight: oversized centred radial gradient on the hero section.
- Hero photo frame: subtle multi-layer shadow + a top-down gradient overlay on the image itself.

No solid coloured shadows. No bright accents in primary palette. No flat-material UI.

---

## What to Avoid

- New colours, fonts, or radius values outside the `:root` tokens.
- Heavy drop shadows with colour.
- Decorative multi-colour gradients.
- Solid bright backgrounds.
- Cluttered layouts — every section should breathe.

---

## Reference Images

`design-references/` holds the original inspiration images for the homepage. Reference only.

---

_When asking Claude to update this site, say: "Follow THEME.md for design consistency."_
