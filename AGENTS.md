# AGENTS.md

## Cursor Cloud specific instructions

This repo is a **single-file static web app** (`index.html`) — the CipherOutreach PROMs
Outreach Journey demo. There is **no build step, no package manager, and no backend**.
All third-party assets (Tailwind, Font Awesome, Inter font) load from public CDNs, so an
internet connection is required to render styling.

### Run it (dev server)

Serve the repo root over HTTP and open the page (see `README.md` "Run it"):

```bash
python3 -m http.server 8000
# open http://localhost:8000
```

Opening `index.html` directly via `file://` also works, but a static server is preferred.

### Lint / test / build

There are **no automated tests, no linter, and no build** configured in this repo. The
"build" is simply serving the static file. Do not add CI-style build steps to the update
script.

### Notes

- A `GET /favicon.ico 404` in the server log is expected and harmless (no favicon shipped).
- App logic (programs, journeys, scripted replies) lives entirely inside `PROGRAMS` in
  `index.html`. Global functions like `switchProgram(id)`, `advance()`, and
  `updateSetting(key, value)` are invoked from inline `onclick`/`oninput` handlers and are
  handy for scripted (headless) interaction.
- `tool.yaml` declares `runtime: static` for Cipher PaaS deployment. Per repo policy, do
  **not** deploy via GitHub Pages.
