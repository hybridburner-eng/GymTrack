# GymTrack v1.0

A mobile-first workout planner and strength log. Built as a static Progressive Web App (PWA) for GitHub Pages. No dependencies, accounts, or servers.

## Features
- Five editable example templates (Push, Pull, Legs, Upper, Lower).
- Add, remove, or customize exercises and sets during a live workout without changing the template.
- Log weight (kg) and reps, one tap to complete a set, auto-save in the same browser.
- Previous exercise performance shown for reference, optional 'Use last'.
- Rest timer with supported vibration, session history, 30-day metrics and exercise strength trends.
- JSON backup/restore and CSV export.
- HTTPS service worker caches app files for offline use after the first online visit.

## Publish on GitHub Pages
1. Create a new **public** repository named `GymTrack` (for GitHub Free Pages; do not commit private data).
2. Extract the ZIP and upload all seven contained items to the repository ROOT (same folder). Do not upload just the ZIP.
3. Repository > Settings > Pages > Build and deployment > Deploy from a branch, `main`, `/(root)` > Save.
4. After deployment, open `https://YOUR_USERNAME.github.io/GymTrack/`.
5. On your Samsung phone in Chrome, open browser menu and select **Install app** or **Add to Home screen**.

`index.html` can open directly as a local file for a basic UI smoke test, but offline caching and PWA installation require HTTPS (GitHub Pages).

## Important data limitations
All data is saved in browser `localStorage` *on that phone and browser only*. Publishing code to GitHub does not sync workouts or back them up. Export full JSON backups after significant sessions and before clearing browser storage. Rest alerts and timer behavior while the browser is backgrounded vary by platform. CSV load-volume metrics use only external recorded weights, not bodyweight or machine leverage. No cloud sync, exercise video library, recovery recommendations, or validated 1RM estimates are included in v1.

## Repository structure
```
index.html
manifest.webmanifest
sw.js
icon-192.png
icon-512.png
README.md
.nojekyll
```

## Testing checklist
- Start Push Day, change weights and reps, complete at least one set, verify rest timer.
- Add a custom exercise, add/remove sets, finish session.
- Check History details and Progress chart.
- Edit a template; ensure previous sessions remain unchanged.
- Export JSON, import in another browser session, confirm history restored.
- After an online load, use Airplane mode and relaunch the installed PWA.
