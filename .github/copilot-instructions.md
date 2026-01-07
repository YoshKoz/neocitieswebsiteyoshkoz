# Copilot Instructions for YoShKoZ's 80's Paradise

## Project Overview
Static personal website hosted on Neocities with an 80s retro/synthwave aesthetic. Pure HTML, CSS, and vanilla JavaScript—no build tools or frameworks. This is Yoshi Tacke's personal site showcasing hobbies, professional background, and 80s nostalgia.

## Architecture
- **Multi-page static site**:
  - `index.html` – Home page with 3-column grid layout
  - `about.html` – Full bio, experience, languages, contact
  - `skills.html` – Skill bars, tools, certifications, portfolio
  - `links.html` – Webring-style links page, 88x31 buttons
  - `guestbook.html` – Visitor messages (demo form)
- **Shared styles**: `index_files/style.css` – CSS custom properties define the color palette
- **Assets**: `index_files/` – local images and styles; external GIFs via Giphy CDN
- **Page-specific styles**: Inline `<style>` blocks in subpages extend base styles

## Visual Design System

### Color Variables (defined in `:root` in style.css)
```css
--neon-pink: #ff1493;    /* Primary accent, borders, headings */
--neon-blue: #00d4ff;    /* Secondary accent, hover states */
--neon-purple: #9d00ff;  /* Gradients, decorative elements */
--text-primary: #00ffcc; /* Body text */
--text-secondary: #ff69b4; /* Labels, secondary text */
```

### Typography
- Headings: `Press Start 2P` (pixel font from Google Fonts)
- Body: `Segoe UI, Orbitron, sans-serif`

### Key CSS Patterns
- Cards use `.card` base class; add `.interactive-card` for hover effects
- Neon glow effects via `text-shadow` and `box-shadow` with color variables
- `.scanlines` overlay creates CRT monitor effect (include in all pages)
- Animations: `flicker`, `pulse`, `blink-slow` for authentic retro feel

## Layout Structure (index.html)
```
.page-container (full viewport, flex column)
├── header (avatar, title, visitor counter)
├── main.main-grid (3-column CSS grid)
│   ├── .column (left: About, Music, Hobbies)
│   ├── .column.center-column (Favorites, featured GIF)
│   └── .column (right: Movies, Games, Updates)
└── footer (About, Guestbook, LinkedIn, Neocities links)
```

## Conventions

### Adding New Pages
1. Copy the `<head>` section from `index.html` (fonts, shared CSS)
2. Include `.scanlines` div for CRT effect
3. Add page-specific styles in inline `<style>` block
4. Include `.back-link` element linking to `index.html`
5. Set `body { overflow: auto; }` for scrollable subpages

### Adding New Sections (on index.html)
1. Create a `<section class="card interactive-card">` inside appropriate `.column`
2. Use `<h2>` with emoji prefix for section headings
3. Follow existing patterns: `.compact-list` for lists, `.games-grid` for icon grids

### Marquee/Ticker Elements
- Use `<marquee behavior="alternate" scrollamount="2">` for bouncing text
- Wrap in `.music-ticker` class for purple background styling
- Include emoji decorations (🎶) for visual flair

### External Resources
- GIFs: Giphy CDN URLs (use HTTPS)
- Fonts: Google Fonts CDN (Press Start 2P, Orbitron)
- Badges: Archive.org for retro badges, Neocities cat logo

### JavaScript
- Minimal vanilla JS at bottom of HTML files
- Cursor sparkle trail effect on `mousemove` (index.html only)
- Hover scale transform on `.interactive-card` elements
- Form handling with `alert()` for static site demos

## Owner Information
- **Name**: Yoshi Tacke
- **Location**: Arnhem-Nijmegen, Netherlands
- **Contact**: yoshitacke@outlook.com, linkedin.com/in/yoshitacke
- **Skills**: 3D Printing, DTP, Web Dev, Video Editing, DJ/Music
- **Martial Arts**: Jodo 4th Dan, Kendo (Kendo Kai Higashi)

## Deployment
Upload all HTML files and `index_files/` folder directly to Neocities. No build step required.
