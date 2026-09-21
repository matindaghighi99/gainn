# GAINN — website

Static site. All page content is currently placeholder — the design system, layout
and hero animation are in place, waiting on real copy.

## Structure

- `index.html` — the entire site. Self-contained: all CSS and JS inline. No build
  step, no dependencies to install.
- `mobile.html` — a standalone mobile layout study. Not linked from `index.html`.
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
