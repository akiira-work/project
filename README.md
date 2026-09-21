# N.O.V.A. Tracker

A single-page tracking dashboard for the **N.O.V.A.** project (Normalize · Organize · Verify · Archive) — the pipeline that consolidates CABAL source material into structured Obsidian notes.

Live page: `index.html` (static, no build step, no dependencies besides the Mermaid CDN script for the flow diagram).

Source of truth is the Obsidian vault at `Documents/Asgard/Asgard/NOVA/`:
- `NOVA - Project Hub.md`
- `NOVA - Project Plan.md`
- `NOVA - Decision Log.md`

This page is a **snapshot** of that content for sharing outside the vault. It does not auto-sync with the vault, but once it's live it *does* auto-refresh itself: `index.html` fetches `data.json` on load and again every 60 seconds, so anyone with the page open sees a status change within a minute of it being pushed — no full redeploy or hard refresh needed.

**To update task/test status:** edit `data.json` (small file, one line per task/test), commit, and push. Do not hand-edit the tables in `index.html` — it renders entirely from `data.json`.

## Push to GitHub

This folder is already a local git repo with everything committed. To publish it:

```bash
# from this folder
git remote add origin https://github.com/akiira-work/project.git
git branch -M main
git push -u origin main
```

(Create the empty repo on GitHub first — no README/license/gitignore, since this folder already has its own.)

## Enable GitHub Pages

1. On GitHub, go to the repo's **Settings → Pages**
2. Under **Build and deployment**, set **Source** to "Deploy from a branch"
3. Branch: `main`, folder: `/ (root)`
4. Save — GitHub gives you the page at `https://akiira-work.github.io/project/` within a minute or two
