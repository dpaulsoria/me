# Portfolio (Astro + Tailwind)

Personal portfolio built with **Astro** and **Tailwind CSS**, featuring a Projects section powered by **Astro Content Collections** (Markdown entries) and clean, fast static pages.

## Tech Stack
- Astro
- Tailwind CSS
- Markdown Content Collections (`src/content/projects`)
- (Optional) Tailwind Typography for Markdown rendering

## Getting Started

### Install
```bash
npm install
```
### Run locally
```bash
npm run dev
```

### Build
```bash
npm run build
```

### Preview production build
```bash
npm run preview
```

### Project Structure
```txt
src/
  content/
    config.ts                # Content collections schema
    projects/                # One .md per project (portfolio entries)
  layouts/
    Layout.astro
  pages/
    index.astro              # Home (featured projects)
    projects/
      index.astro            # Projects listing
      [...slug].astro        # Project detail page (renders markdown)
  styles/
    global.css               # Tailwind + typography/plugin setup
```

### Adding Projects
Create a new mardkdown file in: `src/content/projects/<project-name>.md
Example:
```md
---
title: "Project title"
description: "Short, recruiter-friendly summary."
stack: ["Kotlin", "Laravel", "MySQL"]
repo: "https://github.com/username/repo"
url: "https://demo-link.com"
featured: true
order: 1
date: "2025-01-10"
---

## Problem
...

## What I built
...

## Architecture
...

## Challenges & tradeoffs
...

## Results / Impact
...

## What I’d improve next
...

```

### Ordering Projects
- **Home (Featured)**: set `featured: true` and control order with `order` (lower = first).
- **Projects page:** can be sorted by `order`, `date`, or custom logic (see `src/pages/projects/index.astro`).

### Deployments
This is a standard Astro static site. Deploy to any static host (e.g. Vercel, Netlify, Github Pages).
Run `npm run buil` and publish the `dist/` folder.

### License
MIT
```makefile
::contentReference[oaicite:0]{index=0}
```