# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Static HTML website for **Montreal Parental Village** — a nonprofit supporting single parents in Montreal. No build system, bundler, or package manager. All pages are plain HTML files using Tailwind CSS via CDN.

## Deployment

- **Local:** Open any `code.html` directly in a browser via `file:///` path
- **Live site:** https://cyberartisant.github.io/montreal-parental-village/code.html
- **GitHub repo:** https://github.com/cyberartisant/montreal-parental-village
- Deploy by committing and pushing to `master` — GitHub Pages serves automatically within ~2 minutes

## Page Structure

Each page lives in its own folder with a `code.html` file:

| Page | File |
|------|------|
| Homepage | `code.html` |
| About Us | `About/code.html` |
| Services / Get Help | `Services/code.html` |
| Volunteer | `Volunteer/code.html` |
| Donate | `Donate/code.html` |
| Contact | `Contact/code.html` |

Asset paths are relative: root-level pages reference `MPV_logo.png`, `hero.jpg`, etc. directly; subpages use `../MPV_logo.png`, `../hero.jpg`, etc.

## Design System

Defined in `DESIGN.md` (root) and each folder's `DESIGN.md`. Key rules:
- **No 1px borders** for layout — use background color shifts instead
- **No #000000** — use `on-surface` (`#1a1c1d`) for dark text

### Brand Colors
| Token | Hex | Use |
|-------|-----|-----|
| Deep Navy (`primary`) | `#1F4E79` | Headlines, CTAs, backgrounds |
| Village Blue (`primary-container` / `secondary`) | `#2E75B6` | Buttons, icons, links |
| Sky Mist | `#D6E4F0` | Dividers, card fills |
| Cloud White (`surface` / `background`) | `#EBF3FB` | Page backgrounds |

### Typography
- **Headlines:** Lora (loaded via Google Fonts)
- **Body/UI:** Open Sans (loaded via Google Fonts)

### Shared CSS classes (defined inline in each file)
- `.bg-primary-gradient` — `linear-gradient(135deg, #1F4E79 0%, #2E75B6 100%)`
- `.glass-header` — `rgba(235, 243, 251, 0.8)` + `backdrop-filter: blur(20px)`

## Tailwind Configuration

Each `code.html` contains an inline Tailwind config script (`id="tailwind-config"`) that registers all brand color tokens. When adding a new page, copy this config block from an existing page. Tailwind is loaded from CDN — no local install.

## Key Components

**Village Beacon** — fixed bottom-right floating card (`z-40`/`z-50`) present on all pages. Provides 24/7 crisis line access.

**Testimonial Carousel** (homepage only) — pure JS, no library. Uses `id="t-viewport"`, `id="t-track"`, `.t-card` classes. JS sets pixel widths on resize for exact sliding.

**Navigation** — all pages share the same nav structure with links to all 6 pages plus a "Donate" CTA button. Active page typically highlighted with `text-[#1F4E79] font-bold border-b-2`.

## Git Workflow

```bash
cd "c:/Users/sierr/OneDrive/Desktop/MPV"
git add <files>
git commit -m "message"
git push
```

Avoid committing filenames with accented characters (e.g. `é`) — rename to ASCII equivalents before adding to git.
