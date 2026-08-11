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
linkable URL that teammates can open without making the site public:

1. Open https://console.tools.cipherhealth.dev/install and copy your personal install command.
2. Run it non-interactively (do not paste the tokenized URL into chat or commit it):

```bash
CIPHER_ASSUME_YES=1 bash -c "$(curl -fsSL <install-url-from-console>)"
paas doctor
paas login
paas whoami
paas init          # first time in this repo; accepts tool.yaml static runtime
paas deploy
```

3. Share the PaaS URL returned by `paas deploy`. Local `index.html` / `python3 -m http.server` still works for offline demos.

### Live demo

- **Private URL (SSO):** https://proms-outreach-journey.tools.cipherhealth.dev  
- App: `proms-outreach-journey` (static runtime on Cipher PaaS)  
- Sign in with your `@cipherhealth.com` Google account (IAP).

## Repo note

This demo is intended to live at **`SolarCS/proms-outreach-journey`** (private).

If this code is currently on another repo (e.g. `demo-builder-outreach` bootstrap):

```bash
gh repo create SolarCS/proms-outreach-journey --private \
  --description "CipherOutreach PROMs outreach journey demo (HOOS/KOOS JR + Information Transfer PRO-PM)"
git remote set-url origin https://github.com/SolarCS/proms-outreach-journey.git
git push -u origin HEAD:main
```

Then run the PaaS steps above from that repo.

## Customizing

Most tweaks: **Edit Script** tab (no code). Defaults live in the `PROGRAMS` array
inside `index.html`. Each program has a `journey` of touches; each step is either:

- a **question** — `{ messages: [...], reply: { text, intent, ack: [...] } }`, or
- a **system/closing** message — `{ messages: [...], reply: null }`.

---

*Demo/illustrative tool. Not for clinical use. HOOS, JR. and KOOS, JR. items © Hospital
for Special Surgery. Information Transfer PRO-PM items per CMS/Yale CORE published
instrument. Survey wording included for outreach-demo purposes only.*
