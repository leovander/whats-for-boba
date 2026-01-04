# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Static HTML landing page for What's for Boba, migrated from Shopify to GitHub Pages. This is a pure static site with no e-commerce functionality, API calls, or backend dependencies.

## Target File Structure

```
repository-root/
├── index.html           # Main landing page
├── assets/
│   ├── css/
│   │   └── styles.css   # Consolidated stylesheet
│   ├── images/
│   │   └── logo.svg     # Main logo
│   ├── fonts/           # Custom fonts (if any)
│   └── js/              # Minimal JavaScript (if needed)
├── README.md
└── CLAUDE.md
```

## Development

No build system - edit HTML/CSS/JS files directly. To preview locally, use any static file server:

```bash
python3 -m http.server 8000
# or
npx serve .
```

## Deployment

Push to `main` branch for automatic GitHub Pages deployment.

## Key Constraints

- No Shopify dependencies (remove cart, login, checkout, analytics)
- No e-commerce functionality
- Minimal or no JavaScript
- Mobile-first responsive design
- Accessibility: preserve skip links (#MainContent)
