---
name: new-document
description: This skill should be used when the user asks to "add a new document", "create a new page", "scaffold a new guide", "add a new HTML file", or says things like "make a page for X" or "I want to add a guide about Y" in this static site repository.
version: 0.1.0
---

# New Document Scaffold

Scaffold a new HTML document page in this static site, following all project conventions. Every page must include the shared CSS, OG meta tags, back button, and a card entry in `index.html`.

## Steps

### 1. Determine the path and title

Ask the user (or infer from context):
- **Subdirectory:** `pets/`, `nicole/`, or root — matches the audience/topic
- **Filename:** lowercase, hyphenated (e.g., `cat-care-guide.html`)
- **Page title:** shown in `<h1>` and OG tags
- **Short description:** one sentence, used in `og:description` and the `index.html` card

### 2. Create the HTML file

Use this exact boilerplate. Adjust the `../styles.css` path depth if the file is in a subdirectory (root-level files use `./styles.css`):

```html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>[Page Title]</title>
<meta name="description" content="[Short description]">
<meta property="og:title" content="[Page Title]">
<meta property="og:description" content="[Short description]">
<meta property="og:type" content="website">
<meta property="og:url" content="https://lukelabonte.github.io/documents/[path/to/file.html]">
<meta property="og:image" content="https://lukelabonte.github.io/documents/preview.png">
<meta name="twitter:card" content="summary_large_image">
<meta name="twitter:title" content="[Page Title]">
<meta name="twitter:description" content="[Short description]">
<meta name="twitter:image" content="https://lukelabonte.github.io/documents/preview.png">
<link href="https://fonts.googleapis.com/css2?family=DM+Serif+Display&family=DM+Sans:ital,wght@0,400;0,500;0,600;0,700;1,400&display=swap" rel="stylesheet">
<link rel="stylesheet" href="../styles.css">
<style>
  /* Page-specific styles go here — do not redefine anything already in styles.css */
</style>
</head>
<body>

<div class="container">

  <a href="../index.html" class="back-btn">All Documents</a>

  <div class="header">
    <div class="header-icon">[EMOJI]</div>
    <h1>[Page Title]</h1>
    <div class="subtitle">[Subtitle or tagline]</div>
    <div class="updated">Last updated: [Date]</div>
  </div>

  <!-- Page content here -->

</div>

</body>
</html>
```

### 3. Add a card to `index.html`

Find the correct `<div class="section">` block (Pets, Nicole, or create a new one) and add:

```html
<a href="[path/to/file.html]" class="doc-card">
  <div class="doc-icon">[EMOJI]</div>
  <div class="doc-info">
    <div class="doc-title">[Page Title]</div>
    <div class="doc-description">[Short description]</div>
  </div>
  <div class="doc-arrow">→</div>
</a>
```

### 4. Confirm with the user

After scaffolding, tell the user:
- The file path created
- Any placeholder values that still need to be filled in (emoji, subtitle, content)
- That the card has been added to `index.html`

## Available Shared Classes

Use these from `styles.css` — do not redefine them:

**Layout:** `.container`, `.back-btn`, `.header`, `.header-icon`, `.updated`, `.divider`, `.footer-bar`

**Content:** `.section-heading`, `.tldr`, `.tldr-title`, `.note`, `.note-green`, `.note-orange`, `.note-blue`, `.note-red`, `.note-purple`, `.badge`, `.badge-orange`, `.highlight-row`

**Tables:** standard `<table>` — styles are applied globally in `styles.css`

Add page-specific components (cards, grids, collapsibles, etc.) in the `<style>` block only.

## Design Tokens

Reference these CSS variables for page-specific styles:

| Variable | Value | Use |
|----------|-------|-----|
| `--bg` | `#FAF7F2` | Page background |
| `--surface` | `#FFFFFF` | Card/panel background |
| `--surface-alt` | `#F5F0E8` | Subtle backgrounds |
| `--accent` | `#B5632E` | Primary accent color |
| `--accent-bg` | `#FDF3EB` | Light accent background |
| `--text` | `#2D2518` | Primary text |
| `--text-muted` | `#6B6152` | Secondary text |
| `--border` | `#E4DDD1` | Borders |
| `--radius` | `12px` | Card border radius |
| `--shadow-sm` | — | Subtle shadow |
| `--shadow-md` | — | Elevated shadow |
