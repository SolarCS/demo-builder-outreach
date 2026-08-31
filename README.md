# CipherOutreach · SMS Demo Builder

An interactive, presenter-friendly demo that simulates the **patient SMS experience**
for CipherOutreach outreach programs. Switch between workflows from a dropdown and walk
a patient through the conversation using CipherOutreach's **conversational AI** pattern —
patients reply in plain language; the AI maps each reply to a scripted intent and fires
the approved canned response.

> Live: https://demo-builder-outreach.tools.cipherhealth.dev/

## Workflows

| Workflow | Use case | Timeline |
|----------|----------|----------|
| **TCM / Inpatient Post-Discharge** | Standard inpatient / TCM recovery check-in (symptoms, instructions, meds, follow-up) | 1 touch · same-day |
| **Care Gaps · Cancer Screening** | Preventive care-gap outreach — overdue cancer screenings + callback scheduling | 1 touch · same-day |
| **COPD Post-Discharge** | Best-practice COPD recovery check-ins | 4 touches · Days 2 / 9 / 16 / 23 |
| **CHF Post-Discharge** | Heart-failure home monitoring (weight, SOB, diet, meds, symptoms) | 5 touches · Days 2 / 7 / 14 / 21 / 30 |

Scripts adapted from "press 1 / press 2" IVR-style outreach into **open-ended SMS
prompts**. Patient replies are realistic free text; the bot still only responds with
the configured, approved messages for the mapped intent.

## What it does

- **Workflow dropdown.** Switch across all four programs without reloading — each keeps
  its own editable script and completion state in the browser.
- **Clickable journey timeline.** Jump between touchpoints (multi-day for COPD/CHF;
  single conversation for TCM / Care Gaps); camera icon / **Advance** plays the
  natural-language patient replies.
- **Conversational AI demo.** Free-text patient replies map to scripted intents
  (e.g. `"Feeling worse"`, `"Wants callback to schedule"`) — the SMS thread stays
  clean and realistic with no demo overlays.
- **Live branding tokens.** `{hospital}` and `{patient}` substitute throughout.
- **Editable script.** Edit any outreach message, patient reply, mapped intent, or
  response per touch; **Apply & Refresh** or **Reset** to the built-in default for
  the active workflow.
- **Present mode.** Hide the panel for a clean phone-only view; floating day pills
  switch touches on longitudinal journeys.

## The recovery stories

### TCM / Inpatient Post-Discharge

Single same-day check-in covering identity confirm, how the patient is feeling,
discharge-instruction comprehension, medications, and follow-up scheduling help.

### Care Gaps · Cancer Screening

Single same-day preventive outreach: confirm identity → overdue cancer screening
pitch → preferred callback window → confirm care-team will call within 3 business days.

### COPD

| Touch | Day | Focus | Patient state |
|------|-----|-------|---------------|
| 1 | 2 | Initial check-in (7 questions) | Mostly on track; med question + unscheduled follow-up need outreach |
| 2 | 9 | Early progress (5 questions) | Turning the corner |
| 3 | 16 | Continued recovery (3 questions) | Steady improvement |
| 4 | 23 | Final check-in (3 questions) | Back to normal, program close-out |

### CHF

| Touch | Day | Focus | Patient state |
|------|-----|-------|---------------|
| 1 | 2 | Initial check-in (10 questions) | Mostly stable; weight gain + unscheduled follow-up (with scheduling phone #) |
| 2 | 7 | Early progress (7 questions) | Stabilizing; follow-up scheduled but not yet completed |
| 3 | 14 | Continued recovery (5 questions) | Weight stable, diet and meds on track |
| 4 | 21 | Late recovery (5 questions) | Reinforcing daily weigh-ins and low-salt diet |
| 5 | 30 | Final check-in (5 questions) | Program close-out — recovery on track |

## Run it

Static single-file app — no build step.

```bash
python3 -m http.server 8000
# open http://localhost:8000
```

Or open `index.html` directly in a browser.

## Customizing / adding workflows

Most tweaks can be done live in the **Edit Script** tab (no code). For deeper changes
or new use cases, each workflow's default journey is built in `index.html`:

- `buildTcmJourney()`
- `buildCareGapsJourney()`
- `buildCopdJourney()`
- `buildChfJourney()`

Register a new program in the `DEFAULT_PROGRAMS` array (id, name, shortName, meta,
blurb, journey). Each touch has `steps`, and each step is either:

- a **question** — `{ messages: [...], reply: { text, intent, ack: [...] } }`, or
- a **system/closing** message — `{ messages: [...], reply: null }`.

Bump `STORE_KEY` when adding bundled programs so existing browsers pick them up.
In-browser edits are stored in local storage and take priority until you use
**Reset to default for this workflow**.

---

*Demo/illustrative tool. Not for clinical use. COPD script derived from an internal
best-practice COPD post-discharge outreach document. CHF script adapted from a
Kaiser SoCal LAMC CHF post-discharge outreach program. Care Gaps script adapted from
Central Hospital cancer-screening outreach.*
