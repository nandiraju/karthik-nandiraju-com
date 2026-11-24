# Karthik Nandiraju — Agent & Developer Guide (Static HTML)

Plain static HTML + CSS site for **https://karthik.nandiraju.com**, deployed by GitHub Pages.
No build step and no framework — the files you see are the files that ship.
This folder is a normal git checkout of its GitHub repo — edit, commit, and push.

## Deploy
Pushing to `main` triggers `.github/workflows/deploy.yml`, which uploads the repo contents
to GitHub Pages (Pages is enabled in "workflow" build mode). No Jekyll (`.nojekyll`).
Git auth: `origin` is a clean HTTPS URL; use your own GitHub credentials.

## Structure
| Path | Purpose |
|---|---|
| `index.html` | Home page (full HTML; SEO block lives between `<!--seo-head-->` markers) |
| `<slug>/index.html` | One folder per additional page |
| `styles.css` | Site styles (shared by every page) |
| `sitemap.xml`, `robots.txt`, `CNAME` | SEO + custom-domain files at the site root |
| `images/`, `favicon*`, `apple-touch-icon.png` | Brand & social assets |

## Adding a page
1. Create `<slug>/index.html` (copy an existing page, keep one `<h1>`, a unique title/description, and a canonical URL).
2. Add its URL to `sitemap.xml`.
3. Add a nav link to every page's header.

## Working alongside the Site Launch Agent
The agent regenerates files listed under `generatedFiles` in `site-agent.json` when it re-runs.
**To keep your edits, add the file paths to `preserve` in `site-agent.json`** — the agent will never overwrite them.
GA4 tag and Search Console verification are managed by the site agent.
