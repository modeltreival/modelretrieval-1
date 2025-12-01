## Quick Context

- **Project purpose**: static website and documentation for the NTCIR-19 "ModelRetrieval" task (benchmark and task definition).
- **Primary artifacts**: the MkDocs-powered site in `docs/` and site configuration in `mkdocs.yml`.

## How the repo is structured

- `mkdocs.yml`: site configuration (theme: `mkdocs-material`, `pymdownx` extensions, math support). Edit this to change navigation, theme, and global assets.
- `docs/`: documentation pages (edit `.md` files here). Images live under `docs/assets/images` and are referenced from Markdown.
- `main.py`: tiny CLI/entry placeholder (not used by docs). Treat as non-critical for docs work.
- `pyproject.toml`: project metadata (Python >=3.12) and the `mkdocs-material` dependency.

## Developer workflows (concrete commands)

- Create a virtualenv and activate it:
  - `python -m venv .venv`
  - `source .venv/bin/activate`
- Install documentation dependencies locally:
  - `pip install mkdocs mkdocs-material pymdown-extensions`
- Run the local dev server for live edits:
  - `mkdocs serve`
  - (When ready to publish) `mkdocs build` or `mkdocs gh-deploy` to publish to GitHub Pages.

Notes: `mkdocs.yml` enables `pymdownx` features and Mermaid fenced blocks; keep those settings when editing pages that include math or diagrams.

## Conventions & patterns to follow

- Docs are canonical: update the Markdown files in `docs/` rather than editing HTML output.
- Navigation is controlled by `nav` in `mkdocs.yml`. Add new top-level pages by updating `nav` and adding a `docs/*.md` file.
- Math support is provided via `mathjax.js` and `pymdownx.arithmatex`. Write inline math using standard TeX delimiters when needed.
- Custom CSS lives at `stylesheets/extra.css` (referenced by `extra_css` in `mkdocs.yml`). Use that file for site-wide style tweaks.
- Keep images under `docs/assets/images` and reference them with relative paths in Markdown (example: `assets/images/hero_flat.png`).

## What an AI coding agent should know

- The site is static content focused — changes are primarily to Markdown and small asset edits. Avoid speculative refactors of Python code (there's only a stub `main.py`).
- When adding docs pages that include code blocks, the theme already enables `content.code.copy` and `pymdownx.highlight` — follow the existing fenced-code style.
- For diagrams use the `mermaid` fenced block (configured in `mkdocs.yml`). Use the same fence name: ``mermaid`.
- Preserve `mkdocs.yml` YAML keys (theme, markdown_extensions, extra_css/extra_javascript) — changing these can break rendering locally.

## Integration points & external dependencies

- `site_url` and `repo_url` in `mkdocs.yml` indicate GitHub Pages deployment via `mkdocs gh-deploy` (common pattern).
- `pyproject.toml` lists `mkdocs-material` as a dependency; use `pip` to install the docs toolchain rather than assuming other tooling (no lockfile present).

## Examples (explicit)

- To add a new page called "Evaluation":

  1. Create `docs/evaluation.md` with content.
  2. Add `- Evaluation: evaluation.md` under `nav:` in `mkdocs.yml`.
  3. Run `mkdocs serve` and verify locally.

- To include a Mermaid diagram in `docs/tasks.md`:

  ````markdown
  ```mermaid
  graph LR
    A --> B
  ```
  ````

  ```

  ```

## Safety and scope

- Do not attempt to re-architect the site as an application — keep changes limited to docs, assets, and the MkDocs config unless an explicit task requires otherwise.

If anything in this file is unclear or you want more details (tests, CI, or publishing specifics), tell me which area to expand and I'll update the file.
