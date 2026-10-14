# Alera Health — Open Cases Seed List

Walk this queue after the Denise SMS path and the Marcus voice transfer. Filter to **Integrated Behavioral Health Home**. Every name here is fictional. Nothing in this list is a real member.

**Network:** Alera Health, Ohio ONEcare / OBHPN
**Demo provider:** Riverside Behavioral Health
**Clinicians:** Kathy Smith (Tier 1, on-call) · Jose (Tier 2, same day)
**Tier 3 owner:** Riverside care coordinator

---

## Seed cases

| # | Patient | Age | Channel | Issue | Tier | Status | Last response (summary) | Owner | Demo note |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 1 | **Denise Carter** | 34 | SMS | Enrollment; Medicaid renewal help | 3 Routine | Open | Confirmed identity, worried about a Medicaid letter, said "Yes sign me up", wants texts on workdays | Care coordinator | **Hero SMS.** The "yes" that counts toward engaged % |
| 2 | **Marcus Hale** | 38 | Voice | Safety; out of medication; enrolled | 1 Immediate | Open | Enrolled and accepted texts. Out of meds about a week. "Some days I don't see the point." Answered "maybe" to current self-harm. Transfer to Kathy | Kathy Smith | **Hero voice.** Live transfer. Case stays open until Kathy closes it |
| 3 | Andre Brooks | 29 | Voice | Caregiver worried; not enrolled | 2 Same day | Open | Mother answered. Says he has not picked up medicine and she is scared. He was not on the line, so he was not enrolled. Safe at the time of the call | Jose | Caregiver path. Do not enroll on mom's word |
| 4 | Leon Price | 51 | Voice | Declined | 4 Close | Closed | "No thanks, I'm good." Suppressed from the campaign | None | Show the suppression, not a work item |
| 5 | Rosa Nguyen | 44 | Voice | Out of medication; no safety concern | 2 Same day | Open | Enrolled. Out of medicine for 5 days. Clear "no" to self-harm. Asked for a clinician today | Jose | Tier 2 that is not a crisis. Jose's queue, not Kathy's |

Alternate SMS safety thread (use only if voice transfer cannot be shown): replay **IBHH Safety Escalation** as Denise and describe case 2's outcome on SMS instead of Marcus. Do not put two crisis cases on screen at once.

---

## Denise Carter — case detail

**Why she is in the queue:** The enrollment text got an explicit yes plus a reason (Medicaid letter) and a channel preference, without a care manager dialing the list.

**What staff sees:**

- Program: Integrated Behavioral Health Home
- Provider: Riverside Behavioral Health
- Identity: first name confirmed
- Enrolled: Yes
- Text consent: Yes
- Bucket path: Patient, Wants to verify, Coverage question, Wants to enroll, Prefers text
- Raw reply stored for the coordinator: "Text is better, I'm at work days"
- Issues: Enrollment · Medicaid renewal help
- SLA: coordinator texts within 2 business days
- Safety: none

**Close-the-loop:** coordinator texts during the day, helps with the renewal paperwork, does not promise an exemption.

**One-liner:** "Wants to enroll is the only bucket that counts. Coverage question got the coverage reply, word for word. 'At work days' is on the transcript for the coordinator. It did not change what she was texted."

---

## Marcus Hale — case detail

**Why he is in the queue:** Wants to enroll already fired. On the check-in, his sentence hit Safety. "Maybe" hit Yes or unclear, which is the transfer reply.

**What Kathy sees before she picks up:**

- Enrolled: Yes. Text consent: Yes
- Summary: out of medication about a week; "some days I don't see the point"; safety answer "maybe"
- Transfer result: connected (or failed, if you demo the fallback)
- 988 and 911 already spoken
- SLA: she is the call. The case cannot auto-close

**One-liner:** "Safety on the check-in, then Yes or unclear on the safety question. Unrecognized would have used that same reply. He already hit Wants to enroll, so he still counts."

---

## How to present without a live Evolve queue

1. Finish Denise in the phone.
2. Open this list.
3. Say: "Those replies are Open Cases on Riverside's panel, routed by tier. Coordinators get the yes. Jose gets same-day clinical. Kathy only gets the safety transfer."
4. Spend the time on Denise, then Marcus, then point at Rosa versus Andre so Jose's queue has both a med gap and a caregiver.

---

## What the pilot team counts

Alera's data person and two nurses read the rollup. They are not the escalation targets.

| Disposition | Counts as engaged? | Seed example |
| --- | --- | --- |
| Enrolled (Yes) | Yes | Denise, Marcus, Rosa |
| Interested / Callback | No | (none in this list) |
| Caregiver | No | Andre |
| Escalated (Safety) | No, unless they also have Enrolled (Yes) | Marcus is both: he counts as engaged, and he counts in the safety tally |
| Declined / Unable to Reach / Unable to Verify | No | Leon |
