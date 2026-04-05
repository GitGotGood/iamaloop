# IAmALoop

Personal portfolio and writing hub for Dan Walsh — [iamaloop.com](https://iamaloop.com).

Built with [Astro](https://astro.build) + Tailwind CSS + MDX, deployed on Cloudflare Pages.

## Commands

| Command | What it does |
|---|---|
| `npm install` | Install dependencies |
| `npm run dev` | Start local dev server at `localhost:4321` |
| `npm run build` | Build production site to `./dist/` |
| `npm run preview` | Preview the production build locally |

## Adding content

### A new project
Create a file at `src/content/projects/my-project.md`:

```md
---
title: My Project
summary: One-line pitch.
repo: https://github.com/GitGotGood/my-project
demo: https://example.com
tech: ["TypeScript", "Astro"]
featured: true
date: 2026-04-05
---

Write about the project here. Markdown or MDX (`.mdx`) both work.
```

### A new article
Create a file at `src/content/articles/my-post.md`:

```md
---
title: My Post
description: A short description for previews and SEO.
date: 2026-04-05
tags: ["thoughts"]
draft: false
---

Write the article here.
```

Set `draft: true` to hide it from the live site while you're still writing.

## Project structure

```
src/
  components/      reusable .astro components
  content/
    articles/      markdown/mdx posts
    projects/      markdown/mdx project pages
  layouts/         page shells
  pages/           routes (file-based routing)
  styles/          global css
public/            static assets served as-is
```
