<!-- copilot-instructions for hushpix.github.io -->
# Repository overview

- **Type:** Simple static personal site (single-page/root `index.html` with a `thanks.html`).
- **Entry point:** `index.html` at repo root. CSS lives in `assets/css/cssStyles.css`. Images and media live under `assets/images/` and `assets/audio/`.

# Key patterns and architecture

- **No build step / plain HTML:** Files are served as static assets. There is no bundler, package.json, or task runner present.
- **Root-relative links:** The site uses absolute root paths (e.g., `/assets/css/cssStyles.css`) — keep links consistent with the leading `/` to match GitHub Pages hosting.
- **Minimal JS:** There is little-to-no JavaScript in the repository. Treat the project as content-first; avoid adding heavy front-end frameworks.

# Files to inspect when modifying behavior or style

- `index.html` — site entry; metadata and stylesheet link.
- `thanks.html` — small secondary page used by the site.
- `assets/css/cssStyles.css` — primary stylesheet. Example: `.gradientBg` provides the page background.
- `assets/images/`, `assets/audio/`, `assets/fonts/` — static media assets.

# Developer workflows (how to run / preview locally)

Use a simple static server from the repo root.

PowerShell example (works on Windows):

```powershell
cd C:\Users\Hushpix\Documents\GitHub\hushpix.github.io
python -m http.server 8000
# then open http://localhost:8000 in your browser
```

Or use VS Code Live Server extension to preview with live reload. There are no build/test steps in this repo.

# Code-style / conventions specific to this repo

- Keep file structure unchanged: move or rename assets only when updating all references (HTML `href`/`src` paths use root `/assets/...`).
- CSS is global (single stylesheet). Prefer adding selectors to `cssStyles.css` rather than creating many separate files.
- Avoid adding package managers or node_modules unless you add a clear build step and update this doc.

# Integration points & deploy notes

- Hosting expected: GitHub Pages for `hushpix.github.io` (repo name suggests user/organization site). Deployment is simply pushing to the default branch — no CI is required.
- If you introduce tooling (SASS, bundlers), document the new commands here and update README.

# Guidance for AI agents

- Do not make large structural changes without explaining them in a PR comment — this is a small, static site and reviewers expect minimal diffs.
- When changing paths, update all HTML references and verify local preview loads images/CSS.
- Example safe change: tweak `assets/css/cssStyles.css` styles (e.g., `.gradientBg`) to adjust visuals.
- Example risky change: adding a JS framework or build pipeline — propose in an issue first.

# References & examples

- Entry file: `index.html`
- Stylesheet: `assets/css/cssStyles.css` (see `.gradientBg`)
- Secondary page: `thanks.html`

If anything here is unclear or you want me to expand any section (deploy, PR rules, or testing), tell me which part to improve.
