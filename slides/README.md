# CipherOutreach DRG Patient Journey Slides

Two CipherHealth-branded static slides visualizing longitudinal COPD and CHF outreach journeys for patient **Patti**.

| Slide | Program | Cadence |
|-------|---------|---------|
| 1 | COPD | Discharge → Days 2 / 9 / 16 / 23 (4 touches) |
| 2 | CHF | Discharge → Days 2 / 7 / 14 / 21 / 30 (5 touches) |

## Download
- **PowerPoint:** [`CipherOutreach_DRG_Patient_Journeys.pptx`](./CipherOutreach_DRG_Patient_Journeys.pptx) — upload this to Google Drive / Slides if you want an editable cloud copy
- **PNG previews:** [`render/slide-1.png`](./render/slide-1.png) (COPD), [`render/slide-2.png`](./render/slide-2.png) (CHF)

Touchpoint copy is sourced from the COPD and CHF workflows in `../index.html`.

Rebuild:
```bash
python3 build_journey_slides.py
```
