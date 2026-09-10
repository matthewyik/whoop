# WHOOP Muscle Gain Dashboard

This repository contains only the dashboard UI/code. Personal WHOOP data and credentials stay on the local computer.

## Privacy

Do **not** commit any of the following:

- `whoop_data.json`
- `whoop_tokens.json`
- `whoop.py` if it contains your Client ID, Client Secret, or authorization code
- calorie/weight logs exported from the dashboard

The included `.gitignore` blocks the main private files by default.

## How the local setup works

1. `whoop.py` runs locally and refreshes `whoop_data.json`.
2. A local HTTP server serves the permanent loader and `whoop_data.json`.
3. The permanent loader fetches the newest `dashboard.html` from this repository whenever the page is opened/refreshed.
4. `dashboard.html` reads `whoop_data.json` from the local server and refreshes it every 30 minutes.

This keeps health data local while allowing dashboard-code updates without replacing the local HTML every time.
