# Claude Commands

This directory contains custom slash commands for Claude Code to enhance productivity when working with this AI blog.

## Available Commands

### `/generate-article` - AI Article Generation

A comprehensive command that automates the entire blog article creation process.

**What it does:**
1. **Searches** for the latest AI news using WebSearch
2. **Verifies** the topic hasn't been covered by checking existing posts
3. **Researches** the chosen topic in depth
4. **Generates** a well-structured, 800-1500 word article following the blog's template
5. **Creates** a properly formatted Jekyll post file

**How to use:**
```
/generate-article
```

That's it! The command will guide you through the entire process:
- It will present you with 3-5 current AI news topics
- You select which one to write about
- It conducts deep research on that topic
- It generates a complete, publication-ready article

**What you get:**
- A fully formatted blog post in `_posts/YYYY-MM-DD-topic-slug.md`
- Proper Jekyll front matter (layout, title, date, author)
- Well-structured content with clear sections
- 800-1500 words of original, researched content
- Adds hyperlinks to sources, in-line if able. 
- Accurate technical information from current sources
- Professional tone matching the blog's existing style

**Quality guarantees:**
- No duplicate topics (automatically checks existing posts)
- Current news (searches for recent developments)
- Accurate information (uses WebSearch for verification)
- Proper formatting (follows Jekyll conventions)
- Consistent style (matches blog voice)

## Command Development

To create additional commands, add new `.md` files to this directory. The filename (without extension) becomes the command name.

Example: `quick-fix.md` becomes `/quick-fix`

Commands should provide clear step-by-step instructions for Claude to follow.
