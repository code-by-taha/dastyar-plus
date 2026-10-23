# Dastyar Plus

A lightweight, bilingual (Persian and English) personal dashboard for tasks, study, fitness, coding projects, and notes. It runs as a static site with no account or backend. Your workspace is saved in your browser.

[فارسی](README.fa.md)

Full [installation and GitHub Pages deployment guide](DEPLOYMENT.md) · [راهنمای فارسی](DEPLOYMENT.fa.md)

## Features

- Personal profile with a display name, role, and current goal
- Persian (RTL) and English (LTR) interface
- Task board and list view with categories, priorities, due dates, recurring tasks, search, drag-and-drop, and direct edit/complete/delete actions
- Global command search across tasks, notes, subjects, and projects
- Study sessions, subjects, exams, flashcards, a weekly timetable, and 25/50/90-minute focus timers
- Workout log, programs, body-weight tracking, and progress photos
- Project and code-snippet lists, focus timer, and optional Monaco editor
- Notes with folders and Markdown preview
- Appearance controls, keyboard command palette, optional sounds, and data import/export

## Run locally

No build step or package installation is required. Either open `index.html`, or serve the folder over HTTP:

```bash
python3 -m http.server 8000
```

Then visit <http://localhost:8000>.

## Publish with GitHub Pages

1. Push the repository to GitHub.
2. Open **Settings → Pages**.
3. Choose **Deploy from a branch**, select `main` and `/(root)`, then save.

For repository setup, browser upload steps, privacy notes, and troubleshooting, see the [full deployment guide](DEPLOYMENT.md).

## Privacy and storage

Dastyar Plus has no server component. Profile details and dashboard data are stored in this browser's `localStorage` and are not synced between browsers or devices. Use **Settings → Data → Export** to keep a backup before clearing browser data. Imported JSON files should only come from a source you trust.

The browser's local storage is limited. Progress photos are resized before being saved. Fonts, icons, and the optional Monaco editor may be loaded from third-party CDNs when online; the app otherwise remains usable with fallback fonts.

## Project files

```text
index.html       Application markup
css/style.css    Styles and responsive layout
js/app.js        Application state and interactions
README.md        English documentation
README.fa.md     Persian documentation
DEPLOYMENT.md    English installation and deployment guide
DEPLOYMENT.fa.md Persian installation and deployment guide
LICENSE          MIT license
```

## Contributing

Issues and pull requests are welcome. Keep changes dependency-light, preserve both language directions, and avoid including personal data or exported workspace files in commits.

## License

MIT. See [LICENSE](LICENSE).
