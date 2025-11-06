# AI Insights Blog

A simple AI-themed blog built with Jekyll and GitHub Pages.

## About

This blog explores topics in artificial intelligence, machine learning, and emerging technologies. It features articles on:

- Large Language Models
- Neural Networks
- AI Ethics
- Future of AI
- And more!

## Local Development

To run this blog locally:

1. Install Ruby and Bundler
2. Clone this repository
3. Run `bundle install`
4. Run `bundle exec jekyll serve`
5. Visit `http://localhost:4000`

## GitHub Pages Deployment

This site is designed to be deployed on GitHub Pages:

1. Push to your GitHub repository
2. Go to Settings > Pages
3. Select the branch to deploy (usually `main` or `master`)
4. Your site will be live at `https://[username].github.io/[repository]`

## Structure

```
.
├── _config.yml          # Jekyll configuration
├── _layouts/            # Page layouts
│   ├── default.html    # Base layout
│   └── post.html       # Blog post layout
├── _posts/             # Blog posts (Markdown)
├── assets/
│   └── css/
│       └── style.css   # Site styles
├── index.html          # Home page
├── Gemfile             # Ruby dependencies
└── README.md           # This file
```

## Writing Posts

Create new posts in the `_posts` directory following the naming convention:

```
YYYY-MM-DD-title-of-post.md
```

Each post should have front matter:

```yaml
---
layout: post
title: "Your Post Title"
date: YYYY-MM-DD HH:MM:SS -0000
author: Your Name
---

Your content here...
```

## License

Feel free to use this template for your own blog!
