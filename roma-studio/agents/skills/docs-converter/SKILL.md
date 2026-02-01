---
name: docs-converter
description: Convert Markdown documentation to HTML for static websites. Use when building documentation sites, publishing docs, or converting existing .md files to web-ready HTML.
---

# Docs Converter

Transform Markdown files into clean, readable HTML for static websites. Focus on documentation sites, API references, and technical content.

## When to Use

- Converting .md docs to .html
- Building documentation navigation
- Creating doc index pages
- Formatting code blocks and examples
- Generating table of contents

## Markdown to HTML Conversion

### Basic Conversion

```bash
# Using commonmark or similar
pandoc README.md -o docs/README.html
# Or use a simple Python script for custom formatting
```

### Manual HTML Structure

Each documentation page needs:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Documentation - [Title]</title>
    <link rel="stylesheet" href="/css/docs.css">
</head>
<body>
    <div class="docs-layout">
        <aside class="docs-sidebar">
            <nav>
                <a href="index.html">← Back to Docs</a>
                <ul>
                    <li><a href="architecture.html">Architecture</a></li>
                    <li><a href="getting-started.html">Getting Started</a></li>
                    <li><a href="api-reference.html">API Reference</a></li>
                </ul>
            </nav>
        </aside>
        <main class="docs-content">
            [Converted Markdown Content]
        </main>
    </div>
</body>
</html>
```

## Documentation CSS

```css
.docs-layout {
    display: flex;
    min-height: 100vh;
}

.docs-sidebar {
    width: 250px;
    padding: 2rem;
    border-right: 1px solid #e5e7eb;
    position: sticky;
    top: 0;
    height: 100vh;
    overflow-y: auto;
}

.docs-content {
    flex: 1;
    max-width: 800px;
    padding: 2rem 4rem;
}

.docs-content h1 { font-size: 2rem; margin-bottom: 1rem; }
.docs-content h2 { font-size: 1.5rem; margin-top: 2rem; }
.docs-content h3 { font-size: 1.25rem; margin-top: 1.5rem; }
.docs-content pre { background: #f3f4f6; padding: 1rem; border-radius: 4px; overflow-x: auto; }
.docs-content code { font-family: ui-monospace, monospace; }
.docs-content table { width: 100%; border-collapse: collapse; }
.docs-content th, .docs-content td { border: 1px solid #e5e7eb; padding: 0.5rem; text-align: left; }
```

## Content to Convert

Source files in `docs/`:
- `architecture.md` - System architecture overview
- `coding-standards.md` - Rust conventions
- `communication.md` - Agent protocols

Each becomes a corresponding `.html` file in `website/docs/`.

## Git Workflow

```bash
git checkout -b docs/convert-[topic]
# Convert files, test locally
git add website/docs/
git commit -m "Convert [topic] docs to HTML"
```

## Reference

- [Markdown specification](https://commonmark.org/)
- [Architecture source](docs/architecture.md)
