# Kinegroove

**Move your way. Track what matters. Grow your practice.**

Kinegroove is a privacy-first, mobile-friendly fitness and nutrition journal that runs entirely in **one HTML file**. It works offline, without a server, account, tracking scripts, or external JavaScript dependencies.

## Start using it

- Download [`index.html`](./index.html) and open it in a modern browser, or run it from a static local web server.
- Set your energy profile in Settings.
- Log an activity from **Move** (including yoga, dance, flow arts, skating, walking, fencing, martial arts, gardening, landscaping, skiing, and strength work).
- Record meals with calories and optional protein/carbohydrate/fat.
- Create adjustable weekly goals and review frequency, consistency, and progress under **Insights**.
- Use **Back** for the previous app page, **Home** for the dashboard, and either action within an editing dialog.

## Features

- Activity presets and custom activities, duration, intensity, estimated energy, sets, reps, and weights
- Automatic local date/time stamps with optional manual correction, original creation time, and edit history timestamps
- Meal energy and optional macronutrient logs
- Estimated resting expenditure plus **additional** exercise energy (rather than double-counting gross exercise)
- Per-activity trend charts, weekly linear goals, sessions-per-week goals, streaks, day-of-week frequencies, and activity calendar
- JSON backup/restore and CSV export
- Mobile/desktop responsive layout; keyboard-accessible controls; no third-party requests

## Privacy and backups

All entries are saved in your browser's local storage. Kinegroove intentionally continues using the storage key `momentum.offline.2026.v1` for compatibility with the original Momentum prototype. **Do not rename this key** without providing a data migration.

**Important:** Storage for files opened using `file://` varies by browser, and the same HTML file under different URLs or a GitHub Pages site may use different storage. **Export a JSON backup from the old version first**, then use Settings → Import JSON in Kinegroove. Also back up periodically: clearing site data or switching devices can remove local records.

A standalone HTML file is **not yet an Android APK or a Play Store app**. A future Android wrapper should provide stable storage, backup/export, accessibility testing, and store compliance.

## Calorie estimates

Exercise energy is an approximate amount above a one-MET resting baseline:

```
additional exercise kcal ≈ (MET − 1) × 3.5 × weight_kg ÷ 200 × minutes
```

Intensity defaults draw on the [Compendium of Physical Activities](https://pacompendium.com/adult-compendium/), and resting-energy estimates use the [Mifflin–St Jeor approach](https://pubmed.ncbi.nlm.nih.gov/2305711/) or your manual estimate. These figures are rough population-level models, not personal medical measurements; they omit portions of non-exercise activity and other metabolic variation.

## Development

The application lives in `index.html`. For a quick local preview, open it in a browser or serve it using:

```sh
python -m http.server 8000
```

Then open `http://localhost:8000`. The app needs no bundler, npm install, runtime service, or internet connection after the file is loaded.

This repository's initial release is intentionally simple and auditable. Future development should add automated cross-browser regression tests, accessible Android packaging, and a documented data-migration path before broad distribution.

## License

No explicit software license has been chosen yet. Public source access does not by itself grant reuse or redistribution rights. Add a license when the repository owner chooses one.
