# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What This Is

A static personal website (schuylermaclay.com) deployed on Vercel. No build step, no framework — just plain HTML, CSS, and images served as-is.

## Local Development

Serve locally with any static file server:

```sh
python3 -m http.server 8000
```

Then visit `http://localhost:8000`. There is no build, lint, or test step.

## Architecture

- **`index.html`** — Homepage (centered name + email)
- **`links/index.html`** — Links page (noindex, lists the reports below)
- **`warren-public-buildings-report/`** — Long-form historical report as a single self-contained HTML page with local images in `images/`. Uses Google Fonts (Libre Baskerville, Libre Franklin) and Chart.js from CDN.
- **`rice-mountain/`** — Long-form land history report, same pattern: single HTML page + `images/`. Uses Google Fonts (IM Fell English, Crimson Pro, Libre Baskerville).
- **`files/`** — Standalone documents and utility scripts (e.g., `serve.py` for local viewing of `warren_library.html`)
- **`robots.txt`** — Disallows crawling of all subpages except the homepage

## Conventions

- All pages use an inline SVG gray square as favicon (no external favicon file)
- Subpages use `<meta name="robots" content="noindex, nofollow">` to stay unlisted
- CSS is inlined in each HTML file (no external stylesheets)
- Images are stored locally in each report's `images/` directory, not hotlinked
- No JavaScript frameworks; the only JS dependency is Chart.js on the warren report
