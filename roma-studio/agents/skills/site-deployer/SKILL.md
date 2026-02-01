---
name: site-deployer
description: Deploy static websites to GitHub Pages and manage CI/CD pipelines. Use when setting up deployment, configuring GitHub Actions, or publishing website updates.
---

# Site Deployer

Deploy static websites to GitHub Pages and manage continuous deployment pipelines.

## When to Use

- Setting up initial GitHub Pages deployment
- Configuring CI/CD for automatic deploys
- Publishing website updates
- Troubleshooting deployment issues
- Managing custom domains

## GitHub Pages Setup

### Enable GitHub Pages

1. Go to repository Settings → Pages
2. Source: "GitHub Actions"
3. Select workflow (see below)

### Workflow File (`.github/workflows/deploy.yml`)

```yaml
name: Deploy to GitHub Pages

on:
    push:
        branches: [main]
    workflow_dispatch:

permissions:
    contents: read
    pages: write
    id-token: write

concurrency:
    group: "pages"
    cancel-in-progress: true

jobs:
    deploy:
        environment:
            name: github-pages
            url: ${{ steps.deployment.outputs.page_url }}
        runs-on: ubuntu-latest
        steps:
            - name: Checkout
              uses: actions/checkout@v4

            - name: Setup Pages
              uses: actions/configure-pages@v4

            - name: Upload artifact
              uses: actions/upload-pages-artifact@v3
              with:
                  path: 'website/'

            - name: Deploy to GitHub Pages
              id: deployment
              uses: actions/deploy-pages@v4
```

## Local Testing

```bash
# Test locally with a simple server
cd website
python3 -m http.server 8000
# Open http://localhost:8000

# Or use a static site tool
npx serve .
```

## Deployment Checklist

- [ ] All HTML files render correctly
- [ ] CSS/JS assets load properly
- [ ] Internal links work
- [ ] No broken images or resources
- [ ] Mobile layout works
- [ ] CI/CD workflow passes

## Publishing Updates

```bash
git checkout main
git pull origin main

# Create deployment commit
git add -A
git commit -m "Deploy website updates"

# Push to trigger CI/CD
git push origin main
# GitHub Actions automatically deploys
```

## Custom Domain (Optional)

```yaml
# In deploy.yml, add:
- name: Setup Pages
  uses: actions/configure-pages@v4
  with:
      static_site: true

# Add CNAME file to website/
echo "docs.roma.games" > website/CNAME
```

## Troubleshooting

| Issue | Solution |
|-------|----------|
| 404 on pages | Check workflow ran; wait 1-2 min |
| CSS not loading | Verify paths are absolute (`/css/style.css`) |
| Build failed | Check Actions tab for error logs |
| Old content showing | Hard refresh (Cmd+Shift+R) or clear cache |

## Reference

- [GitHub Pages docs](https://docs.github.com/en/pages)
- [Actions workflow syntax](https://docs.github.com/en/actions/using-workflows/workflow-syntax-for-github-actions)
- Repository: `roma-games/roma-games.github.io` (or similar)
