# MessCulater

A lightweight monthly mess expense calculator.

## Features
- Live total: main amount + advance amount
- Save or update one record per month
- Compare the latest two saved months
- Monthly history with edit and delete
- CSV export for backups
- Responsive layout for mobile and desktop

## Run locally
Open `index.html` in a browser. No build step or dependencies are required.

## Deploy
- **GitHub Pages:** Repository Settings → Pages → Deploy from a branch → `main` → `/ (root)`.
- **Vercel:** Import this repository and deploy with no build command and no output directory (static HTML).

## Data storage
The current version stores records in browser `localStorage`. Data persists across refreshes in the same browser profile, but is not shared across devices, browsers, or users. Clearing browser site data can erase it. Use Export CSV for backups.

GitHub README/JSON files are not a safe writable database for a public static frontend. For shared multi-device persistence, connect a hosted database such as Supabase and add authentication/access rules before storing real records.
