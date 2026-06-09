# Daily HQ 📊

A mobile-first personal dashboard that pulls live Gmail and Google Calendar data. Built as a single HTML file — no backend, no build step, deployable to GitHub Pages in minutes.

**Live:** https://xuwang-goldenwater.github.io/Dashboard/

---

## Features

| Tab | What it does |
|-----|-------------|
| ⚡ Today | Urgent emails, today's schedule, job search checklist, tasks, reading tracker |
| 🗓 Week | 7-day calendar grid + full event list |
| 🚀 Projects | 4 active projects with editable progress % and notes |
| 📧 Inbox | AI-filtered unread emails — real people only, newsletters stripped |
| 📡 Tech | Tech digest from Gmail `TechNews` label with → 查看原文(source) links |
| 📚 Reading | Book list with streak counter |

**Inbox filtering** uses a three-tier system: spam domains blocked, transactional emails de-prioritized, newsletter content detected by snippet patterns — so only real people surface as urgent.

**PWA ready** — add to iPhone/Android home screen for a native app feel.

---

## Setup

### 1. Google Cloud Console

1. Go to [console.cloud.google.com](https://console.cloud.google.com) and create a project.
2. Enable **Gmail API** and **Google Calendar API**.
3. Go to **APIs & Services → Credentials → Create Credentials → OAuth 2.0 Client ID**.
4. Application type: **Web application**.
5. Under **Authorized JavaScript origins**, add:
   ```
   https://xuwang-goldenwater.github.io
   ```
6. Copy the **Client ID** (ends in `.apps.googleusercontent.com`).

### 2. First-time login

Open the dashboard URL → paste your Client ID into the setup screen → Sign in with Google. The Client ID is stored in `localStorage` so you only do this once.

### 3. Tech Digest

Label any newsletters or tech emails with `TechNews` in Gmail. The Tech tab will pick them up automatically on next refresh.

---

## Deploy

```bash
git clone https://github.com/xuwang-goldenwater/Dashboard.git
cd Dashboard
# Edit index.html as needed
git add index.html
git commit -m "Update"
git push
```

GitHub Pages serves from the `main` branch root — no configuration needed beyond what's already set.

---

## Tech Stack

- Vanilla HTML/CSS/JS — zero dependencies, zero build
- [Google Identity Services](https://developers.google.com/identity) for OAuth
- Gmail REST API (`/gmail/v1`) for inbox + thread fetching
- Google Calendar API (`/calendar/v3`) for events
- `localStorage` for tasks, projects, books, reading streak

---

## Project Structure

```
Dashboard/
└── index.html    # Everything — HTML, CSS, JS in one file
```

---

Built in Public · [@xuwang-goldenwater](https://github.com/xuwang-goldenwater)
