# Beyond Health — Demo Builder Scripts

**Account:** Beyond Health (Albuquerque, NM)  
**Style:** Conversational AI outreach (same pattern as TCM)  
**Patient replies:** natural language, casual texting (no "reply 1/2", no em dashes)  
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

Bot asks in plain language. Maria answers like a real texter:

1. Confirm identity → `hey yes this is Maria`
2. Med adherence → `yeah I've been taking it like they told me`
3. Side effects → `honestly the nausea has been pretty bad and it's getting worse`
4. Missed nutrition visit → `no I missed the nutrition one last week, things got crazy`
5. Callback → `yes please call me when you can`

That path opens the care-team follow-up story (side effect + missed visit + callback).

## Voice outline (Week 4)

Same questions as SMS, no touch-tone menus. Patient can speak naturally; intents map to the same branches (adherence, side effect, missed visit, callback).

## Rule for future use cases

**Always add** a new dropdown template for single-thread demos. **Never remove or overwrite** existing programs unless the user explicitly asks to retire one.  
Put new **longitudinal DRG** programs in `drg-specific-outreach/`.
