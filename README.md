# AI Blogger - Static Blog Site

A fast, static blog site built with Astro that automatically generates pages from markdown files.

## Quick Start

1. **Install dependencies:**
   ```bash
   npm install
   ```

2. **Add your blog posts:**
   - Add `.md` files to the `src/content/blog/` folder
   - Each file needs frontmatter with `title`, `date`, and optionally `description`

3. **Run locally:**
   ```bash
   npm run dev
   ```

4. **Build for production:**
   ```bash
   npm run build
   ```

## Markdown File Format

Create `.md` files in `src/content/blog/` with this structure:

```markdown
---
title: "Your Post Title"
description: "Optional description"
date: 2024-01-15
draft: false
---

Your markdown content here...
```

## Deployment

### Deploy to Vercel (Recommended - Fastest)

1. Push your code to GitHub
2. Go to [vercel.com](https://vercel.com)
3. Import your repository
4. Vercel will auto-detect Astro and deploy
5. Every commit will trigger a new deployment!

### Deploy to Netlify

1. Push your code to GitHub
2. Go to [netlify.com](https://netlify.com)
3. Import your repository
4. Set build command: `npm run build`
5. Set publish directory: `dist`
6. Deploy!

## Auto-deployment

Both Vercel and Netlify automatically:
- Deploy on every commit
- Rebuild when you add/update markdown files
- Provide HTTPS and CDN automatically

## Project Structure

```
├── src/
│   ├── content/
│   │   └── blog/      # Add your .md files here
│   ├── layouts/       # Page layouts
│   └── pages/         # Route pages
├── public/            # Static assets
└── dist/              # Build output (generated)
```

## Features

- ✅ Automatic page generation from markdown
- ✅ Fast static site generation
- ✅ SEO-friendly
- ✅ Auto-deployment on commits
- ✅ Clean, simple design

