# Alera Health Demo — Run of Show

**Audience:** Alera CIO, plus the pilot team he brings (data person and the two nurses). Kathy Smith and Jose if the clinicians join.
**Length:** about 30 minutes of product inside a longer working session
**Tool:** Outreach SMS Demo Builder (`index.html`) for the texts. Voice is the same buckets, read from `01-USE-CASE-AND-SCRIPTS.md`.
**Model in the room:** natural language in, one configured bucket out. Do not demo an open-ended answer. If they ask "what if she says something else?", read that bucket's row.
**Hero SMS:** IBHH Program Enrollment
**Hero voice:** Marcus live transfer to Kathy
**Settings:** Patient = `Denise` · Hospital = `Riverside Behavioral Health` (switches automatically with the Alera templates)

They are choosing among about five vendors in the next 30 to 60 days. Lead with safety routing and the engaged-% definition. Do not lead with a platform tour.

---

## Pre-call checklist

- [ ] Dropdown still includes TCM, Care Gaps, COPD, CHF, and the Beyond Health programs
- [ ] Select **IBHH Program Enrollment**. Confirm Patient = Denise and Hospital = Riverside Behavioral Health
- [ ] **IBHH Safety Escalation** is one click away, in case the voice transfer cannot be shown
- [ ] `02-OPEN-CASES-SEED-LIST.md` open (Denise, Marcus, Rosa, Andre, Leon)
- [ ] Present mode ready
- [ ] Say "automated assistant" out loud once before the meeting so it does not come out as "nurse" or "AI nurse"

---

## Minute-by-minute

| Min | Segment | What to do | Landing line |
| --- | --- | --- | --- |
| 0–4 | Their problem | Engagement is the constraint: care managers are scarce, quality scores depend on contact, and HR1 makes coverage paperwork real on January 1, 2027. Alera normalizes the payer list. Clinicians should only see escalations. | "You don't need more dials. You need a yes, and a safe handoff when the call stops being about enrollment." |
| 4–12 | **Hero SMS** | Play Denise. Name the bucket at each pause: Wants to verify, Coverage question, Wants to enroll, Prefers text. Point out that "at work days" is stored and does not change the reply. | "She counts as engaged at 'Yes sign me up.' That is the Wants to enroll bucket. Coverage got the coverage reply, not a custom answer." |
| 12–20 | **Hero voice** | Same nodes. Marcus: Patient, Verified, Coverage question, Wants to enroll, Prefers text, then Safety on the check-in, then Yes or unclear, then Kathy. If transfer is not live, read the failed-transfer line and show **IBHH Safety Escalation**. | "Maybe is the Yes or unclear bucket. Unrecognized on that question uses the same reply. Kathy gets the call either way." |
| 20–25 | **Open Cases** | Denise on the coordinator list. Marcus on Kathy's list. Rosa and Andre on Jose's list. Leon closed and suppressed. | "Three queues, one provider. Alera sees the rollup, Riverside sees its own panel." |
| 25–30 | Pilot math | 2,000 to 3,000 members, one state, phone and text only. Engaged % = Enrolled (Yes) / list. Next to it: Tier 1 count, transfer connect rate, minutes to clinician. | "That's the number your data person can manage the pilot on." |

---

## Click path

1. Template: **IBHH Program Enrollment**
2. Patient `Denise`, Hospital `Riverside Behavioral Health` (set when the template is selected)
3. Restart, Present mode
4. Advance and name the bucket: Patient → Wants to verify → Coverage question → Wants to enroll → Prefers text → 988 close
5. Leave present mode. Open the seed list at Denise, then Marcus
6. If voice is not built: switch to **IBHH Safety Escalation**, restart, advance identity → "Honestly I don't want to be here anymore" → clinician-is-calling close

---

## Lines that matter

- "Are we speaking with the patient, Marcus, or a caregiver?"
- "There is no cost to you, and this does not change your doctors or your benefits."
- "Your coordinator can help you with that paperwork so your coverage stays active. I can't say how any new rule applies to you."
- "Are you having thoughts of hurting yourself right now?"
- "I'm going to connect you right now with Kathy, a clinician on your Riverside care team."
- Failed transfer: "If you are in danger, hang up and call 911. You can also call or text 988."

## Lines to avoid

- Answering a question that has no bucket. Unrecognized has its own line
- Calling the assistant a nurse, a care manager, or part of the clinical team
- Any diagnosis, medicine name, or substance use history
- "You qualify for an exemption" or "you won't lose Medicaid"
- Enrolling Marcus because his mother said yes
- A central Alera queue as the only place escalations go. Escalations go to the provider. Alera is the conduit and the report.

---

## If they push

| They say | You say |
| --- | --- |
| "We could build this." | You could. The pilot is whether an off-the-shelf agent, pointed at your list and your providers, produces a yes rate and a safe handoff your nurses will trust. |
| "What does it cost?" | Scope the pilot to this list and this program. The number they react to is a large annual platform fee; keep the conversation on the 2,000 to 3,000 member pilot. |
| "Our patients have schizophrenia. You don't know how they'll react." | That's why every reply is a bucket. Suspicion is the verify bucket and it gives the clinic's real number. Anything off-script is Unrecognized, which re-asks once. On the safety question, Unrecognized transfers to Kathy. Nothing is interpreted. |
| "Don't call it a nurse." | Agreed. It introduces itself as an automated assistant, and it says so again if asked. |
| "Live transfer might not work at every provider." | The demo shows the warm transfer and the failure path. Providers who can't take a transfer get the same Tier 1 case, a page, and 988 / 911 on the line. |
| "We're talking to five companies." | The difference to listen for is who stops the script and who the clinician is. Here the clinician is theirs, on their panel. |
| "We don't want an app." | Phone and text only. Program info goes by text after a separate yes. |
| "Who holds the data?" | You do. Payer list in, normalized by Alera, attributed to the provider. We contact. Your clinicians take the escalations. |

---

## Done when

- They repeat "engaged means they said yes" without being corrected
- A clinician nods at the maybe → Kathy transfer, including the failed-transfer fallback
- They accept that Andre's mother cannot enroll him
- A next step is named: pilot population file, the 25 provider names, and which providers can take a warm transfer
