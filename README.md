# portfolio

Professional portfolio website of **Ashitha Ambar** — Artificial Intelligence & Machine Learning student at AJ Institute of Engineering and Technology, Mangaluru.

Every personal and professional detail on the site (profile, education, skills, projects, achievement, certifications, languages) is transcribed from my resume. There is no invented content: no fabricated statistics, links, testimonials, or credentials.

## Features

- Responsive single-page portfolio: Home, About, Education, Skills, Projects, Achievements, Certifications, Languages, Contact, Footer
- Dark, technology-focused design with teal/indigo accents and modern typography
- Original SVG illustrations (animated hero network diagram + conceptual project artwork — clearly labelled as illustrations, not screenshots)
- Subtle reveal-on-scroll animations that respect `prefers-reduced-motion`
- Mobile navigation (hamburger menu) with keyboard and Escape-key support
- Accessible markup: skip link, semantic landmarks, single `h1`, labelled links, visible focus states
- SEO: page title, meta description, Open Graph/Twitter cards, hierarchical headings
- Functional `mailto:` / `tel:` links and real GitHub/LinkedIn profile links (no fake contact form)

## Tech stack

- [Vite](https://vite.dev/) 7 + [React](https://react.dev/) 19 + TypeScript (strict)
- Plain CSS with custom properties — no UI framework, no backend, no API keys
- Fonts: Space Grotesk (display) + Inter (body) via Google Fonts

## Getting started

```bash
npm install      # install dependencies
npm run dev      # start dev server → http://localhost:3000
npm run build    # typecheck + production build → dist/
npm run preview  # serve the production build
```

## Editing content

All site content lives in a single file:

```
src/data/content.ts
```

Profile details, skill groups, projects, achievements, certifications, and languages can all be updated there without touching any component code.

## Project structure

```
src/
├── components/        # one component + stylesheet per section
│   ├── Navbar.tsx     # responsive navigation
│   ├── Hero.tsx       # intro + animated SVG network
│   ├── About.tsx      # summary + education timeline
│   ├── Skills.tsx     # grouped skill cards
│   ├── Projects.tsx   # project cards + conceptual SVG art
│   ├── Achievements.tsx
│   ├── Certifications.tsx
│   ├── Languages.tsx
│   ├── Contact.tsx    # functional email/phone/profile links
│   ├── Footer.tsx
│   ├── Section.tsx    # shared section wrapper
│   └── Icon.tsx       # inline SVG icon set
├── data/content.ts    # single source of truth for all copy
├── hooks/useReveal.ts # reveal-on-scroll observer
└── styles/global.css  # design tokens, reset, shared utilities
```

## Verification

- `npm run build` passes (strict TypeScript + production bundle)
- 55 automated Playwright checks cover navigation anchors, mobile menu behavior, link correctness, resume facts, forbidden-content patterns, heading hierarchy, and horizontal-overflow at 390 px / 768 px / 1440 px
- No deployment is configured — this repository holds the source and can be deployed to any static host
