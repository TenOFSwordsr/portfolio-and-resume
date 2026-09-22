# Portfolio & Resume Pages

Two standalone, dependency-free HTML pages used as the author's public portfolio and résumé.
Each is a single file with all CSS inlined - no framework, no build step, no assets directory -
so either one can be dropped on any web root or opened directly in a browser. Both are English
(`lang="en"`), dark-themed, responsive, and carry an `@media print` stylesheet so the résumé
exports cleanly to PDF. Content covers freelance Python/automation work: scraping pipelines,
WordPress/REST integrations, document generation, and trading bots.

**Suggested repo name:** `dev-portfolio-resume`
**Stack:** hand-written HTML + inlined CSS (no JS build, no dependencies), inline SVG icons
**Status:** active
**Last modified:** 2026-09-12

## What it does

- `portfolio-index.html` - landing page: hero with avatar and role, stats row,
  `projects-grid` of `proj-card` entries, `skills-grid`, a `platforms-grid` of freelance
  profiles, and a contact block. Project cards name the real work: *Crypto Auto Trader*,
  *Doctoreto Scraper*, *hjs* (GitHub), plus skills tagged `BitPin API`, `GMGN On-chain`,
  `DexScreener`, `Apify`, `Fingerprint rotation`, `Chrome Automation`, `Cron`, `C / FFI`,
  `Google Sheets API`, `CoinGecko`, `AltFins`, `Flask`, `Bash`, `Active Directory`.
- `resume-index.html` - the same person as a formal CV: `hero`, `highlights`,
  `exp-card` (company / title / period / bullets), `edu-card` (degree, school, GPA),
  `lang-card` with country flags, skills, and buttons to the freelance profiles. Includes a
  standing note above the fold: "This resume was sent automatically using a Python script I
  built" - the pages are the destination of his automated application sending.
- Outbound links on both pages point at the author's freelance profiles and messaging handle
  (personal identifiers, not reproduced here).

## Layout

```
portfolio-index.html   377 lines, self-contained portfolio landing page
resume-index.html      739 lines, self-contained printable résumé
```

The intended deployment shape is two document roots (or one root with two files renamed to
`index.html`); the `-index` suffix is only a local convention to keep them side by side.

## Running it

Open either file in a browser directly - there is nothing to install or compile.

```
start portfolio-index.html
```

For a local preview over HTTP (so relative links behave): `python -m http.server 8000`.

## Notes

- Both pages reference an `avatar.jpg` that is **not** in this folder - `resume-index.html`
  expects `avatar.jpg` beside it, `portfolio-index.html` expects `/resume/avatar.jpg`. Add the
  image or both avatars render broken.
- The two pages duplicate the same `:root` palette, hero and contact markup with no shared
  stylesheet, so any change to identity or links has to be applied twice.
- These are personal pages, not part of the visital.ir site.
