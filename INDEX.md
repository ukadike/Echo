# Index — Echo

Sitemap of the Echo repository. This is a single-page static site; there is no multi-page
structure beyond what's listed here.

## Root

- `README.md` — project overview, SSL Method inside Echo, Starter Lessons list, Accessibility
  Baseline, Status.
- `SSL-METHOD.md` — the general Small Systems Lab Method (Operations of Care, Rule-Based
  Intelligence, Ancient Geometry as Interface Logic, Accessibility as System Architecture,
  Public Knowledge and Returnability). Linked from `index.html`.
- `index.html` — the live homepage (GitHub Pages entry point). Sections, in order:
  1. Header — title and one-line description.
  2. "What this is" — Echo overview.
  3. "SSL method inside Echo" — three cards (Operations of Care, Rule-Based Intelligence,
     Ancient Geometry) + link to `SSL-METHOD.md`.
  4. "Starter lessons" — list of 7 prototype lesson titles (titles only, no content yet).
  5. "Accessibility baseline" — 7-item list.
  6. "Get involved" — link to GitHub Issues.
  7. "Status" — GitHub Pages starter package, part of Small Systems Lab.
  8. Footer — link to Small Systems Lab hub, copyright.
- `site.css` — layout glue (max-width, grid, base element rules). Not the token/component
  system — see `variables.css`.
- `variables.css` — locked "Omoluabi Visual Language System" CSS custom properties and
  components, shared across Small Systems Lab, Earth Sensors Lab, and Omoluabi. Canon; not
  modified here.
- `.nojekyll` — disables GitHub Pages' Jekyll processing (required since the site is plain
  static HTML/CSS).
- `.gitattributes` — text/LF normalization only.

## Documentation added in this restoration pass

- `docs/REPO_AUDIT.md` — full repository audit (structure, links, accessibility, gaps,
  recommendations).
- `SCHEMA_CARD.md` — project schema card (purpose, audience, core concepts, interfaces,
  dependencies, related repos, accessibility, future notes).
- `INDEX.md` — this file.

## External links referenced by the site

- `https://ukadike.github.io/Small-Systems-Lab/` — Small Systems Lab hub (footer).
- `https://github.com/ukadike/Echo/issues` — contribution/issue intake (Get involved section).
- `https://github.com/ukadike` — author GitHub profile (footer).

## Not yet present

- No lesson content pages (the 7 Starter Lessons are titles only — see `docs/REPO_AUDIT.md`).
- No images/assets directory.
- No LICENSE or CONTRIBUTING files (flagged as "Needs Kemi review" in `docs/REPO_AUDIT.md`).
