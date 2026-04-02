# documents

A static site hosted via GitHub Pages. Used to share public documents with others.

## Structure

- `index.html` — document index / landing page
- `pets/` — pet-related guides

## Style

All documents use a consistent design system:
- **Fonts:** DM Serif Display (headings) + DM Sans (body) via Google Fonts
- **Background:** `#FAF7F2` warm off-white
- **Accent:** `#B5632E` warm orange-brown
- **Max width:** 800px centered container
- **Border radius:** 12px cards

When creating new documents, match the existing style in `pets/dog-feeding-guide.html`.

## Adding Documents

1. Create the HTML file in the appropriate subdirectory (or root for general docs)
2. Add a card entry to `index.html`
3. Update `README.md` to reflect the new document and any structural changes
4. Commit and push — GitHub Pages deploys automatically
