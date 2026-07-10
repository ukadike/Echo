# Echo — Repository Audit

Date: 2026-07-02
Scope: full repo (README.md, SSL-METHOD.md, index.html, site.css, variables.css, .gitattributes, .nojekyll)

## Purpose

Echo is the AI-literacy branch of Small Systems Lab. It teaches people to question, use,
critique, and shape AI systems without surrendering judgment, culture, accessibility, or
community knowledge. Currently a GitHub Pages starter package, not yet a built-out curriculum.

## Current structure

```
.
├── .gitattributes
├── .nojekyll
├── README.md
├── SSL-METHOD.md
├── index.html
├── site.css
└── variables.css
```

Flat, single-page site. No `assets/`, no images, no additional HTML pages, no CI config.

## Homepage / entry point

`index.html` — single page, served via GitHub Pages (`.nojekyll` present, so Jekyll processing
is correctly disabled).

## Important pages

- `index.html` — the only page. Sections: header, "What this is," "SSL method inside Echo"
  (Operations of Care / Rule-Based Intelligence / Ancient Geometry cards), "Starter lessons"
  (list of 7), "Accessibility baseline," "Get involved," "Status," footer.
- `SSL-METHOD.md` — linked from index.html ("Read the full SSL method"). Standalone doc, not
  rendered as HTML on Pages (renders as GitHub-flavored markdown if visited directly on GitHub;
  no HTML wrapper page for it).

## Orphan pages

None found — the repo has no pages beyond `index.html` that aren't linked from it or from
README.

## Broken links

None found.
- Hub cross-link (`https://ukadike.github.io/Small-Systems-Lab/`, footer) uses lowercase
  `small-systems-lab`, matching the earlier fix in commit `204b51e` ("Fix hub link casing to
  lowercase small-systems-lab"). Still correct.
- `SSL-METHOD.md` relative link resolves to the file at repo root — exists.
- `https://github.com/ukadike/Echo/issues` — reachable (HTTP 200 verified).
- `github.com/ukadike` footer link — well-formed, not independently verified over network in
  this pass (proxy blocked the direct check) but the path is a standard profile URL.

## Missing navigation

Single-page site with in-page anchors implied by section IDs (`about-h`, `method-h`,
`lessons-h`, `access-h`, `involved-h`, `status-h`) but no visible in-page nav / table of
contents and no `<nav>` landmark. Not a defect for a page this short, but worth noting if the
page grows (e.g., once lesson pages exist, a nav will be needed).

## Missing documentation

- No `LICENSE` file, though the footer states "Copyright Adekemi (Kemi) Sijuwade Ukadike. All
  rights reserved unless otherwise stated." — consistent, but there's no separate LICENSE file
  to point to. Needs Kemi review if a formal license is wanted.
- No `CONTRIBUTING.md`, despite index.html inviting "questions, corrections, and lesson
  contributions... through GitHub." Not required, but a short contributing note would match the
  invitation. Needs Kemi review.
- The 7 "Starter Lessons" are listed by title only in both README.md and index.html — no lesson
  content, lesson pages, or lesson folders exist anywhere in the repo. This is honestly reflected
  as "in development" / "prototype" language in both files, so it is not a broken promise, but it
  means Echo currently has zero actual lesson content beyond a title list. Flagging this
  explicitly rather than treating it as complete.

## Duplicated / outdated files

None. README.md and index.html present the same three SSL-method concepts and the same 7-item
lesson list with consistent wording — no drift between them.

## Accessibility issues

Reviewed against WCAG-style basics (semantic HTML, alt text, focus states, heading order,
color-only meaning, keyboard nav):

- Semantic HTML: good — `header`, `main`, `section[aria-labelledby]`, `footer`, skip link to
  `#main`. No `<nav>` landmark, but there is no multi-item navigation to land in one yet.
- Alt text: no `<img>` elements exist in the repo, so there is nothing to caption. No issue
  found, but this should be re-checked the moment images are added (e.g., Nago-style diagrams,
  lesson graphics).
- Focus states: `variables.css` defines `--focus-outline` / `--focus-offset` and applies them
  globally (`*:focus`) plus explicitly on interactive elements. Skip link has a visible
  `:focus` position change. Good.
- Heading order: `h1` → `h2` (six sections) → `h3` (three method cards). No skipped levels.
- Color-only meaning: none found — no information is conveyed by color alone; text/labels
  carry all meaning.
- Keyboard nav: skip link present and functional via CSS position change on focus; all
  interactive elements are native `<a>` links, which are keyboard-operable by default. No
  custom widgets, so no custom keyboard handling is needed.
- `lang="en"` set on `<html>`. Meta description present and accurate.

No accessibility defects found. This is a clean, small implementation of the locked SSL
system.

## Code quality issues

- No build tooling, no linting config, no tests — appropriate for a static 3-file site at this
  stage; not flagged as a defect.
- `site.css` correctly treats `variables.css` as the locked token/component layer and only adds
  layout glue, per the file's own header comment. Consistent with the "do not redesign the
  locked SSL visual system" instruction.

## Recommended changes (not made — flagged for Kemi)

1. Decide on a formal `LICENSE` file to match the footer's copyright statement, or confirm
   "all rights reserved" is intentional as-is. **Needs Kemi review.**
2. Consider a short `CONTRIBUTING.md` given the "contributions welcome via GitHub" invitation
   on the homepage. **Needs Kemi review.**
3. When lesson content is written, plan for a `lessons/` (or similar) directory and an in-page
   or dedicated nav — not needed yet at 1 page.
4. When any image/diagram is added (Nago signage, screenshots, etc.), alt text must be added at
   that time to preserve the current clean accessibility state.

## Completed changes (this pass)

- Read and cross-checked README.md against index.html for consistency — no fixes needed, they
  already match.
- Verified the hub link casing fix from commit `204b51e` is still intact.
- Verified no broken internal links and no orphan pages.
- Added this audit (`docs/REPO_AUDIT.md`).
- Added `SCHEMA_CARD.md` and `INDEX.md` at repo root (see those files for content).

No content was deleted or altered in README.md, SSL-METHOD.md, index.html, site.css, or
variables.css during this pass — this was a read/audit/document pass only.
