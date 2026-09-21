# project

GitHub Pages home at `https://akiira-work.github.io/project/` for shareable project trackers. Currently holds one:

## N.O.V.A. tracker

Path: `nova/tracker/` → live at **https://akiira-work.github.io/project/nova/tracker/**

A single-page tracking dashboard for the **N.O.V.A.** project (Normalize · Organize · Verify · Archive) — the pipeline that consolidates source material from any game, project, or client into structured Obsidian notes. Built for reviewers: objectives, features, flow diagram, the full task tracker, test status, and the open decisions blocking build start.

Source of truth is the Obsidian vault at `Documents/Asgard/Asgard/NOVA/`:
- `NOVA - Project Hub.md`
- `NOVA - Project Plan.md`
- `NOVA - Decision Log.md`
- `NOVA - Design Proposal.md`

The page (`nova/tracker/index.html`) renders entirely from `nova/tracker/data.json` and re-fetches that file every 60 seconds while open, so anyone with the tab open sees a status change within a minute of it being pushed — no redeploy of the HTML needed.

**To update task/test status:** edit `nova/tracker/data.json` (small file, one entry per task/test), commit, and push. Don't hand-edit the tables in `index.html` — it's generated from the JSON.

The repo root (`index.html`) is just a redirect into `nova/tracker/`, so visiting `https://akiira-work.github.io/project/` lands on the tracker automatically. Future sub-projects can live alongside `nova/` the same way.

## Push to GitHub

This folder is already a local git repo with everything committed. To publish it:

```bash
# from this folder
git remote add origin https://github.com/akiira-work/project.git
git branch -M main
git push -u origin main
```

(Skip `git remote add` if it's already set — check with `git remote -v`. Create the empty repo on GitHub first if it doesn't exist yet — no README/license/gitignore, since this folder already has its own.)

## Enable GitHub Pages

1. On GitHub, go to the repo's **Settings → Pages**
2. Under **Build and deployment**, set **Source** to "Deploy from a branch"
3. Branch: `main`, folder: `/ (root)`
4. Save — GitHub serves the site at `https://akiira-work.github.io/project/` within a minute or two, and the tracker specifically at `https://akiira-work.github.io/project/nova/tracker/`
