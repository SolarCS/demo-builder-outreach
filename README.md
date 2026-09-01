# CipherOutreach · SMS Demo Builder

A lightweight, single-file web tool for demoing what the **CipherOutreach** SMS patient
experience looks like on a phone. Upload a script template, swap between templates per use
case, edit the script live, and present an animated iMessage-style thread.

> Live demo: enable GitHub Pages for this repo (Settings → Pages → Deploy from branch → `main` / root),
> then open `https://<your-username>.github.io/demo-builder-outreach/`.

## What it does

- **Realistic iOS SMS preview** — animated typing indicator, message bubbles, read receipts,
  and tappable scripted patient replies, all inside an iPhone frame you can present full-screen.
- **Template library** — import as many templates as you like and switch between them from a
  dropdown. Rename, duplicate, export, and delete them. Everything is saved in your browser.
- **Inline script editing** — edit bot messages and the patient's scripted reply for every step,
  reorder or add/remove steps, without touching a spreadsheet.
- **Tokens** — use `{patient}` and `{hospital}` anywhere in the script; they're replaced live and
  the hospital name shows as the SMS sender.

## Template format

Import a spreadsheet (`.xlsx` or `.csv`) with these columns:

| Step ID | Bot Message | Choice Text | Choice Next |
| ------- | ----------- | ----------- | ----------- |

- Rows that share a **Step ID** are grouped into one step.
- Each non-empty **Bot Message** becomes a texted bubble, sent in order.
- **Choice Text** is the patient's scripted reply for that step (shown as a tappable chip).
- **Choice Next** is the Step ID the thread advances to after the reply. Leave it blank to just
  advance to the next step in order; a step with no Choice Text is treated as a closing message.

A ready-to-edit **TCM (Transitional Care Management) outreach** script ships as the built-in
sample. Use the **Export** button to download the current template in this exact format as a
starting point for new ones.

### Bundled outreach programs

Dropdown templates (conversational AI / natural-language patient replies):

- **TCM Outreach (Sample)** — inpatient / TCM post-discharge
- **Care Gaps / Cancer Screening**
- **COPD Post-Discharge (Day 2)** — longitudinal
- **CHF Post-Discharge (Day 2)** — longitudinal
- **GLP-1 Program Continuity** (hero demo; org name set via Hospital field)
- **Wellness Care Gap**
- **Pre-Visit Pellet/Weight Prep**

Those three auto-set Patient = `Maria` and Hospital = `Beyond Health` (change Hospital for other prospects).  
COPD/CHF auto-set Patient = `Patti`.  
Pack notes: [`demos/beyond-health/`](demos/beyond-health/).

**Important:** when adding a new use case, **add** a new dropdown entry. Do not remove or overwrite existing programs.

## Presenting

- **Advance** (button, the pulsing camera icon, or tapping a reply chip) steps the thread forward
  one message/reply at a time.
- **Restart** replays the thread from the top.
- **Present mode** (expand icon) hides the editor panel for a clean, phone-only view.

## Running locally

It's a static file — just open `index.html` in a browser, or serve the folder:

```bash
python3 -m http.server 8000
# then open http://localhost:8000
```

## Tech

Plain HTML/CSS/JS. Tailwind, Font Awesome, and [SheetJS](https://sheetjs.com) (`xlsx`) are loaded
from CDNs; there is no build step and no backend. All data lives in `localStorage`.
