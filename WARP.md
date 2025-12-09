# WARP.md

This file provides guidance to WARP (warp.dev) when working with code in this repository.

## Project Overview

This is a static single-page CV/portfolio website for Nick Foard. The entire application is contained in `index.html` - a self-contained HTML file with embedded CSS and JavaScript.

## Project Structure

```
.
├── index.html          # Main CV website (single-file application)
├── README.md           # Project documentation
├── WARP.md            # This file - guidance for WARP AI
└── docs/              # Documentation and assets
    └── Nick Foard CV.pdf  # PDF version of CV
```

## Architecture

**Single-File Architecture**: The project uses a monolithic single-file approach where all HTML structure, CSS styles, and JavaScript functionality are contained within `index.html`. There is no build process, no external dependencies, and no package management.

**Key Sections**:
- **Hero Section**: Animated hero with contact information and gradient text effects
- **Experience Timeline**: Chronological work history with visual timeline (30+ years of experience)
- **Skills & Tools**: Tag-based display of technical competencies and platforms
- **Additional Info**: Education, certifications, hobbies, and video presentations grid
- **CTA Section**: Call-to-action for contact

**Styling Approach**: 
- CSS custom properties (CSS variables) defined in `:root` for theming (colors, gradients)
- Dark theme with primary colors: indigo (#6366f1), cyan (#06b6d4)
- Animation-heavy design with intersection observers for scroll-triggered reveals
- Fully responsive with mobile breakpoints at 768px

**JavaScript Features**:
- Intersection Observer for section visibility animations
- Smooth scrolling for anchor links
- No external libraries or frameworks

## Development Workflow

**No Build Required**: This is a static HTML file that can be opened directly in a browser or served with any HTTP server.

**Testing Locally**:
```powershell
# Option 1: Open directly
Start-Process "index.html"

# Option 2: Use Python HTTP server (if Python installed)
python -m http.server 8000

# Option 3: Use PowerShell (Windows 10+)
# Requires IIS features enabled
```

**Version Control**: Standard Git workflow. All changes are to `index.html`.

## Making Changes

**Adding New Experience**: Locate the `.timeline` section and add new `.timeline-item` divs following the existing pattern. Timeline items are ordered chronologically from newest (top) to oldest (bottom).

**Updating Contact Info**: Modify the `.contact-links` div in the `.hero-content` section. Email, phone, and location are hardcoded.

**Modifying Colors/Theme**: Update CSS custom properties in the `:root` selector at the top of the `<style>` block. Key variables:
- `--primary`: Main accent color
- `--accent`: Secondary accent color  
- `--bg`: Background color
- `--text`: Text color

**Adding Skills/Tools**: Add new `<span class="skill-tag">` elements to the `.skills-container` in either the Skills or Tools section.

**Content Updates**: All content is inline HTML. Search for the relevant section by ID or class name and modify the markup directly.

## Deployment

This static site can be deployed to:
- GitHub Pages (push to gh-pages branch or configure in repo settings)
- Any static hosting service (Netlify, Vercel, Azure Static Web Apps, AWS S3)
- Traditional web hosting (upload via FTP)

No build or compilation step is required before deployment.
