---
name: website-builder
description: HTML/CSS/JS scaffolding, layouts, and components for static websites. Use when creating new pages, navigation, styling, or frontend components for the Roma Studio website.
---

# Website Builder

Build static websites with HTML, CSS, and vanilla JavaScript. No frameworks—keep it simple and portable.

## When to Use

- Creating new pages (index, docs, about, etc.)
- Building navigation structures
- Styling with CSS (responsive, clean design)
- Adding interactive components
- Setting up layouts for documentation

## Project Structure

```
website/
├── index.html          # Landing page
├── docs/
│   ├── index.html      # Documentation hub
│   ├── architecture.html
│   └── ...
├── css/
│   └── style.css
├── js/
│   └── main.js
├── assets/
│   ├── images/
│   └── icons/
└── _includes/          # For reusable components (optional)
```

## HTML Patterns

### Base Template

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Roma Studio - [Page Title]</title>
    <link rel="stylesheet" href="/css/style.css">
</head>
<body>
    <nav class="site-nav">
        <a href="/" class="logo">Roma Studio</a>
        <ul class="nav-links">
            <li><a href="/docs/">Docs</a></li>
            <li><a href="https://github.com/roma-games">GitHub</a></li>
        </ul>
    </nav>
    <main>[content]</main>
    <footer class="site-footer">
        <p>&copy; 2026 Roma Studio. Built with agent collaboration.</p>
    </footer>
</body>
</html>
```

### Documentation Page

```html
---
layout: default
title: [Page Title]
---

# [Page Title]

[Content...]

## See Also

- [Related Page](related.html)
- [Back to Docs](index.html)
```

## CSS Guidelines

- Use CSS variables for colors and spacing
- Mobile-first responsive design
- Clean typography (system fonts preferred)
- Minimal color palette (dark mode optional)

```css
:root {
    --primary: #6366f1;
    --text: #1f2937;
    --bg: #ffffff;
    --code-bg: #f3f4f6;
    --max-width: 800px;
}

body {
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
    line-height: 1.6;
    color: var(--text);
    background: var(--bg);
    margin: 0;
}

main {
    max-width: var(--max-width);
    margin: 0 auto;
    padding: 2rem;
}

pre {
    background: var(--code-bg);
    padding: 1rem;
    border-radius: 4px;
    overflow-x: auto;
}
```

## Git Workflow

```bash
# Create branch for changes
git checkout -b website/[feature-name]

# Make changes, then
git add website/
git commit -m "Add [feature] to website"

# Push and create PR
git push origin website/[feature-name]
```

## Reference Files

- [Existing docs](docs/architecture.md) - Content to migrate
- [Design inspiration](https://github.com/roma-games) - Roma GitHub org
