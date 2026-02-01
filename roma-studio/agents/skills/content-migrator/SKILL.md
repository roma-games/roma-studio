---
name: content-migrator
description: Extract and adapt content from existing documentation into website-ready pages. Use when migrating docs, adapting technical content for web, or reorganizing information from multiple sources.
---

# Content Migrator

Pull content from existing documentation and adapt it for the website. Focus on clarity, readability, and proper structure for web presentation.

## When to Use

- Migrating docs from `docs/` to `website/`
- Adapting technical content for web audiences
- Creating landing page content
- Writing project descriptions
- Organizing information hierarchy

## Content Sources

| Source | Purpose | Target |
|--------|---------|--------|
| `docs/architecture.md` | Tech stack overview | `website/docs/architecture.html` |
| `README.md` | Studio intro | `website/index.html` |
| `agents/README.md` | Team structure | `website/about.html` |
| `docs/coding-standards.md` | Dev guidelines | `website/docs/standards.html` |

## Migration Workflow

1. **Read source doc** - Understand the original content
2. **Adapt for web** - Shorter paragraphs, clearer headings
3. **Add navigation** - Link to related docs
4. **Preserve links** - Update internal links to web paths
5. **Test** - Verify the page renders correctly

## Writing Guidelines

### Landing Page Content

```markdown
# Roma Studio

A game development studio built on OpenClaw agent collaboration.

## What We Build

- **Roma Engine** - 2D game engine in Rust + wgpu
- **Finisterra** - Our first game using the engine
- **Agent Framework** - Multi-agent collaboration system

## Tech Stack

| Layer | Technology |
|-------|------------|
| Engine | Rust + wgpu |
| Client | Rust + Roma |
| Server | Rust + Tokio |

[Get Started →](docs/getting-started.html)
```

### Documentation Pages

```markdown
# Architecture Overview

Roma Studio projects follow a modular architecture...

## Tech Stack

See the table above for technologies used.

## Repository Structure

[Diagram or structure description]

## Key Patterns

- Client-server separation
- Entity-component system
- State machines
```

## Content Review Checklist

- [ ] Clear page title (H1)
- [ ] Logical heading structure (H2, H3)
- [ ] Internal links updated to web paths
- [ ] Code blocks formatted correctly
- [ ] Tables readable on mobile
- [ ] Links to related docs

## Git Workflow

```bash
git checkout -b content/migrate-[page]
# Migrate content
git add website/
git commit -m "Migrate [page] content to website"
```

## Reference

- [Architecture doc](docs/architecture.md) - Primary migration source
- [Main README](README.md) - Studio overview content
- [Agent docs](agents/README.md) - Team and process info
