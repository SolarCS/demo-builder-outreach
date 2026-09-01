# CipherOutreach · DRG-Specific Outreach

Standalone multi-touch **DRG outreach** demo tool. Click Day → Day on the timeline and
Advance / camera to play each SMS thread. Built for presenting full longitudinal
recovery series (not single-day excerpts).

Programs today:

| Program | Touches | Days |
| --- | --- | --- |
| **COPD Post-Discharge** | 4 | 2, 9, 16, 23 |
| **CHF Post-Discharge** | 5 | 2, 7, 14, 21, 30 |

COPD matches the original COPD journey demo. CHF is the full restored multi-touch CHF
program (not a Day-2 excerpt).

> Companion to the single-conversation [SMS Demo Builder](../index.html)
> (`SolarCS/demo-builder-outreach`). Add new DRG programs here — do not put
> longitudinal DRG journeys back into the SMS Demo Builder dropdown.

## What it does

- **Program switcher** — COPD or CHF (room to add more DRGs).
- **Clickable journey timeline** — jump between touchpoints; each loads its own SMS thread.
- **Camera / Advance playback** — natural-language patient replies with conversational AI intent mapping.
- **Live branding** — Hospital + Patient tokens.
- **Editable script** — Edit Script tab; resets per program.
- **Present mode** — hide the panel for a clean phone-only demo.

## Run locally

```bash
# from repo root
python3 -m http.server 8000
# open http://localhost:8000/drg-specific-outreach/
```

Or open `index.html` directly in a browser.

## Split into its own SolarCS app (optional)

This folder is self-contained. When `SolarCS/drg-specific-outreach` exists as a private
repo, copy this directory to the repo root (with `tool.yaml`) and deploy as its own PaaS app.

## Tech

Single-file HTML/CSS/JS. Tailwind + Font Awesome from CDN. State in `localStorage`
(`drg_outreach_v1`).
