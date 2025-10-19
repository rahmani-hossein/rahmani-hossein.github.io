# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is an **Academic Pages** website built with Jekyll - a static site generator for GitHub Pages. It's a personal academic portfolio for Hossein Rahmani showcasing publications, teaching, talks, blog posts, and CV.

**Key characteristics:**
- Built on Jekyll 3.10.0 using the github-pages gem (v232)
- Forked from Minimal Mistakes theme
- Deploys automatically to GitHub Pages at https://rahmani-hossein.github.io
- Uses Jekyll Collections for organizing academic content

## Development Commands

### Running the Development Server

**macOS (Homebrew Ruby):**
```bash
# Required: Use UTF-8 encoding to avoid character encoding errors with Ruby 3.4+
LANG=en_US.UTF-8 LC_ALL=en_US.UTF-8 /opt/homebrew/opt/ruby/bin/bundle exec jekyll serve --livereload
```

**Alternative (if Ruby is in PATH):**
```bash
LANG=en_US.UTF-8 LC_ALL=en_US.UTF-8 bundle exec jekyll serve --livereload
```

Server runs at: `http://localhost:4000` with automatic browser reload on file changes.

### Installation

**First time setup:**
```bash
# Install Ruby dependencies (requires Homebrew Ruby 3.x, not system Ruby)
/opt/homebrew/opt/ruby/bin/bundle install

# Optional: Install Node.js dependencies for JS minification
npm install
```

### Building

```bash
# Build site (output to _site/)
bundle exec jekyll build

# Build with production environment
JEKYLL_ENV=production bundle exec jekyll build
```

### JavaScript Build (Optional)

```bash
# Minify JavaScript assets
npm run build:js

# Watch and rebuild JS on changes
npm run watch:js
```

## Architecture

### Jekyll Collections System

The site uses **Jekyll Collections** to organize different types of academic content. Each collection is defined in `_config.yml` and has its own directory:

| Collection | Directory | Purpose | Layout |
|------------|-----------|---------|--------|
| `publications` | `_publications/` | Research papers, preprints | `single` |
| `talks` | `_talks/` | Conference presentations | `talk` |
| `teaching` | `_teaching/` | Courses taught/TA'd | `single` |
| `portfolio` | `_portfolio/` | Projects and demos | `single` |
| `posts` | `_posts/` | Blog posts | `single` |
| `pages` | `_pages/` | Static pages (About, CV, etc.) | `single` |

**Collection Configuration** (`_config.yml` lines 200-213):
```yaml
collections:
  teaching:
    output: true
    permalink: /:collection/:path/
  publications:
    output: true
    permalink: /:collection/:path/
  # ... etc
```

### Content Front Matter Structure

Each markdown file requires YAML front matter. Example for a publication:

```yaml
---
title: "Paper Title"
collection: publications
permalink: /publication/2024-10-30-slug
excerpt: 'Brief description for listing pages'
date: 2024-10-30
venue: 'Conference/Journal Name'
paperurl: 'http://url-to-paper.pdf'
citation: 'BibTeX or formatted citation'
---
```

**Key front matter fields:**
- `title`: Display title
- `collection`: Must match collection name
- `permalink`: Custom URL (optional, defaults to collection path)
- `excerpt`: Short description for archive/list views
- `layout`: Usually `single` (default) or `talk`

### Site Configuration

**`_config.yml`** - Main configuration file:
- **Lines 10-17**: Site metadata (title, description, URL, repository)
- **Lines 22-73**: Author profile (bio, social links, academic profiles)
- **Lines 200-213**: Collections definitions
- **Lines 216-271**: Default layouts for each collection
- **Lines 283**: Timezone (America/Los_Angeles)

**`_data/navigation.yml`** - Top navigation menu structure

### Layout Hierarchy

```
_layouts/
├── default.html          # Base layout (HTML structure)
├── single.html           # Most content types (includes author sidebar)
├── talk.html             # Specialized for talks/presentations
├── archive.html          # Collection listing pages
└── compress.html         # HTML minification wrapper
```

**Include components** (`_includes/`):
- `author-profile.html` - Sidebar with bio and social links
- `masthead.html` - Top navigation bar
- `footer.html` - Site footer
- `archive-single.html` - Single item in list views

### Styling

- **SCSS source**: `_sass/` directory
- **Compiled output**: Built by Jekyll during generation
- Based on Minimal Mistakes theme architecture
- Custom styles should go in `_sass/` subdirectories

## Common Workflows

### Adding a New Publication

1. Create file: `_publications/YYYY-MM-DD-shortname.md`
2. Add front matter with title, venue, paperurl, citation
3. Add paper PDF to `files/` directory
4. Optional: Add content below front matter for detailed page

### Adding a Blog Post

1. Create file: `_posts/YYYY-MM-DD-title.md`
2. Front matter must include `layout: single`
3. Use categories and tags for organization

### Bulk Content Generation

Use Python/Jupyter notebooks in `markdown_generator/`:

```bash
cd markdown_generator

# Generate publications from TSV
python publications.py

# Generate talks from TSV
python talks.py
```

Edit `publications.tsv` or `talks.tsv` with structured data, then run scripts to generate markdown files.

### Updating Author Profile

Edit `_config.yml` lines 22-73:
- Update bio, location, employer
- Add/remove social media links (uncomment lines to enable)
- Change avatar image (place in `images/` directory)

### Static Files

- **PDFs, datasets, etc.**: Place in `files/` directory
- **Images**: Place in `images/` directory
- **Profile photo**: Referenced in `_config.yml` as `avatar: "hossein-profile.jpg"`

## Important Notes

### Character Encoding

Ruby 3.4+ requires explicit UTF-8 encoding. Always set `LANG` and `LC_ALL` environment variables when running Jekyll commands to avoid Sass encoding errors.

### GitHub Pages Compatibility

- Uses `github-pages` gem which locks Jekyll and plugin versions
- Ensures local development matches GitHub's build environment
- Do not upgrade Jekyll independently - update `github-pages` gem instead

### Navigation Menu

Edit `_data/navigation.yml` to add/remove menu items. Each entry needs:
```yaml
- title: "Display Name"
  url: /url-path/
```

**Currently Hidden Tabs:**
The "Teaching" and "Guide" tabs have been removed from the navigation menu (as of Oct 2024). To restore them, edit `_data/navigation.yml` and uncomment the following lines at the bottom:
```yaml
# - title: "Teaching"
#   url: /teaching/
# - title: "Guide"
#   url: /markdown/
```

**External Link Configuration:**
Some navigation items link directly to external resources instead of internal pages:
- **CV**: Links directly to PDF (`/files/HosseinRahmani_CV.pdf`) for instant download
- **Talks**: Use `link:` field in front matter to link directly to presentation slides
- **Publications**: Use `link:` field in front matter to link directly to arXiv/paper URL

Example front matter for external links:
```yaml
---
title: "Your Talk Title"
collection: talks
link: "https://docs.google.com/presentation/d/YOUR_ID/edit"
---
```

### Theme Inheritance

This site is based on Minimal Mistakes but heavily customized. Theme files are in `_includes/`, `_layouts/`, and `_sass/` - not in a gem. Updates from upstream theme require manual merging.

### Local vs Production

- Local: `http://localhost:4000` (baseurl is empty)
- Production: `https://rahmani-hossein.github.io` (configured in `_config.yml` line 15)
- GitHub Pages automatically builds on push to master branch