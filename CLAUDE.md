# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Jekyll-based static blog deployed on GitHub Pages, focused on AI and machine learning topics. The site uses custom layouts and styling rather than relying on a pre-built theme.

## Development Commands

### Initial Setup
```bash
bundle install
```

### Local Development
```bash
bundle exec jekyll serve
```
Site will be available at `http://localhost:4000`

### Build Only
```bash
bundle exec jekyll build
```
Output goes to `_site/` directory (git-ignored)

## Architecture

### Jekyll Structure

The site follows standard Jekyll conventions with custom implementations:

- **_config.yml**: Site configuration (title, description, author, permalink structure)
- **_layouts/**: Custom HTML layouts that define page structure
  - `default.html`: Base layout with header/footer (wraps all pages)
  - `post.html`: Blog post layout (extends default.html)
- **_posts/**: Blog posts in Markdown format
- **assets/css/**: Custom CSS styling (no theme dependency)
- **index.html**: Home page that lists all posts

### Layout Hierarchy

```
default.html (base structure)
  └── post.html (blog post wrapper)
        └── [post content]
```

All pages use Liquid templating for dynamic content rendering.

### Styling

The site uses a custom CSS file (`assets/css/style.css`) with:
- Modern gradient-based design (purple gradients for header)
- Responsive design with mobile breakpoints
- Card-based post previews with hover effects
- Custom styling for markdown elements in posts

## Writing Blog Posts

### File Naming Convention
Posts must follow: `YYYY-MM-DD-title-slug.md`

Example: `2025-11-01-understanding-large-language-models.md`

### Post Front Matter (Required)
```yaml
---
layout: post
title: "Your Post Title"
date: YYYY-MM-DD HH:MM:SS -0000
author: AI Enthusiast
---
```

### Post Organization
- All posts go in `_posts/` directory
- Posts are automatically sorted by date (newest first on home page)
- URL structure: `/posts/YYYY/MM/DD/title-slug/` (per _config.yml permalink settings)

## Deployment

### GitHub Pages
This site deploys automatically via GitHub Pages:
- Configured in repository Settings > Pages
- Uses `github-pages` gem which includes Jekyll and compatible plugins
- Any push to the main branch triggers a rebuild

### Important Notes
- The `_site/` directory is git-ignored (generated during build)
- GitHub Pages runs Jekyll build automatically on push
- Local builds use the same `github-pages` gem for consistency

## Key Conventions

### Content Organization
- Home page (`index.html`) dynamically lists all posts from `_posts/`
- Each post uses the `post` layout which includes metadata display and back navigation
- Site configuration in `_config.yml` is used throughout templates via `site.*` variables

### Liquid Templating Patterns
- `{{ site.title }}` - Site-wide configuration
- `{{ page.title }}` - Current page/post data
- `{% for post in site.posts %}` - Iterate through all posts
- `{{ post.url | relative_url }}` - Generate proper URLs with baseurl support

### Styling Approach
- Single monolithic CSS file (no CSS preprocessor or build step)
- CSS variables could be added if more theming flexibility is needed
- Responsive design uses `@media (max-width: 768px)` breakpoint
