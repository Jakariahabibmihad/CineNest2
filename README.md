# CineNest Anime Extensions

This repository contains the JSON catalog for anime extensions used by the CineNest Android application. CineNest reads this repository to discover media sources that will be loaded as internal extensions for data scraping, catalog browsing, and playback.

## Structure

*   **`sources.json`**: The live list of available extensions. CineNest fetches this file to display installable anime providers.
*   **`schema.json`**: The data structure rules. Notice that `integrationType` now includes `internal_extension` to signal to the app that these modules should be loaded internally rather than handed off to a browser.

## Deployment

To deploy updates to these extensions:

```bash
git add sources.json schema.json README.md
git commit -m "Update repository for internal anime extensions"
git push
