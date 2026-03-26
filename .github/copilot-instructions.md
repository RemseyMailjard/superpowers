`# Project Guidelines

## Architecture

- Static site: `index.html` + `styles.css` + `app.js`.
- Case content lives in `cases.json` (loaded by `app.js` and rendered as cards).
- Keep it single-page unless a change request explicitly adds navigation.

## Code Style

- Prefer small, readable functions and plain browser APIs (no frameworks unless requested).
- Avoid introducing new build tooling unless required for a feature.
- Keep HTML semantic and accessible (headings in order, labels for status/errors).

## Build and Test

- Local run: `python -m http.server 8000` (then open `http://localhost:8000/`).
- If fetch/CORS issues appear, confirm you’re not using `file://`.

## Conventions

- Case objects in `cases.json` should be stable and human-editable:
  - Use `YYYY-MM-DD` dates.
  - `keyPoints` and `tags` are arrays of strings.
- Do not add real customer data or confidential content to sample cases.
