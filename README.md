# GAINN — website

Static site for GAINN (Graduate Advancement in Neuromodulation and Neurotechnology),
CRANIA NeuroModulation Institute, University of Toronto.

## Structure

- `index.html` — the entire site. Self-contained: all CSS and JS inline, logo embedded
  as a data URI. No build step, no dependencies to install.
- `assets/` — source logo files (the page does not load these; kept for future edits)

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
the `<style>` tag — colours, fonts, spacing, radii. Content marked `[IN BRACKETS]` is a
placeholder waiting on real copy (dates, bios, photos, event details, phone number,
official NSERC acknowledgement wording).
