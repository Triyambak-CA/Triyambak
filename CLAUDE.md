# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

Personal profile/CV website for S Triyambaka Patro (CA). Single-page static HTML site hosted on GitHub Pages at `triyambak.in`.

**Stack:** Pure HTML + CSS + vanilla JS — no build tools, no frameworks, no dependencies to install.

## Deployment

Every `git push origin main` auto-deploys to `https://triyambak.in` via GitHub Pages. There is no build step.

```bash
git add .
git commit -m "your message"
git push origin main
```

## File Structure

- `index.html` — entire site (HTML + CSS + JS in one file)
- `Photos/` — profile images referenced in the HTML
- `CNAME` — custom domain config (`triyambak.in`), do not modify
- `THEME.md` — design system spec, **read this before making any visual changes**
- `design-references/` — original inspiration images used to generate the site

## Design System

**Always read `THEME.md` before modifying or adding any UI.** Key rules:

- Background: `#070707`, CSS vars defined in `:root` at top of `index.html`
- Cards: glassmorphism — `rgba(16,16,16,0.72)` + `backdrop-filter: blur`
- Fonts: Cormorant Garamond (display/headings) · Inter (body) · JetBrains Mono (mono)
- Animated background orbs using `filter: blur(110px)` + CSS keyframe animations
- All CSS variables prefixed with `--` and defined in `:root`

## CSS Variable Reference

```
--bg, --card-bg, --card-bg-h   backgrounds
--border, --border-h           borders
--t1, --t2, --t3               text hierarchy
--silver                       accent text
--radius, --radius-sm          border radii
--font-d, --font-b, --font-m   font families
```

## Images

Profile photos live in `Photos/` and are referenced as relative paths (`Photos/filename.png`). Add new images to this folder before referencing them in HTML.
