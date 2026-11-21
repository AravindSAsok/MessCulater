# MessCulater

A lightweight personal monthly mess expense calculator with a mobile-first Android app.

## Features
- Live total: main amount + advance amount
- Save or update one record per month
- Compare the latest two saved months
- Monthly history with edit and delete
- Export all saved months into one master CSV file
- Import a previous master CSV to restore or merge records
- Weekly in-app reminder to export a CSV backup
- Responsive mobile-first interface with bottom navigation
- Android app can share a CSV backup through the native Android share sheet
- Offline-capable Android build: web assets are bundled inside the APK; no website connection is needed to open the app

## Website
GitHub Pages builds the Vite output in `dist` and deploys it automatically from `main`.

Expected URL: https://aravindsasok.github.io/MessCulater/

## Android APK (built by GitHub Actions)
Every push to `main` that changes the app or Android workflow triggers **Build Android APK**.

1. Open the repository's **Actions** tab.
2. Select the latest **Build Android APK** run.
3. Wait for the workflow to complete successfully.
4. Open the run and download the `MessCulater-Android-APK` artifact.
5. Extract the ZIP and install `app-debug.apk` on your Android phone.

You can also trigger the workflow manually from Actions → Build Android APK → Run workflow.

The workflow creates the native Android project during CI, builds a debug APK, and stores it as a 30-day workflow artifact. This is an installable testing APK, not a Play Store-signed release.

## Run locally
Requires Node.js 20 or newer.

```bash
npm install
npm run dev
```

Create the production web build with `npm run build`.

## Android CSV backups
On Android, **Export all months** writes the master CSV into the app cache and opens the Android share sheet. Choose an available destination such as Files or Drive to save a copy outside the app. **Import CSV** opens the Android file picker and merges records by month; matching months are updated.

On the website, CSV export downloads `messculater-months.csv` through the browser.

## Data and migration
Monthly records are stored locally on the device in browser storage. The Android app bundles its own files and works offline, but its local storage is separate from the GitHub Pages website's browser storage. To move existing website records into Android, export the master CSV from the website and import it in the Android app.

Clearing app storage can erase local records. Keep a CSV backup regularly. The weekly reminder is checked when the app is opened; it cannot appear while the app is closed.

No backend, cloud database, Google Drive integration, or API key is required.
