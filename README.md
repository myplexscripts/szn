# Suzanne Raider — Video Archive

Unofficial static fan archive for [@suzanneraider](https://www.youtube.com/@suzanneraider). No API keys or backend required.

## Setup

1. Open **Settings → Pages → Build and deployment** and select **GitHub Actions** as the source.
2. Open **Actions → Sync videos → Run workflow**, select `main`, and run it. Enable Actions if prompted. Repository policies must allow the workflow to write contents and push to `main`.
3. The Publish archive workflow deploys the website after a successful sync. The site is expected at https://myplexscripts.github.io/szn/.

Alternatively, select **Deploy from a branch**, `main`, `/ (root)`, and save. However, commits made using GITHUB_TOKEN normally do not trigger branch-based Pages builds; use GitHub Actions for automatic updates. If choosing branch deployment, remove the optional pages.yml workflow and publish bot changes with a manual human push.

## Sync behaviour

The sync runs every four hours (UTC), merges by video ID, and retains previously discovered videos even if they leave the RSS feed. The first run only discovers recent uploads (typically up to 15). Older videos can be added manually using the same JSON fields. Deleted or private videos remain in the archive but may not play. YouTube can also restrict embedding; the direct watch link remains available. Scheduled workflows can be delayed by GitHub or disabled after inactivity.

## Local preview

Run `python3 -m http.server 8000` in the repository root and open `http://localhost:8000`.
