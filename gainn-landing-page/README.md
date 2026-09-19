# GAINN — landing page (dark theme v1)

Static build of the GAINN landing page. Open `index.html` in any browser — no build
step, no dependencies, no server required. Fonts load from Google Fonts, so the first
load needs a connection; everything else is local.

GAINN — Graduate Advancement in Neuromodulation and Neurotechnology — is an NSERC
CREATE graduate training program delivered through the CRANIA NeuroModulation
Institute at the University of Toronto.

## Contents

| File | What it is |
| --- | --- |
| `index.html` | The full desktop landing page, 1440px canvas, 1120px content column |
| `mobile.html` | The 390px mobile layout (condensed: hero, about, requirements, news, footer) |
| `foundations.html` | Design foundations board — colour grid, type specimens, components, grid |
| `tokens.css` | Every colour, type size, spacing step and radius as CSS custom properties |
| `assets/gainn-logo-dark.png` | Logo recoloured for dark backgrounds (used by the pages) |
| `assets/gainn-logo-original.png` | The original supplied lockup, for light backgrounds |

## Sections on the page

Sticky nav → hero → partner strip → 01 About us → conditions band → 02 The field →
03 Program requirements → 04 News → 05 Events → 06 Team + 06.2 Partners →
07 Contact us → NSERC acknowledgement → footer (CRANIA slot, socials, partner links,
mailing-list signup, oversized wordmark).

Nav items are in-page anchors. The Upcoming / Past toggle in the events section is
wired with a few lines of vanilla JS at the bottom of `index.html`.

## Design system

**Typefaces** — Instrument Serif for display, Instrument Sans for body and UI,
IBM Plex Mono for technical labels and eyebrows.

**Colour** — everything is pulled from the logo itself. Near-black ink ground
(`#070A0F`) with a cool cast, U of T navy (`#1E3765`) as the hero glow, a lifted
signal blue (`#7CA6E2`) for labels, rules and links, and the mark's red (`#FF4A2B`)
reserved for nodes, section dots and primary calls to action.

**Spacing** — strict 4 / 8 scale. Sections are 128px top and bottom, 64px between
blocks, 48px under section eyebrows, 32px card padding, 24px grid gaps.

**Texture** — SVG fractal-noise grain (20% over the hero, 10–12% over the dark
bands and footer), a 32px dot mesh and faint column rules in the hero, 2% vertical
gradients on card surfaces, and 1px light seams across the top edge of key panels.

## What still needs real content

Anything in `[SQUARE BRACKETS]` is a deliberate placeholder, not filler copy:

- `[##]` trainees supported, `[X CREDITS]`, `[PER YEAR]`, `[DURATION]`, `[MODULES]`
- `[APPLICATION DATE]` and the `[ROLLING / ANNUAL]` review cycle
- `[PULL QUOTE FROM THE PROGRAM DIRECTOR]`
- News: `[DATE]`, `[CATEGORY]`, `[NEWS HEADLINE]`, `[FEATURE IMAGE]`, `[IMG]`
- Events: `[MON]`, `[00]`, `[EVENT TITLE]`, `[LOCATION]`, times
- Team: `[PHOTO]`, `[TEAM MEMBER]`, `[ROLE]`, `[SHORT BIO]`
- Partners: `[LOGO]`, `[PARTNER BLURB]`
- `[PHONE NUMBER]`, `[X] business days`, `[FREQUENCY]`
- `[NSERC LOGO]`, `[CRANIA]` logo, `[SOCIAL HANDLES]`
- The NSERC acknowledgement paragraph should be replaced with the official wording

Confirmed, real content already in place: the NSERC CREATE award and its value, the
participating graduate units, the five partner institutions, the CNMI office address
and `info.cnmi@utoronto.ca`, and the conditions neuromodulation therapies target.

## Notes for whoever builds this for real

- Layout is fixed-width by design (1440 canvas). `mobile.html` shows the intended
  small-screen treatment; the two need to be merged into one responsive build.
- Styles are inline so the design stays portable and editable as a comp. When porting
  to a framework, lift `tokens.css` first and replace inline values with the variables.
- Forms are markup only — no action, no validation, no backend.
- Every interactive element is a real `<button>`, `<a href>` or `<input>` with a
  `<label>`, and icon-only buttons carry `aria-label`, so keyboard and screen-reader
  behaviour survives the port.
