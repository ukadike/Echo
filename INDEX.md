# Index — Echo

Sitemap of the Echo repository. This is a single-page static site; there is no multi-page
structure beyond what's listed here.

## Root

- `README.md` — project overview, SSL Method inside Echo, Starter Lessons list, Accessibility
  Baseline, Status, Related SSL Projects.
- `SSL-METHOD.md` — the general Small Systems Lab Method (Operations of Care, Rule-Based
  Intelligence, Ancient Geometry as Interface Logic, Accessibility as System Architecture,
  Public Knowledge and Returnability). Linked from `index.html`.
- `index.html` — the live homepage (GitHub Pages entry point). Structure, in order:
  1. Skip link.
  2. Ecosystem nav — cross-repo links to all Small Systems Lab siblings (Small Systems Lab,
     Omoluabi, Earth Sensors Lab, Echo [current page], Umada, Accessible by Design) + GitHub.
  3. Breadcrumb — Small Systems Lab > Echo.
  4. Header — title and one-line description.
  5. "What this is" — Echo overview.
  6. "SSL method inside Echo" — three cards (Operations of Care, Rule-Based Intelligence,
     Ancient Geometry) + link to `SSL-METHOD.md`.
  7. "Lesson roadmap: seven starter lessons" — the 7 prototype lesson titles as numbered,
     linked items (each links to the Starter Lessons section of `README.md` on GitHub;
     individual lesson pages do not exist yet — `AWAITING FRAGMENT`).
  8. "Accessibility baseline" — 7-item list.
  9. "Get involved" — link to GitHub Issues.
  10. "Status" — GitHub Pages starter package, part of Small Systems Lab.
  11. Footer — link to Small Systems Lab hub, copyright.
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

- `https://ukadike.github.io/small-systems-lab/` — Small Systems Lab hub (ecosystem nav, breadcrumb,
  footer).
- `https://ukadike.github.io/omoluabi/` — Omoluabi (ecosystem nav).
- `https://ukadike.github.io/earth-sensors-lab/` — Earth Sensors Lab (ecosystem nav).
- `https://ukadike.github.io/echo/` — Echo, current page (ecosystem nav, `aria-current="page"`).
- `https://ukadike.github.io/umada/` — Umada (ecosystem nav).
- `https://ukadike.github.io/accessible-by-design-prototyping/` — Accessible by Design
  (ecosystem nav).
- `https://github.com/ukadike/Echo/blob/main/README.md#starter-lessons` — README Starter Lessons
  section (Lesson roadmap section, each of the 7 items).
- `https://github.com/ukadike/Echo/issues` — contribution/issue intake (Get involved section).
- `https://github.com/ukadike` — author GitHub profile (ecosystem nav, footer).

## Not yet present

- No lesson content pages (the 7 Starter Lessons are titles only, each linking to the shared
  README Starter Lessons anchor on GitHub — see `docs/REPO_AUDIT.md`). Individual per-lesson
  pages/anchors are `AWAITING FRAGMENT` and remain a follow-up.
- No images/assets directory.
- No LICENSE or CONTRIBUTING files (flagged as "Needs Kemi review" in `docs/REPO_AUDIT.md`).
