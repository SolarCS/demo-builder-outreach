# Beyond Health — Demo Builder Scripts

**Account:** Beyond Health (Albuquerque, NM)  
**Hero program:** GLP-1 / Weight Management Program Continuity  
**Supporting:** Wellness care-gap · Pre-visit pellet/weight prep  
**Tool:** CipherOutreach SMS Demo Builder (`index.html`)  
**Tokens:** `{patient}` → Maria · `{hospital}` → Beyond Health

Importable spreadsheets (same folder / repo root):

| File | Use in demo |
| --- | --- |
| `BH-GLP1-Program-Continuity-SMS.xlsx` | **Hero** — Week-4 check-in, risk path (side effect + missed nutrition + callback) |
| `BH-Wellness-Care-Gap-SMS.xlsx` | Supporting vignette — overdue wellness / preventive |
| `BH-PreVisit-Pellet-Weight-Prep-SMS.xlsx` | Supporting vignette — confirm + education |

Demo Builder settings for the hero path: **Patient** = `Maria` · **Hospital / SMS sender** = `Beyond Health`.

---

## Program 1 — GLP-1 / Weight Management Continuity (SMS)

**Program type (Evolve framing):** Call-On-Date / Preventive + Clinical Longitudinal  
**Cadence story:** Day-3 welcome (optional mention) → weekly/refill → **Week-4 check-in (demo)** → silent-patient re-engage → pre-provider visit  
**Issues opened on this path:** Side Effect · Missed Visit · Callback Requested

### SMS flow (demo path)

| Step | Bot summary | Patient reply (demo) | Issues |
| --- | --- | --- | --- |
| 0.0 | Intro / continue | Continue | — |
| 1.0 | Identity | Yes, this is Maria | — |
| 2.0 | Med adherence | Taking as directed | — |
| 3.0 | Side effects | Nauseous, getting worse | **Side Effect** |
| 4.0 | Coach/nutrition kept? | Missed nutrition visit | **Missed Visit** |
| 5.0 | Callback? | Yes, please call me back | **Callback Requested** |
| 6.0 | Close + education tip | — | Cases remain open for staff |

### Voice script (Week-4 check-in)

Use for “we also do voice” or if presenting Evolve voice talent later. Keep conversational; IVR prompts in brackets.

```
[Intro]
Hello, this is a call from Beyond Health about your weight management program.
If you are disconnected, you can call us back at (505) 899-4414.
To continue in English, press 1.

[Who answered]
Before we continue, can you confirm that you are {patient} by pressing 1?
If you are a family member or caregiver, press 2.
If we have the wrong number, press 3.

[Program context]
Thank you. Our records show you are enrolled in Beyond Health's weight management
program and are due for your Week-4 check-in.

[Medication adherence]
Have you been able to take your prescribed medication as directed?
Press 1 if yes — taking it as directed.
Press 2 if you have missed doses or stopped.
Press 3 if you have not been able to obtain your medication.
  → If 2 or 3: Thank you for letting us know. A care team member will follow up. [Open Case: Med Adherence]

[Side effects]
Are you having any side effects that concern you, such as nausea, vomiting,
dizziness, or stomach pain?
Press 1 if you are doing fine.
Press 2 if you are having side effects or have questions.
  → If 2: We're sorry you're dealing with that. Someone from Beyond Health will
    follow up. If this is urgent, please call the clinic or seek emergency care.
    [Open Case: Side Effect]

[Coach / nutrition visit]
Were you able to keep your most recent coach or nutrition appointment?
Press 1 if yes.
Press 2 if you missed it or need to reschedule.
Press 3 if you are not sure.
  → If 2 or 3: [Open Case: Missed Visit]

[Callback]
Would you like someone from Beyond Health to call you back to discuss your
responses and help with next steps?
Press 1 for yes, please call me back.
Press 2 if you are all set for now.
  → If 1: [Open Case: Callback Requested] / optional live transfer

[Close]
Thank you for partnering with Beyond Health. Someone may follow up during
clinic hours. If you have an urgent medical problem, call your provider,
911, or go to the nearest emergency department. Goodbye.
```

**Voicemail:**  
`Hello, this is a call from Beyond Health about your weight management program. We're sorry we missed you. We will try again. You can also call us at (505) 899-4414. Have a nice day.`

**SMS nudge (unreached after voice):**  
`Hi, this is Beyond Health checking in on your weight management program. Please call us at (505) 899-4414 or reply to this text when you can. Reply STOP to opt out.`

### Suggested multi-touch cadence (talk track only)

| Timing | Channel | Purpose |
| --- | --- | --- |
| Day 3 post-start | SMS | Welcome + side-effect education |
| Weekly / refill window | Voice or SMS | Med obtain / dose adherence |
| Before coach/nutrition | SMS | Confirm / reschedule |
| Week 4–8 silent patients | Voice | Re-engage drop-offs |
| Pre-provider visit | SMS + education | Prep + reminder |

---

## Program 2 — Wellness / Care Gap (SMS + voice outline)

**Program type:** Call-On-Date / Preventive  
**Issue:** Schedule Help Requested

**Voice (short):**  
Beyond Health calling about an overdue wellness visit or preventive screening → offer scheduling help → thank / close. Negative or “help schedule” → Open Case.

---

## Program 3 — Pre-Visit Pellet / Weight Prep (SMS + voice outline)

**Program type:** Appointment Reminder (+ education)  
**Issues:** Cancelled Appointment · Reschedule Requested

**Voice (short):**  
Reminder for Thursday 10:00 AM at Beyond Health → confirm / cancel / reschedule → on confirm, read prep tip (arrive early, med list, pellet site prep) → close.

---

## Weave differentiator (one line)

> Weave helps you message. Cipher helps you **run** the weight program — every check-in, every missed touch, and which patients need a human today.
