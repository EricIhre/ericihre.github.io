# ericihre.github.io — Personal Site & CV

## Goal

A minimal, text-first personal website hosted on GitHub Pages at
`https://ericihre.github.io/`, modeled on the structure of
[edvinli.github.io/cv](https://edvinli.github.io/cv/): a short header that says
who I am, a CV page in plain reverse-chronological sections, and room for a few
project pages.

## Reference: what the inspiration site does

- **Site-wide top nav:** name (home), CV, Work, Research, plus links to individual projects.
- **Header block:** profile photo, name in lowercase, a one-line tagline
  (e.g. "senior ml engineer, phd"), location, and a row of links (email,
  Google Scholar, GitHub, LinkedIn, X/Twitter).
- **CV page:** single column, lowercase section headings, in this order:
  1. education: years, degree, institution
  2. work experience: years, title, linked employer, optional one-line note
  3. grants: year, title, funder, amount
- **Footer:** a single copyright line.
- **Style:** minimal. No sidebar, no cards, no animation. Content comes first.
- **Accessibility:** a "Skip to content" link at the top.

## Scope

### v1 (must have)
- [ ] `index.html`: home page with header block (photo, name, tagline, links) and a short bio
- [ ] `cv/index.html`: CV page with education and work experience sections
- [ ] Shared nav and footer on every page
- [ ] One shared stylesheet that works in light and dark mode (`prefers-color-scheme`)
- [ ] Responsive: readable on a phone with no horizontal scroll
- [ ] Deployed via GitHub Pages from `main`

### Later (nice to have)
- [ ] `work/` and `research/` pages (projects, publications)
- [ ] Extra CV sections if relevant: grants/awards, skills, publications, talks
- [ ] Downloadable PDF CV
- [ ] Individual project pages linked from the nav
- [ ] Favicon and Open Graph meta tags for link previews

### Out of scope
- Blog/CMS, analytics, contact forms, JS frameworks.

## Tech

- **Plain static HTML + CSS**, no build step. GitHub Pages serves the repo root directly.
- No JavaScript unless a specific feature needs it.
- System font stack, or one web font at most.
- Option: switch to Jekyll later if repeating the nav/footer by hand gets tedious.
  GitHub Pages builds Jekyll natively.

## Proposed structure

```
/
├── index.html          # home / about
├── cv/
│   └── index.html      # CV
├── work/index.html     # (later)
├── research/index.html # (later)
├── assets/
│   ├── style.css
│   └── profile.jpg
└── PROJECT.md
```

## Content I need to provide

- [ ] Display name and tagline
- [ ] Location
- [ ] Profile photo
- [ ] Links: email, GitHub, LinkedIn, others?
- [ ] Short bio (2–4 sentences)
- [ ] Education entries (years, degree, institution)
- [ ] Work entries (years, title, employer + URL)
- [ ] Any grants/awards/publications to list

## Design direction (to decide)

- Keep the reference's plain lowercase style, or add a small distinctive touch
  of my own (accent color, typeface)?
- Language: English, Swedish, or both?

## Definition of done (v1)

The live site at `https://ericihre.github.io/` shows the home page and CV with
my real content. It reads well on desktop and mobile, in light and dark mode,
and the nav works on every page.
