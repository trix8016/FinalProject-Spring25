# RCCT Practice Test

Practice versions of both cone contrast color vision tests, for someone retaking a color vision screening.
Open `index.html` in any modern browser. No install or server is needed.

## The two test types

| Item | Letters (Rabin CCT, Innova military version) | C ring (ColorDx / Konan CCT-HD) |
|---|---|---|
| Symbol | Sloan letters C D H K N O R S V Z inside a crosshair | Landolt C, gap up, down, left or right |
| Answer | Letter, typed or tapped (clinic: read aloud) | Arrow key, on-screen arrow, or swipe toward the gap |
| Contrast | Fixed fade: 10 steps of 0.16 log units, 2 letters each. Red/green 27.5% to 1%, blue 173% to ~6% | Adaptive Psi-marginal method, 20 rings per color |
| Timing | Letter 1.0 to 1.6 s, then blank gray for the same time | Ring stays up to 5 s or until answered |
| Size | Red/green 20/330, blue 20/440. Clinic distance 36 in | 13 mm ring with 2.6 mm gap at 60 cm (1.24 deg) |
| Score | Letters correct x 5 (0 to 100) | Threshold on the same Rabin scale (0 to 175) |

Both run each eye separately in the order red (L-cone), green (M-cone), blue (S-cone).
Reference lines: FAA pass for the military RCCT is 55 per color. Normal is 75 (CCT-HD studies also use 90).

## Practice features

- Exam mode (no hints) or practice mode (right/wrong after each answer).
- Timed like the clinic, or no time limit.
- 6-symbol demo at strong contrast to learn the controls.
- "Drill" button that repeats the weakest color from the last run.
- Results per color with a dot strip (letters) or staircase chart (ring), progress charts and a history table.

## How the colors are computed

1. The display color space (sRGB or Display P3) is converted to cone excitations with the Smith & Pokorny fundamentals.
2. The background gray uses the chromaticity from Rabin 2011 (x 0.299, y 0.300) at 20% of screen white.
3. Each symbol changes only one cone type's excitation. The other two cones see no change.
4. Faint symbols use per-pixel random dithering. At 1% contrast the measured average is within 0.005% of target.

## Verified

- Simulated observers (300 runs each): the ring test's median score matched the true score within 1 point.
  A single 20-ring run varies about +/-8 points (10th to 90th percentile), so average several runs.
- Letter timing measured in Chromium: 2.0 s per letter at the start, 3.2 s at the faintest step.

## Limits

- Home screens are not calibrated, so scores can differ from the clinic by a few points.
- On sRGB screens the strongest green contrast is capped at about 23% instead of 27.5%.
- The ring test's adaptive method follows the published description, not the device's source code.
- Practice cannot change cone function. It helps with the format: speed, guessing, one eye at a time.

## Sources

- Rabin J, Gooch J, Ivan D. Rapid quantification of color vision: the cone contrast test. Invest Ophthalmol Vis Sci. 2011;52:816-820. https://pubmed.ncbi.nlm.nih.gov/21051721/
- FAA Guide for Aviation Medical Examiners, Item 52. https://www.faa.gov/ame_guide/app_process/exam_tech/item52/et
- AFRL-RH-WP-TR-2019-0122, Comparison of cone contrast tests for color vision. https://apps.dtic.mil/sti/trecms/pdf/AD1154166.pdf
- Quantitative cone contrast threshold testing (ColorDx CCT-HD methods). https://link.springer.com/article/10.1186/s40942-023-00442-3
- Cone contrast test-HD: sensitivity and specificity in red-green dichromacy. https://www.researchgate.net/publication/368972059
