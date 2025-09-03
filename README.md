# Google Homepage — Local Clone (THP02/Google)

A simple, tidy clone of the Google homepage in HTML/CSS (dark theme), designed to open locally with no external dependencies. The form submits to the real Google Search.

## Overview

- Local logo (`logo.svg`) and magnifying glass icon (`loupe.png`).
- Search bar with accessible label (visually hidden) and clear focus styles.
- Header and footer structured with `<nav>` for clean semantics.
- Basic responsiveness via `meta viewport` and flexible layout.

## Features

- Search: submits queries to `https://www.google.com/search` via GET (`name="q"`).
- Buttons: "Google Search" and "I'm Feeling Lucky" (visual behavior; the latter does not implement Google's special redirect — see TODO).
- Accessibility: hidden label via `.sr-only`, focus outlines (`:focus-visible`), semantic landmarks.
- Dark theme: background around `#202124` (Google dark theme), contrasted text, soft hover.

## Structure

```
THP02/Google/
├─ index.html      # Main page
├─ style.css       # Styles (foundations, layout, components)
├─ logo.svg        # Local Google logo (vector)
├─ loupe.png       # Magnifying glass icon (search bar)
└─ README.md       # This file
```

## Usage

- Option 1: open `index.html` directly in your browser.
- Option 2 (recommended): serve locally to avoid some CORS/relative URL edge cases.
  - VS Code: Live Server extension → "Open with Live Server" from `index.html`.
  - Node: `npx serve .` then open the provided URL.

## Implementation Details

- HTML
  - Document language: `en`.
  - `<header>`: primary navigation (Gmail, Images, Google apps, Profile — links can be customized).
  - `<main>`: hero (logo) + search form (input `name="q"`).
  - `<footer>`: three link groups (left/center/right). Some URLs are placeholders.

- CSS
  - Light reset: `box-sizing: border-box`, vertical layout `header/main/footer`.
  - Accessibility: `.sr-only` for a visually hidden but screen reader–read label.
  - Focus styles: `:focus-visible` for comfortable keyboard navigation.
  - Components: centered logo, search bar (magnifier icon), buttons, footer navs.

## Accessibility (a11y)

- Explicit label for the search input (visually hidden but in the DOM).
- Visible focus on links and interactive elements.
- Semantic structure: `header`, `main`, `footer`, `nav`, `form`, `label`.

## Known Limitations / TODO

- "I'm Feeling Lucky": reproducing the real Google behavior requires Google's server-side handling; locally, the button acts as a standard submit.
- Header/footer links: some are placeholders (`#`). Replace with official URLs if desired.
- Light theme: this project uses a dark theme. A dark/light toggle can be added.
- Extra icons: the "Google apps" icon and avatar are simplified; you can inline a more faithful SVG if needed.

## Tech

- Semantic HTML5
- CSS3 (flexbox, media queries, focus-visible)

## Quick Customization

- Tweak colors in `style.css` (consider CSS variables if you want to factor settings).
- Update links in `index.html` (header/footer) to point to real Google services.
- Swap `logo.svg`/`loupe.png` with your own assets if needed.

## Credits

- Google logo and brand belong to Google LLC. This project is for educational purposes.

---

Need pixel-perfect spacing/typography to match google.com, a light theme, or to open all links in new tabs (`target="_blank"`)? Open an issue/PR or ask for adjustments.
