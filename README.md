# GAINN — website

Static site. `index.html` is currently a holding page — logo and "Coming soon"
only. The full template (design system, sections, hero animation) lives on the
`claude/spec-sections` branch and in history.

## Structure

- `index.html` — the entire site. Self-contained: all CSS and JS inline. No build
  step, no dependencies to install.
- `assets/` — source logo files (the pages do not load these; kept for future edits)

Two external requests at runtime: Google Fonts (Fraunces, Instrument Sans, IBM Plex Mono)
and three.js r128 from cdnjs for the hero animation.

## Local preview

Open `index.html` in a browser, or:

    python3 -m http.server 8000

## Deploy (Cloudflare Pages)

Push to `main` — Cloudflare Pages rebuilds and deploys automatically.

Project settings:

| Setting | Value |
| --- | --- |
| Framework preset | None |
| Build command | *(empty)* |
| Build output directory | `/` |

## Editing

Everything is in `index.html`. Design tokens live in the `:root` block at the top of
the `<style>` tag — colours, fonts, spacing, radii. Anything marked `[In brackets]` is
a placeholder waiting on real copy. Repeated items (partners, marquee entries, team
cards) are generated from short arrays near the top of the `<script>` block.
