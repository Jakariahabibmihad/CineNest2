# CineNest Sources

This repository serves as the official catalog of verifiable media sources for the CineNest Android application. CineNest utilizes this repository via its Repositories feature to dynamically discover and load remote source definitions.

## Catalog Format

The primary catalog is stored in `sources.json`. It maps individual provider definitions following the strict schema outlined in `schema.json`.

**Fields:**
* `id`: A unique string identifier for the source.
* `name`: The display name of the provider.
* `description`: (Optional) Brief summary of the provider.
* `type`: Categorization of the source (`website`, `catalog_api`, `direct_stream`, `media_server`).
* `baseUrl`: The base endpoint used by the application for data retrieval.
* `websiteUrl`: (Optional) Public-facing homepage of the provider.
* `integrationType`: How the app connects (`external`, `documented_api`, `direct_stream`, `server_api`).
* `capabilities`: Boolean toggles representing if the source supports `search`, `catalog`, and `playback`.
* `authorization`: Contains a `verified` boolean indicating if API usage is officially permitted, and optional `notes`.
* `enabled`: Determines if the app should parse and load the source by default.

## Adding a New Source

To add a new source, review the criteria in `CONTRIBUTING.md`. Submissions must include evidence of authorized API usage or public domain validation. 

## Utilizing in CineNest

To load this catalog into CineNest, point the application to the raw GitHub user content URL:
`[https://raw.githubusercontent.com/](https://raw.githubusercontent.com/)<OWNER>/CineNest-Sources/main/sources.json`
*(Replace `<OWNER>` with the actual GitHub username or organization).*

**Limitation Warning:** This JSON file operates strictly as a metadata index. It does not contain code to implement video parsing, extraction, or playback within the application.
