# Quick Deployment Guide

## Option 1: Vercel (Fastest - Recommended)

1. **Install dependencies:**
   ```bash
   npm install
   ```

2. **Push to GitHub:**
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git remote add origin <your-github-repo-url>
   git push -u origin main
   ```

3. **Deploy to Vercel:**
   - Go to [vercel.com](https://vercel.com) and sign in with GitHub
   - Click "Add New Project"
   - Import your repository
   - Vercel auto-detects Astro - just click "Deploy"
   - Done! Your site is live in ~30 seconds

4. **Auto-deployment:**
   - Every commit to your main branch automatically triggers a new deployment
   - Add a `.md` file → commit → push → site updates automatically!

## Option 2: Netlify

1. **Push to GitHub** (same as above)

2. **Deploy to Netlify:**
   - Go to [netlify.com](https://netlify.com) and sign in with GitHub
   - Click "Add new site" → "Import an existing project"
   - Select your repository
   - Build settings:
     - Build command: `npm run build`
     - Publish directory: `dist`
   - Click "Deploy site"

## Folder Structure Preservation

Your folder structure in `content/blog/` is preserved in URLs:

- `content/blog/post.md` → `/blog/post`
- `content/blog/category/post.md` → `/blog/category/post`
- `content/blog/2024/january/post.md` → `/blog/2024/january/post`

Just add `.md` files anywhere in `content/blog/` and the structure is automatically reflected!

