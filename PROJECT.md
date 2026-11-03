# ericihre.github.io: Personal Site & CV

## Goal

A minimal, text-first personal website at **https://ericihre.github.io/**,
hosted on GitHub Pages. It was inspired by the structure of
[edvinli.github.io/cv](https://edvinli.github.io/cv/). The home page is a short
CV with a photo, a CV page has the full details, and there are pages for
research and projects.

## Status (2026-10-31)

All of the work below is live, deployed from `main`.

| Page | Path | State |
|---|---|---|
| Home | `index.html` | Done. Photo placeholder, contact links, short CV |
| CV | `cv/index.html` | Done. Full CV with bullet points and skills |
| Research | `research/index.html` | Done. Paper and master's thesis |
| Projects | `projects/index.html` | Empty, title only |

### Home page (`/`)
- Left column: photo placeholder box (dashed), then email, phone, LinkedIn and GitHub links.
- Right column: short CV with no page title (the name is already in the header).
  - **Education:** Lund University (MSc Engineering Mathematics) with plain-text
    lines for exchanges (TUM, Tokyo) and the CentraleSupélec summer school.
  - **Work experience:** Deloitte, RISE, MAG Interactive (2023), Qred Bank.
    The internships are left out to keep it short.
- On phones the photo and contact links stack above the CV.

### CV page (`/cv/`)
- Order: **Work experience**, then **Education**, then **Skills & interests**.
- Every job from the PDF CV, including the internships, with its bullet points.
  The RISE bullet links to the TMLR paper.
- Education: Lund (GPA, exchanges, courses and summer school as bullets) and
  Kungsholmens gymnasium (2015 – 2018).
- Skills & interests: label/value rows (programming, tools, AI tools,
  languages, climbing, scholarships).

### Research page (`/research/`)
- Paper first, then the thesis, each with a bold label before the title:
  - **Paper:** *On the effects of similarity metrics in decentralized deep
    learning under distributional shift* (2025, TMLR). Co-authored with
    Edvin Listo Zec, Tom Hagander and Sarunas Girdzijauskas.
    Link: [PDF](https://openreview.net/pdf?id=WppTEs4Kkn).
  - **Master's thesis:** *With a Little Help from My Friends: A Comparative
    Study of Decentralized Deep Learning Strategies* (2024, Lund University).
    Co-authored with Tom Hagander.
    Link: [record](https://lup.lub.lu.se/student-papers/record/9159064).
- Each entry has a summary paragraph and a link below it.

## Design decisions

- **Font:** EB Garamond (Google Fonts). It's a free Garamond; the commercial
  Garamond isn't licensed for the web. Fallback: `Garamond`, then serif.
- **Colors:** warm off-white in light mode and near-black in dark mode, following
  the system setting. Defined as CSS variables (`--bg`, `--text`, `--muted`,
  `--rule`).
- **Header:** the name on the left links home; CV · Research · Projects are on
  the right. The current page is shown brighter.
- **Entry layout** (shared by home, CV and research):
  - Title in bold on the left, with the **main dates on the right in bold/bright**.
  - Under the title: role or subtitle in *italics*. Secondary lines
    (exchanges, summer school) are in normal text, and per-role dates follow
    in parentheses in muted grey.
  - Under the dates: the location (or venue) in muted grey.
  - Bullet points or summaries span the full width below.
- **No separator lines** between sections; each section heading has its own underline.
- **Page width:** 60rem max, so the dates sit at the far right in line with the nav.
- **Stable header:** `scrollbar-gutter: stable` stops the header shifting
  sideways between short and long pages.
- **Same spacing** between the page title and the first content on every page.
- **Footer:** centered copyright line.
- **No click artifacts:** no text caret or mouse-focus outline when clicking.
  Keyboard users still get focus outlines.

## Tech & conventions

- Plain static HTML and CSS, no build step and no JavaScript.
- One stylesheet: `assets/style.css`.
- **Cache-busting:** every page links `assets/style.css?v=N`. **Bump `N` on
  all four pages whenever the CSS changes**, because GitHub Pages tells browsers
  to cache CSS for 10 minutes and visitors would otherwise see stale styles.
  The current version is `v=11`.
- The nav, footer and `<head>` are copied into each page by hand. Edit all
  four pages when changing them.
- The home and CV pages each hold their own copy of the entries; editing one
  doesn't update the other.
- Deploys take about 30–60 seconds after a push to `main`.
- **Privacy:** the source CV PDF contains a home address, so `.gitignore`
  excludes `*.pdf`. Don't commit it. A public PDF CV would need a redacted copy.

## Structure

```
/
├── index.html            # home: photo + short CV
├── cv/index.html         # full CV
├── research/index.html   # paper + thesis
├── projects/index.html   # (empty)
├── assets/style.css      # all styles
├── .gitignore            # excludes *.pdf
└── PROJECT.md
```

## Next up

- [ ] Replace the photo placeholder with a real photo (`assets/profile.jpg`)
- [ ] Fill in the Projects page
- [ ] Decide whether CentraleSupélec on the CV page should match the home page
      (plain line instead of a bullet)
- [ ] Favicon and Open Graph meta tags for link previews
- [ ] Optional: downloadable PDF CV (redacted, without the address)
- [ ] Optional: switch to Jekyll includes if editing the nav/footer in four
      places gets tedious
