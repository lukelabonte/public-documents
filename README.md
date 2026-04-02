# documents

A collection of public documents hosted via GitHub Pages.

## View Online

**[Luke's Documents](https://lukelabonte.github.io/public-documents/)**

## Structure

```
documents/
├── index.html              # Document index / landing page
├── styles.css              # Shared design system (load in every page)
├── pets/
│   └── dog-feeding-guide.html
└── nicole/
    └── dashcam-guide.html
```

## Adding a Document

1. Create an HTML file in the appropriate subdirectory (or root for general docs)
2. Link the shared stylesheet in `<head>` (adjust `../` depth as needed):
   ```html
   <link rel="stylesheet" href="../styles.css">
   ```
3. Use shared classes from `styles.css` — see `CLAUDE.md` for the full list of available components
4. Add page-specific styles in a local `<style>` block
5. Add a card entry to `index.html`
6. Commit and push — GitHub Pages deploys automatically
