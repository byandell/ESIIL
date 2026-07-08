# AGENTS.md — byandell/ESIIL

Brian Yandell's ESIIL
(Environmental Data Science Innovation and Inclusion Lab)
collaboration hub, forked from
[CU-ESIIL/Postdoc_OASIS](https://github.com/CU-ESIIL/Postdoc_OASIS).
The published site lives at <https://byandell.github.io/ESIIL>.

---

## Branch Workflow

| Branch | Purpose | Edit directly? |
|--------|---------|----------------|
| `main` | Source content: Markdown, config, assets | **Yes** — all edits go here |
| `gh-pages` | Built HTML output, served by GitHub Pages | **No** — auto-generated; never edit manually |

**On every push to `main`**, the GitHub Action in
`.github/workflows/gh-pages.yml` runs `mkdocs gh-deploy --force`,
which builds the site and force-pushes the output to the `gh-pages` branch
(in its `docs/` folder).
Manual edits to `gh-pages` will be overwritten on the next deploy.

---

## Repository Layout

```
ESIIL/
├── docs/                        # Source Markdown (edit these)
│   ├── index.md                 # Home page
│   ├── EarthDataAnalytics/
│   │   └── index.md             # Earth Data Analytics projects page
│   ├── resources/               # Reference docs, notes, manuscripts
│   └── assets/                  # Logos, images, stylesheets
├── mkdocs.yml                   # MkDocs + Material theme config
├── requirements.txt             # Python deps for mkdocs build
├── .github/
│   └── workflows/
│       ├── gh-pages.yml         # Auto-deploy to gh-pages on main push
│       ├── fetch-template.yml   # Upstream template sync
│       └── build-and-push-jupyterlab-image.yml
└── docker/                      # Docker image definitions
```

---

## Key Files

- **`mkdocs.yml`** — site name, URL (`https://byandell.github.io/ESIIL`),
nav tree, Material theme settings. Update `nav:` here when adding new pages.
- **`docs/index.md`** — landing page for the published site.
- **`docs/EarthDataAnalytics/index.md`** — projects from the 2024 Earth Data
Analytics course (First Map, Climate, Species Distribution, Redlining, Habitat).
- **`requirements.txt`** — Python packages installed by the CI workflow before
building (includes `mkdocs`, `mkdocs-material`, `mkdocs-jupyter`, etc.).

---

## Local Development

Preview the site locally before pushing to `main`:

```bash
# Install dependencies (once)
pip install -r requirements.txt

# Serve with live reload at http://127.0.0.1:8000
mkdocs serve
```

`mkdocs serve` watches `docs/` and `mkdocs.yml` for changes and hot-reloads the
browser.
Stop it with `Ctrl+C`. Nothing is written to `gh-pages` — it is purely local.

---

## Making Changes

1. **Edit Markdown** under `docs/` on the `main` branch.
2. **Add new pages** by creating a `.md` file under `docs/` and adding it to the
`nav:` section in `mkdocs.yml`.
3. **Embed HTML artifacts** (interactive maps, plots) by placing `.html` files
in the appropriate `docs/` subdirectory and referencing them with
`<embed type="text/html" src="file.html" ...>` in Markdown.
4. **Commit and push to `main`** — the GitHub Action builds and deploys
automatically.
Monitor progress in the repo's **Actions** tab.

Do **not** commit directly to `gh-pages`.

---

## Upstream Template Sync (`fetch-template.yml`)

The workflow `.github/workflows/fetch-template.yml` syncs changes from the
upstream template repo
([CU-ESIIL/Postdoc_OASIS](https://github.com/CU-ESIIL/Postdoc_OASIS))
into `main`.

**Trigger**: `workflow_dispatch` only — it must be run manually from the repo's
**Actions** tab. It never runs automatically.

**What it does**:
1. Fetches the upstream template's `main` branch.
2. Attempts a merge with `--allow-unrelated-histories`.
3. Runs `git checkout --ours .` — local files always win any conflict.
4. Commits and pushes to `main`, which then triggers the `gh-pages.yml` deploy.

**Key implication**: Because `--ours` is applied unconditionally,
this sync **cannot overwrite your customizations**.
Its main value is pulling in brand-new files added to the template that don't
yet exist locally (e.g., new resource docs, workflow updates).
Run it when you want to check for upstream improvements,
but it is safe to skip if the upstream template is inactive.

---

## Site Configuration (mkdocs.yml highlights)

- **Theme**: Material (`mkdocs-material`)
- **Plugins**: `search`, `mkdocstrings`, `git-revision-date`, `mkdocs-jupyter`
(for `.ipynb` rendering)
- **Edit URI**: `edit/main/docs/` — the "edit this page" links in the rendered
site point to `main`.
- **Requires** `GH_TOKEN` secret in repo settings for the deploy step to push to
`gh-pages`.

---

## Projects Covered

- **First Map** — interactive UW-Madison campus map (Python + R)
- **Climate Project 1** — climate coding challenge notebooks
- **Species Distribution** — Sandhill and Siberian Crane migration maps
(GBIF data)
- **Redlining Project** — Madison, WI NDVI + redlining grades; also `landmapy`
Python package and `geospatial` R package
- **Habitat Project** — habitat suitability modeling (Blue Stem grass;
Buffalo Gap & Oglala National Grasslands); work in progress

External code lives in separate repos under
[byandell-envsys](https://github.com/byandell-envsys)
and
[byandell-Tribal](https://github.com/byandell-Tribal)
GitHub organizations.
