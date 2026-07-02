# Schema Card — Echo

## Project name

Echo

## Purpose

Echo is the AI-literacy branch of Small Systems Lab. It teaches people how to question, use,
critique, and shape AI systems without surrendering judgment, culture, accessibility, or
community knowledge. It is a learning system for public understanding of how AI sees,
summarizes, misreads, translates, classifies, excludes, and assists — not only a curriculum.

## Audience

General public learners engaging with AI literacy education, within the wider Small Systems
Lab public-interest studio context. Site is designed for low-bandwidth, plain-language,
screen-reader access — implying a broad, non-specialist audience.

## Core concepts (as they appear in Echo's README.md / index.html)

### Operations of Care
Echo asks:
- Who is learning?
- What prior knowledge do they bring?
- What access needs exist?
- What should never be uploaded to an AI system?
- What does the machine know, guess, distort, or omit?
- How do learners keep authority over their own work?

### Rule-Based Intelligence
Echo teaches AI as a set of visible rules and choices: input, instruction, constraint, source,
uncertainty, bias check, human review, output, revision.

### Ancient Geometry in Echo
- **Circle** — prompt, response, reflection, revision.
- **Triangle** — learner, machine, community context.
- **Grid** — lesson structure, taxonomy, comparison.
- **Spiral** — iterative learning and skill growth.
- **Threshold** — when not to use AI.

(These are Echo-specific restatements of the general Small Systems Lab Method in
`SSL-METHOD.md` — Operations of Care, Rule-Based Intelligence, Ancient Geometry as Interface
Logic, Accessibility as System Architecture, and Public Knowledge and Returnability.)

## Interfaces

- Static GitHub Pages site (`index.html` + `site.css` + `variables.css`), single page.
- No forms, no API, no JavaScript, no build step.
- External interface: "Open an issue on GitHub" button linking to
  `https://github.com/ukadike/Echo/issues` for questions, corrections, and lesson
  contributions.

## Inputs / outputs

- Input: none (static, read-only site; no data collection, no upload mechanism — consistent
  with the "no upload" privacy warning listed under Accessibility Baseline).
- Output: rendered static HTML page for public reading.

## Dependencies

- None (no package manager, no JS framework, no external fonts/CDN calls detected in
  `index.html`).
- Shared CSS token system (`variables.css`) — the same locked "Omoluabi Visual Language
  System" used across Small Systems Lab, Earth Sensors Lab, and Omoluabi. Treated as canon;
  not modified in this repo.

## Related repos

- **Small Systems Lab** (hub) — `https://ukadike.github.io/small-systems-lab/`, linked from
  the Echo footer. Echo is one branch within this ecosystem.
- Earth Sensors Lab and Omoluabi — share the same locked SSL visual system (per project
  context); not directly linked from this repo's content.

## Accessibility considerations

- Plain language, captions and transcripts, screen-reader-readable lessons, alt text practice,
  high-contrast slides/pages, low-bandwidth materials, and "no upload" privacy warnings are all
  named as an explicit Accessibility Baseline in both README.md and index.html.
- Implementation currently matches these commitments: skip link, semantic landmarks, visible
  focus states (`variables.css`), correct heading order, no color-only meaning, no images (so
  no alt-text debt yet). See `docs/REPO_AUDIT.md` for the full accessibility review.
- No `<nav>` landmark yet — acceptable at one page; will need one if the site grows to multiple
  lesson pages.

## Future implementation notes

- The 7 "Starter Lessons" currently exist as titles only (no lesson content, no lesson pages).
  Any future lesson build-out should preserve the Operations of Care / Rule-Based Intelligence
  / Ancient Geometry framing already established, and should add alt text/captions at the same
  time any media is introduced.
- No LICENSE or CONTRIBUTING file exists yet despite the site inviting GitHub contributions —
  **Needs Kemi review** on whether to formalize either.
- If lesson pages are added, plan navigation (in-page anchor nav or a `<nav>` landmark) at that
  time.
