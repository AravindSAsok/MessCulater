# MessCulater

A lightweight personal monthly mess expense calculator.

## Features
- Live total: main amount + advance amount
- Save or update one record per month
- Compare the latest two saved months
- Monthly history with edit and delete
- Export all saved months into one master CSV file
- Import a previous master CSV to restore or merge records
- Weekly in-app reminder to export a CSV backup
- Responsive layout for mobile and desktop

## Run locally
Open `index.html` in a browser. No build step or dependencies are required.

## Deploy
- **GitHub Pages:** Repository Settings → Pages → Deploy from a branch → `main` → `/ (root)`.
- **Vercel:** Import this repository and deploy with no build command and no output directory (static HTML).

## Data and backups
The app stores monthly records in this browser's `localStorage`, so they persist across refreshes in the same browser profile. Records are not automatically shared across devices or browsers. Clearing browser site data can erase them.

Use **Export all months** to download one complete file named `messculater-months.csv`. It contains every saved month, not just the currently selected month. Use **Import CSV** to restore or merge a backup; matching months are updated and other months are retained.

The app checks for the backup reminder when opened. After the first week, it asks for a CSV export once every seven days. Choosing **Remind me later** postpones the next reminder for seven days. The reminder cannot appear while the browser/app is closed.

No Google Drive connection, backend, database account, or API key is required.
