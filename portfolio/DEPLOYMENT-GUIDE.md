# Portfolio Deployment Guide

## How to deploy to ireney2050.github.io

### Option A: Replace your existing repo contents
1. Back up your current repo (or create a branch)
2. Delete all existing files in your `ireney2050.github.io` repo
3. Copy all files from this `portfolio/` folder into the repo root
4. Commit and push — GitHub Pages will build automatically

### Option B: Fresh start
1. Clone your repo: `git clone https://github.com/ireney2050/ireney2050.github.io.git`
2. Remove old files, copy in the new portfolio files
3. Push to `main` branch

### Testing locally (optional)
```bash
cd portfolio
bundle install
bundle exec jekyll serve
```
Then visit http://localhost:4000

## File structure
```
_config.yml          # Jekyll configuration
_layouts/
  default.html       # Base HTML layout
  project.html       # Individual project page layout
_includes/
  nav.html           # Navigation bar
  footer.html        # Footer
_projects/           # One .md file per project (8 total)
assets/css/
  style.css          # All styles
index.html           # Homepage (hero, skills, projects, experience, contact)
Gemfile              # Ruby dependencies
```

## Customisation notes
- To add your resume as a download: place the PDF in `assets/` and add a button link in the hero section
- To add a headshot: place the image in `assets/` and add an `<img>` tag in the hero section
- Colours can be changed via CSS variables at the top of `style.css`
- To add/remove projects: create/delete files in `_projects/` and update `index.html`
