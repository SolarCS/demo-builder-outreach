# CipherOutreach · PROMs Outreach Journey Demo

An interactive, presenter-friendly demo that simulates the **patient SMS experience**
for CipherOutreach **PROMs (Patient-Reported Outcome Measures)** programs. Switch
between three built-in journeys from a dropdown and walk a patient through
pre-op / longitudinal check-ins / post-op survey collection using CipherOutreach's
**conversational AI** pattern — patients reply in plain language; the AI maps each
reply to a CMS-aligned intent and fires the approved response.

> Companion to the COPD multi-touch journey demo and the single-conversation
> [SMS Demo Builder](https://github.com/SolarCS/demo-builder-outreach).

## Programs

| Program | Use case | Timeline |
|---------|----------|----------|
| **HOOS, JR. (THA)** | Total hip arthroplasty PRO-PM | Pre-op (−14) → Days 30 / 120 / 180 / 270 → Day 300+ |
| **KOOS, JR. (TKA)** | Total knee arthroplasty PRO-PM | Same longitudinal arc |
| **Information Transfer PRO-PM (9Q)** | Post-op transition understanding | Day 2 primer → Day 3 full 9-question survey |

Pre-op and Day 300+ touches for HOOS/KOOS use the **exact CMS HOOS, JR. / KOOS, JR. items**
and the **None / Mild / Moderate / Severe / Extreme** response scale. Mid-year
check-ins sample pain, stiffness, and function themes without administering the
full instrument (engagement + recovery support so patients complete the
matched-pair post-op survey).

The 9-question program uses the published CMS/Yale Information Transfer PRO-PM
items and response sets, with anonymity called out in the intro.

## What it does

- **Program dropdown.** Switch HOOS / KOOS / 9Q without reloading — each keeps its own
  editable script and completion state in the browser.
- **Clickable journey timeline.** Jump between touchpoints; camera icon / **Advance**
  plays the natural-language patient replies.
- **Conversational AI demo.** Free-text patient replies map to scripted CMS intents
  (e.g. `"Moderate"`) — the SMS thread stays clean and realistic.
- **Live branding tokens.** `{hospital}` and `{patient}` substitute throughout.
- **Editable script.** Edit any outreach message, patient reply, mapped intent, or
  response per touch; **Apply & Refresh** or **Reset** to the built-in default for
  the active program.
- **Present mode.** Hide the panel for a clean phone-only view; floating day pills
  switch touches.

## Run it

Static single-file app — no build step.

```bash
# Local
python3 -m http.server 8000
# open http://localhost:8000
```

Or open `index.html` directly in a browser.

### Private shareable URL (Cipher PaaS)

Do **not** use GitHub Pages (always public). Deploy with Cipher PaaS for a private,
linkable URL:

```bash
# Install CLI from https://console.tools.cipherhealth.dev/install (use your token)
CIPHER_ASSUME_YES=1 bash -c "$(curl -fsSL <install-url>)"
paas doctor
paas login
paas init          # if not already initialized
paas deploy
```

## Repo note

This demo is intended to live at **`SolarCS/proms-outreach-journey`** (private).
If you are viewing it on another repo (e.g. during bootstrap), create that private
repo under SolarCS and push this branch there as `main`.

## Customizing

Most tweaks: **Edit Script** tab (no code). Defaults live in the `PROGRAMS` array
inside `index.html`. Each program has a `journey` of touches; each step is either:

- a **question** — `{ messages: [...], reply: { text, intent, ack: [...] } }`, or
- a **system/closing** message — `{ messages: [...], reply: null }`.

---

*Demo/illustrative tool. Not for clinical use. HOOS, JR. and KOOS, JR. items © Hospital
for Special Surgery. Information Transfer PRO-PM items per CMS/Yale CORE published
instrument. Survey wording included for outreach-demo purposes only.*
