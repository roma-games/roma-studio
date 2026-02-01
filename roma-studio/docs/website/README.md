# Roma Studio Website

This is the official website for Roma Studio, built as a static site with HTML, CSS, and vanilla JavaScript.

## Structure

```
website/
├── index.html              # Landing page
├── css/
│   ├── style.css           # Main styles
│   └── docs.css            # Documentation styles
├── js/
│   └── main.js             # Main JavaScript
├── docs/
│   ├── index.html          # Docs hub
│   ├── architecture.html   # Architecture docs
│   ├── getting-started.html
│   └── coding-standards.html
└── assets/
    └── images/
```

## Development

To preview the site locally:

```bash
cd website
python3 -m http.server 8000
# Open http://localhost:8000
```

## Deployment

The site is automatically deployed to GitHub Pages via `.github/workflows/deploy.yml` on push to main.

## Tech Stack

- Pure HTML5, CSS3, and JavaScript
- No frameworks - simple and portable
- Responsive design
- Dark mode not currently supported

## Contributing

1. Create a branch: `git checkout -b website/feature-name`
2. Make changes
3. Test locally
4. Submit a PR
