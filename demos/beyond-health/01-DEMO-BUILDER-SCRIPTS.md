# Beyond Health — Demo Builder Scripts

**Account:** Beyond Health (Albuquerque, NM)  
**Style:** Conversational AI outreach (same pattern as TCM)  
**Patient replies:** natural language with light context (not slangy — prefer “Yes, …” over “yeah”)  
**Tokens:** `{patient}` → Maria · `{hospital}` → Beyond Health

## Dropdown programs in the tool

| Dropdown name | Role |
| --- | --- |
| TCM Outreach (Sample) | Keep — inpatient / TCM conversational baseline |
| Care Gaps / Cancer Screening | Clinical |
| GLP-1 Program Continuity | **Hero** (set Hospital field per prospect) |
| Wellness Care Gap | Supporting |
| Pre-Visit Pellet/Weight Prep | Supporting |

Cedars numeric / "reply 1" inpatient template is retired.  
**COPD / CHF** full multi-touch journeys live in `drg-specific-outreach/` (not Day-2 excerpts in this dropdown).

## Hero path (Maria, Week 4)

Bot asks in plain language. Maria answers with clear, natural replies:

1. Confirm identity → `Yes, this is Maria`
2. Med adherence → `Yes, I've been taking it like they told me`
3. Side effects → `Yes, the nausea has been pretty bad and it's getting worse`
4. Education push → bot sends GLP-1 nausea guide URL (blue link)
5. Missed nutrition visit → `No, I missed the nutrition appointment last week`
6. Callback / reschedule → `Yes`
7. Close → callback confirmation + patient portal reschedule URL (blue link)

That path shows **education push**, **care-team callback**, and **self-service portal reschedule**.

## Wellness Care Gap path

1. Confirm identity → `Yes, this is me`
2. Help scheduling? → `Yes, I'd like help scheduling`
3. Contact window → bot asks morning / afternoon / evening → `The morning is best`
4. Close → morning preference confirmed + portal schedule URL

## Pre-Visit Pellet/Weight Prep path

1. Confirm Thursday 10:00 AM pellet / weight visit → `Yes, I can make Thursday at 10`
2. Prep tips (arrive early, med list, comfortable clothing)
3. Prep guide push → blue URL for this visit type
4. Optional portal reschedule link + close

## Voice outline (Week 4)

Same questions as SMS, no touch-tone menus. Patient can speak naturally; intents map to the same branches (adherence, side effect, missed visit, callback / reschedule).

## Rule for future use cases

**Always add** a new dropdown template for single-thread demos. **Never remove or overwrite** existing programs unless the user explicitly asks to retire one.  
Put new **longitudinal DRG** programs in `drg-specific-outreach/`.
