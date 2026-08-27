# CipherOutreach DRG Patient Journey Slides

Two static CipherHealth-branded slides visualizing longitudinal COPD and CHF outreach journeys for patient **Patti**.

| Slide | Program | Cadence |
|-------|---------|---------|
| 1 | COPD | Discharge → Days 2 / 9 / 16 / 23 (4 touches) |
| 2 | CHF | Discharge → Days 2 / 7 / 14 / 21 / 30 (5 touches) |

## Files
- `CipherOutreach_DRG_Patient_Journeys.pptx` — editable PowerPoint
- `render/slide-1.png` / `render/slide-2.png` — PNG previews
- `build_journey_slides.py` — rebuild from brand assets + Patti avatar
- `patti_avatar.png` — circular patient avatar used on the slides

Touchpoint copy is sourced from the COPD and CHF workflows in `../index.html`.

Rebuild:
```bash
python3 build_journey_slides.py
```
