# N.O.V.A. Tracker

A single-page tracking dashboard for the **N.O.V.A.** project (Normalize · Organize · Verify · Archive) — the pipeline that consolidates CABAL source material into structured Obsidian notes.

Live page: `index.html` (static, no build step, no dependencies besides the Mermaid CDN script for the flow diagram).

Source of truth is the Obsidian vault at `Documents/Asgard/Asgard/NOVA/`:
- `NOVA - Project Hub.md`
- `NOVA - Project Plan.md`
- `NOVA - Decision Log.md`

This page is a **snapshot** of that content for sharing outside the vault. It does not auto-sync — update `index.html` by hand (or ask Claude to regenerate it) when the vault notes change.

## Push to GitHub

This folder is already a local git repo with everything committed. To publish it:

```bash
# from this folder
git remote add origin https://github.com/<your-username>/nova-tracker.git
git branch -M main
git push -u origin main
```

(Create the empty repo on GitHub first — no README/license/gitignore, since this folder already has its own.)

## Enable GitHub Pages

1. On GitHub, go to the repo's **Settings → Pages**
2. Under **Build and deployment**, set **Source** to "Deploy from a branch"
3. Branch: `main`, folder: `/ (root)`
4. Save — GitHub gives you a URL like `https://<your-username>.github.io/nova-tracker/` within a minute or two
