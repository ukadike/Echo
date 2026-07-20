# Echo — WCAG 2.1 AA Accessibility Audit

Date: 2026-07-20
Scope: all web content in the repo — `index.html`, `site.css`, `variables.css`. There are no
other HTML/CSS/JS files, no images, no forms, and no custom JS widgets in the repo, so those
categories are marked N/A below rather than "no issues found."

## Summary

| Severity | Found | Fixed | Left open |
|---|---|---|---|
| Critical | 0 | 0 | 0 |
| Serious | 0 | 0 | 0 |
| Moderate | 1 | 1 | 0 |
| Low / advisory | 1 | 0 | 1 |
| **Total** | **2** | **1** | **1** |

The one moderate finding was a real, measured contrast failure (not previously caught — the
prior `docs/REPO_AUDIT.md` pass reviewed contrast qualitatively but did not compute ratios).
The one open item is a decorative, non-text border color that traces back to a locked shared
token (`variables.css`) and was intentionally left unfixed per this task's ground rules — see
below.

## Issues found

### 1. `.text-meta` / `--color-muted` on `--color-paper` fails 4.5:1 text contrast (Moderate — fixed)

- **Where:** `variables.css:12` (`--color-muted: #6f6f6f`) and `variables.css:106-112`
  (`.text-meta` rule), consumed in `index.html:16` (header eyebrow), `index.html:58` ("Read
  the full SSL method" link line), and `index.html:117` (footer copyright line).
- **WCAG:** 1.4.3 Contrast (Minimum), AA.
- **Detail:** Computed contrast of `--color-muted` (`#6f6f6f`) against `--color-paper`
  (`#efece2`), the page background all three `.text-meta` instances render on, is **4.25:1**.
  The text is 0.85rem / normal weight, so it does not qualify as "large text" (needs 3:1) —
  it needs the full 4.5:1 and falls short. (For reference: the same muted color against
  `--color-white`/`--color-soft` is 5.02:1 / 4.77:1 — fine; the gap is specific to the paper
  background used on this page.)
- **Fix:** `variables.css` is a locked shared design-token file used across Small Systems Lab,
  Echo, omoluabi, and Umada — its token *values* were not changed. Instead, added a scoped
  override in `site.css:18-28` that sets `.text-meta` to `#6b6b6b` (a ~2-unit darkening,
  visually indistinguishable from the original `#6f6f6f`), which measures 4.51:1 on paper,
  5.33:1 on white, 4.51:1+ on soft. This is a point-of-use fix, not a token change.
- **Systemic flag (for Kemi, not fixed here):** because `--color-muted` itself is under 4.5:1
  against `--color-paper` specifically, any other page in the shared SSL family that pairs
  `--color-muted` text directly on `--color-paper` background likely has the same gap. Worth
  deciding whether to nudge the shared `--color-muted` token itself at some point — that
  decision belongs to whoever owns `variables.css` across repos, not to a single-repo fix.

### 2. `--color-line` decorative borders are below 3:1 non-text contrast (Low / advisory — left open)

- **Where:** `variables.css:12` (`--color-line: #d0cdc6`) and `--border-thin` (`variables.css:51`),
  used by `.divider` (`site.css:58-62`, the `<hr>` between sections) and `.card`
  (`variables.css:190-195`, the three method cards in `index.html:39-56`).
- **WCAG:** 1.4.11 Non-text Contrast, AA (as applied to "graphical objects required to
  understand content").
- **Detail:** `--color-line` against `--color-paper` is 1.34:1; against `--color-white` (card
  background) it's 1.59:1 — both well under the 3:1 minimum for UI-component/graphical-object
  boundaries.
- **Why left open:** these are purely decorative separators — a horizontal rule between
  sections and a card wrapper around already-labeled `<h3>` content. No control's identity or
  state depends on seeing this border; heading hierarchy and landmark structure convey the
  same grouping without it, so this is advisory rather than a hard content-understanding
  failure. It is also a token-locked color (`--color-line` from `variables.css`), so fixing it
  properly means either accepting a darker shared token or adding a repo-local override that
  would change the visual system's look (thin hairline dividers becoming visibly gray lines),
  which is a design decision beyond the scope of an accessibility patch. Flagging for Kemi to
  decide whether the shared token should be revisited, or whether an explicit non-decorative
  exception is acceptable as-is.

## Reviewed — no issues found

- **1.1.1 Non-text content:** no `<img>`, `<svg>`, icon-only buttons/links, or other non-text
  content anywhere in the repo. N/A.
- **1.3.1 Info & relationships:** single `<h1>` ("Echo"), followed by six `<h2>` section
  headings and three `<h3>` card headings inside the method section — no skipped levels.
  `header` / `main` / `footer` landmarks present; each `<section>` uses
  `aria-labelledby` pointing at its own heading id. Lists (`lesson-list` and the accessibility
  baseline list) use real `<ol>`/`<ul>`, not styled `<div>`s. No `<form>` elements exist, so no
  label-association issue is possible.
- **1.4.1 Use of color:** no information is conveyed by color alone; links are underlined by
  default (not distinguished by color only), and no status/state is color-coded.
- **1.4.3 / 1.4.11 Contrast (all other pairs checked):** `--color-ink` on `--color-paper`
  14.72:1, on `--color-white` 17.40:1, on `--color-soft` 16.51:1 — all pass easily. Button
  border/background (`--color-ink` on `--color-paper`) and focus outline
  (`--focus-outline: 2px solid var(--color-ink)`) both exceed 3:1 non-text contrast against
  every background used on the page.
- **2.1.1 / 2.4.7 Keyboard access & focus:** every interactive element is a native `<a>` (no
  custom widgets), so all are keyboard-operable by default. `variables.css` applies a visible
  `*:focus` outline globally and again explicitly on `input/textarea/button/a`; nothing sets
  `outline: none` anywhere in the repo. Skip link becomes visible on `:focus` via a position
  change (not `display:none`), which is the correct pattern.
- **2.4.1 Bypass blocks:** `index.html:12` has a working `.skip-link` to `#main`
  (`index.html:22`). There's no repeated nav (single-page site), so this is more than the
  minimum required, which is good.
- **2.4.2 Page titled:** `<title>Echo</title>` (`index.html:6`) present, matches the page's
  own `<h1>` and the project name, and is backed by a descriptive `<meta name="description">`
  on the line below. Considered adequate for what is effectively a one-page project identity
  card; not changed.
- **2.4.4 Link purpose:** every link's visible text is self-describing in context ("Read the
  full SSL method," "Open an issue on GitHub," "Small Systems Lab" inline in a sentence that
  names it as a hub). No bare "click here" / "read more" instances found.
- **3.1.1 Language of page:** `<html lang="en">` set (`index.html:2`).
- **4.1.2 Name, role, value:** no custom widgets (menus, toggles, modals, carousels, tabs)
  exist in the repo — everything is native HTML. N/A.
- **Motion:** `variables.css:60` sets `--transition: none` globally and `.btn` is the only rule
  that references `var(--transition)` — there is currently no CSS animation or transition
  running anywhere on the page, so there is nothing for a `prefers-reduced-motion` query to
  turn off yet. Not a violation today; worth adding a `prefers-reduced-motion` guard only once
  actual motion is introduced.
- **Inline SVGs:** none exist in the repo. N/A.

## Files changed

- `site.css` — added a scoped `.text-meta` color override (contrast fix, see Issue 1 above).
  No other files were modified; `variables.css` token values are untouched, and no HTML
  structure, wording, or content was changed.
