# RCCT Practice Test

A practice version of the Rabin Cone Contrast Test (RCCT) for someone retaking a color vision screening.
Open `index.html` in any modern browser. No install or server is needed.

## What matches the clinic test

| Item | Value | Source |
|---|---|---|
| Letters | Sloan letters C D H K N O R S V Z, inside a crosshair on gray | Rabin 2011; AFRL comparison of CCTs |
| Order | Right eye, then left; 20 red (L), 20 green (M), 20 blue (S) letters each | Rabin 2011 |
| Contrast | 10 steps of 0.16 log units, 2 letters per step. Red/green 27.5% to 1%, blue 173% to ~6% | Rabin 2011 |
| Timing | Letter shown 1.0 s to 1.6 s, then blank gray for the same time | Rabin 2011 |
| Size | Red/green 20/330, blue 20/440, scaled to the chosen viewing distance (clinic: 36 in) | Rabin 2011 |
| Score | Letters correct x 5 (0 to 100). Normal is 75+. FAA pass is 55+ in each color | Rabin 2011; FAA AME Guide Item 52 |

## How the colors are computed

1. Each display color space (sRGB or Display P3) is converted to cone excitations with the Smith & Pokorny cone fundamentals.
2. The background gray uses the chromaticity from Rabin 2011 (x 0.299, y 0.300) at 20% of screen white.
3. Each letter changes only one cone type's excitation by the target contrast. The other two cones see no change.
4. Faint letters use per-pixel random dithering, so the average contrast is correct even below one 8-bit color step.
   At the faintest 1% level the measured average is within 0.003% of target.

## Limits

- Home screens are not calibrated, so scores can differ from the clinic by a few letters.
- On standard sRGB screens the first green level is capped at about 23% instead of 27.5%. Wide-color screens show every level exactly.
- Practice cannot change cone function. It helps with the format: speed, guessing, one eye at a time, and fading letters.

## Sources

- Rabin J, Gooch J, Ivan D. Rapid quantification of color vision: the cone contrast test. Invest Ophthalmol Vis Sci. 2011;52:816-820. https://pubmed.ncbi.nlm.nih.gov/21051721/
- FAA Guide for Aviation Medical Examiners, Item 52, acceptable color vision tests. https://www.faa.gov/ame_guide/app_process/exam_tech/item52/et
- AFRL-RH-WP-TR-2019-0122, Comparison of cone contrast tests for color vision (Innova CCT uses Sloan letters). https://apps.dtic.mil/sti/trecms/pdf/AD1154166.pdf
