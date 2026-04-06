# documents

A static site hosted via GitHub Pages. Used to share public documents with others.

## Structure

- `index.html` — document index / landing page
- `styles.css` — **shared design system** (load this in every page)
- `preview.png` — shared OG preview image (used by all pages for link previews); to regenerate: edit `preview.svg`, run `rsvg-convert -w 1200 -h 630 preview.svg -o preview.png`, then delete the SVG (only PNG is committed)
- `pets/` — pet-related guides
- `nicole/` — guides for Nicole

## Style

All documents share a design system defined in `styles.css`:
- **Fonts:** DM Serif Display (headings) + DM Sans (body) via Google Fonts
- **Background:** `#FAF7F2` warm off-white (`--bg`)
- **Accent:** `#B5632E` warm orange-brown (`--accent`)
- **Max width:** 800px centered container
- **Border radius:** 12px cards (`--radius`)

## Adding Documents

1. Create the HTML file in the appropriate subdirectory (or root for general docs)
2. In `<head>`, load the shared CSS:
   ```html
   <link href="https://fonts.googleapis.com/css2?family=DM+Serif+Display&family=DM+Sans:ital,wght@0,400;0,500;0,600;0,700;1,400&display=swap" rel="stylesheet">
   <link rel="stylesheet" href="../styles.css">  <!-- adjust path depth as needed -->
   ```
3. Add OG/Twitter Card meta tags in `<head>` for rich link previews (iMessage, Slack, etc.):
   ```html
   <meta name="description" content="[page description]">
   <meta property="og:title" content="[Page Title]">
   <meta property="og:description" content="[page description]">
   <meta property="og:type" content="website">
   <meta property="og:url" content="https://lukelabonte.github.io/documents/[path]">
   <meta property="og:image" content="https://lukelabonte.github.io/documents/preview.png">
   <meta name="twitter:card" content="summary_large_image">
   <meta name="twitter:title" content="[Page Title]">
   <meta name="twitter:description" content="[page description]">
   <meta name="twitter:image" content="https://lukelabonte.github.io/documents/preview.png">
   ```
4. Use the shared classes — see `styles.css` for the full list. Key ones:
   - Layout: `.container`, `.back-btn`, `.header`, `.header-icon`, `.updated`, `.divider`, `.footer-bar`
   - Content: `.section-heading`, `.tldr`, `.tldr-title`, `.note`, `.note-green/orange/blue/red/purple`, `.badge`, `.badge-orange`, `.highlight-row`
5. Add page-specific styles in a `<style>` block — avoid redefining anything already in `styles.css`
6. Add a card entry to `index.html`
7. Commit and push — GitHub Pages deploys automatically
