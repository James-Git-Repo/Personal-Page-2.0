# The (un)Stable Net — Multi‑page Static Site

This repo contains a ready‑to‑deploy static website with a blue, business‑clean design.

## Structure

```
.
├── index.html          # Home (project cards + newsletter hero)
├── articles.html       # Articles Hub (upload .html/.md or paste; stores to localStorage)
├── article.html        # Article reader (loads from localStorage or api/posts/<slug>.html)
├── projects.html       # Projects Admin (create cards, export projects.json)
├── msb.html            # Million Slots Billboard landing page
├── bio.html            # Full Bio page
└── api/
    ├── projects.json   # Home will fetch this (fallback to built‑ins if missing)
    └── posts/
        └── emm.html    # Example article body served by your API folder
```

## Local usage

- Open `index.html` in your browser to preview.
- Go to `projects.html` to add/edit projects, **Export JSON**, then replace `api/projects.json` before publishing.
- Go to `articles.html` to upload `.html`/`.md` files, paste content, or add cover images.
  - Articles are saved in your browser (localStorage key: `tsn_articles`).
  - Open an article from the grid → it uses `article.html?slug=<your-slug>`.
  - When ready to publish, click **Download .html** and place it under `api/posts/<slug>.html`.

## GitHub Pages

1. Create a new repo and upload all files as shown above (including the `api/` folder).
2. In GitHub, go to **Settings → Pages**: choose **Deploy from a branch**, select your default branch, and root folder `/`.
3. Your site will be live at `https://<username>.github.io/<repo>/`.

## Sanity checks

Append `?test=1` to pages to run small checks (only logs to console).

- `msb.html?test=1` → confirms 640 micro‑cells render.
- `articles.html?test=1` / `projects.html?test=1` (manually triggered via console if needed).

## Notes

- Everything is static (no server required). Uploads are stored in **localStorage** for in‑browser authoring.
- To make content public, export and copy files into the `api/` folder as described above.
