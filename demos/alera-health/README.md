# Alera Health — IBHH Enrollment Demo Pack

Voice and SMS for **Alera Health** (Ohio behavioral health network / ONEcare). The member can answer in their own words. Outreach maps that answer to a configured bucket (Wants to enroll, Does not want to enroll, Coverage question, Safety, and so on) and plays only that bucket's reply.

**SMS style:** plain language, casual patient replies, no numbered menus. The phone templates play the hero bucket path. The full bucket tables are in `01-USE-CASE-AND-SCRIPTS.md`.
**Tokens:** `{patient}` → Denise · `{hospital}` → Riverside Behavioral Health

## Quick start

1. Open the SMS Demo Builder (`index.html`).
2. Confirm the dropdown still includes TCM, Care Gaps, COPD, CHF, and the Beyond Health programs.
3. Select **IBHH Program Enrollment**. Patient and Hospital switch to Denise and Riverside Behavioral Health.
4. Present mode, then advance the enroll path (scam question, Medicaid letter, "Yes sign me up").
5. For the safety moment, read the Marcus voice path in `01-USE-CASE-AND-SCRIPTS.md`, or select **IBHH Safety Escalation** if transfer cannot be shown.
6. Use `02-OPEN-CASES-SEED-LIST.md` for Kathy (Tier 1), Jose (Tier 2), and the care coordinator (Tier 3).
7. Follow `03-DEMO-RUN-OF-SHOW.md` for the meeting.

## Files

| File | Purpose |
| --- | --- |
| `Alera-IBHH-Voice-Script.docx` | Evolve voice script in the Outreach export layout (question, webform, numbered responses, issue panel, alert, next question) |
| `01-USE-CASE-AND-SCRIPTS.md` | Same script in markdown, plus the SMS hero paths |
| `02-OPEN-CASES-SEED-LIST.md` | Fictional personas for the queue |
| `open-cases-seed.csv` | Same seeds as CSV |
| `03-DEMO-RUN-OF-SHOW.md` | Minute-by-minute |
| `Alera-IBHH-Enrollment-SMS.xlsx` | Importable enroll thread |
| `Alera-IBHH-Safety-Escalation-SMS.xlsx` | Importable crisis thread |

The same two spreadsheets are at the repo root for a quick import.

## Rule for this pack

These templates were **added** to the dropdown. TCM, Care Gaps, COPD, CHF, GLP-1 Program Continuity, Wellness Care Gap, and Pre-Visit Pellet/Weight Prep stay as they are.
