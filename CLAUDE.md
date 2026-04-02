# documents

A static site hosted via GitHub Pages. Used to share public documents with others.

## Structure

- `index.html` — document index / landing page
- `styles.css` — **shared design system** (load this in every page)
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
3. Use the shared classes (`.header`, `.container`, `.tldr`, `.note`, `.badge`, `.section-heading`, `.updated`, `.footer-bar`, `.highlight-row`, etc.) — see `styles.css` for the full list
4. Add page-specific styles in a `<style>` block — avoid redefining anything already in `styles.css`
5. Add a card entry to `index.html`
6. Update `README.md` to reflect the new document and any structural changes
7. Commit and push — GitHub Pages deploys automatically
