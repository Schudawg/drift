# Drift — Pushup Momentum

A single-file pushup tracker built around a **momentum** system instead of streaks, inspired by [Polar Habits](https://polarhabits.com/momentum). Missing a day doesn't reset you to zero — it just costs you a proportional dip that's easy to bounce back from.

No build step, no backend, no dependencies. It's one HTML file plus a manifest and service worker so it can be installed as a PWA.

## Features

- **Log with a date picker** — log today or backdate any past day
- **Edit or delete entries** — fix a mis-logged number right from the history list
- **Momentum engine** — replicates Polar Habits' gain/loss/bounce-back formula
- **Daily or weekly-frequency mode** — score momentum per day, or per week against an N-times-a-week target (extra days still earn points; short weeks cost a proportional dip, same as the daily model)
- **52-week grid** — GitHub-style contribution grid, color intensity scaled to reps that day
- **Personal records** — best single day and best week, tracked automatically
- **Goals** — monthly and yearly rep targets with progress bars
- **Stats** — totals by day / week / month / year, plus 8-week and 12-month bar charts
- **Evening reminder** — optional browser notification if you haven't logged by a set time (only fires while the app is open in a tab — no server-side push)
- **Backup** — export a JSON snapshot (full fidelity) or CSV (for spreadsheets), import JSON to restore
- **Installable** — manifest + service worker for "Add to Home Screen" / desktop install, works offline once loaded

## Running it

Just open `index.html` in a browser — everything runs client-side. Data is stored in `localStorage`, scoped to whatever domain you host it on.

## Deploying to GitHub Pages

```bash
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/<your-username>/<repo-name>.git
git push -u origin main
```

Then in the repo: **Settings → Pages → Deploy from a branch → main / (root)**. Your app will be live at:

```
https://<your-username>.github.io/<repo-name>/
```

Once it's live over HTTPS, most mobile browsers will offer to install it as an app (or use the browser's "Add to Home Screen" / install icon in the address bar).

## Notes

- Data lives in your browser's `localStorage` on whatever device/browser you use it in — it does **not** sync across devices. Use **Export** periodically and save the file to Google Drive (or anywhere) as a backup, and **Import** to restore it on another device.
- All charts and the contribution grid are hand-drawn SVG — no chart library required.

## License

MIT — see [LICENSE](LICENSE).
