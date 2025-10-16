# Team Dashboard


This folder contains a self-contained copy of the Bug Bash team dashboard front-end (`team.html`) and its supporting API server. You can copy/move this directory into a fresh project and deploy it independently from the main Bug Bash site.

## Contents

- `team.html` – front-end dashboard interface (unchanged from the primary project)
- `team-data.js` – seed data for departments, members, and initial tasks
- `server.js` – lightweight Express service that powers the login, tasks, and updates APIs
- `package.json` – dependencies (`express`, `cors`) and scripts (`npm start`, `npm run dev`)
- `storage.json` – generated at runtime to persist task and update changes across restarts

## Getting Started

```bash
cd team-dashboard
npm install
npm run dev # or: npm start
```

By default the server listens on `http://localhost:4000`. Open that URL in a browser to load `team.html`.

The API implements the same endpoints the front-end expects:

- `POST /api/team/login`
- `POST /api/team/logout`
- `GET /api/team/me`
- `GET /api/team/tasks`
- `POST /api/team/tasks`
- `PATCH /api/team/tasks/:id`
- `DELETE /api/team/tasks/:id`
- `POST /api/team/tasks/:id/claim`
- `GET /api/team/tasks/:id/updates`
- `POST /api/team/tasks/:id/updates`
- `GET /api/team/events`

Seed data lives in `team-data.js`; you can edit it to customise the initial experience. All modifications made through the API are saved to `storage.json` so they persist between restarts.

Static assets (logos, etc.) are served from `../assets` – keep that folder alongside this one, or adjust the static path in `server.js` as needed.
