# WORKLOG — HSL Wall Boxes

## Current Tasks
- [ ] Multi-site expansion — waiting on box/port data from other campuses for location dropdown
- [x] Style overhaul — Easter design shipped: light default, dark header (#252525), orange accent (#f2a649), card polish, pill badges

## Decisions
2026-05-20 | Softened accent palette across the board — blue #4a9eff→#6096c8, green #4caf7d→#60a878, purple #9b7fe8→#8878c8, amber #f0a742→#c8a040, red #e8635a→#c86060. Updated every hardcoded hex and rgba in CSS, SVG, and light theme tints.
2026-05-20 | Added DOCTYPE, <head>, viewport meta tag, and </body></html> — file previously had no HTML structure, causing mobile browsers to render at 980px desktop width and ignoring all mobile media queries.
2026-04-15 | Kept existing brand accent colors (blue, green, amber, purple, red) — confirmed from TLC brand guidelines
2026-04-15 | Light theme uses CSS variable overrides via data-theme="dark/light" on document root; SVG floor plan overridden via ID selectors, no SVG structure changes needed
2026-04-15 | Theme preference persisted in localStorage under key `tlc_theme`, defaults to dark
2026-04-26 | Replaced Montserrat (Google Fonts) with local Gotham OTF files (Book/Medium/Bold/Black) via @font-face; removed Montserrat CDN link; updated all font-family references throughout CSS and SVG
2026-04-26 | Style overhaul planned to match https://brianpitre.github.io/easter-2026-schedule/ — full source analyzed. Plan: flip default to light theme, black full-width header with orange accent (#ff6900), white cards with 14px radius + box-shadows, pill-style badges, gray-light body (#f4f4f5), `<header class="app-header">` + `<main class="app-main">` HTML structure, dark theme becomes [data-theme="dark"] override. Implementation not yet started.

## Ideas / Parking Lot
- gotham_uJ50q.zip is still in the project folder (untracked) — safe to delete once fonts are confirmed working on live site

## Session Log
2026-05-20 | Easter design overhaul shipped to main via PR. Light theme default, dark header (#252525) with orange accent (#f2a649), full HTML restructure to app-header/app-main, 14px card radius, pill badges. Branched, previewed, iterated, merged.
2026-05-20 | Mobile pass + color refresh. Fixed missing viewport meta tag (root cause of all mobile CSS being ignored). Added responsive header, stacked connection rows, bottom sheet modal for input, larger touch targets, SVG expanded hit areas. Softened full color palette (all accents + SVG hardcoded colors). Fixed light theme SVG boxes showing square hit-area rect behind rounded corners.
2026-04-26 | Replaced Montserrat with Gotham (Book/Medium/Bold/Black OTFs). Analyzed Easter schedule design system for full style overhaul — plan documented in Decisions. Overhaul not yet implemented.
2026-04-15 | Added light/dark theme toggle — CSS variables, SVG floor plan support, header toggle button, localStorage persistence. Resolved merge conflict with main (Firebase auth branch). Deployed to https://tlc-wall-boxes.web.app via GitHub Actions (auto-deploy on push to main, ~34s).
