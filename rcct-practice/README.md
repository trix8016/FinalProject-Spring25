# RCCT Practice Test

Practice versions of the FAA computer color vision tests, for someone retaking a color vision screening.
Open `index.html` in any modern browser (phone, iPad or laptop). No install or server is needed.

## The three test types

| Item | C ring (Rabin cone test, ring version) | Letters (Rabin cone test) | Number plates (Waggoner style) |
|---|---|---|---|
| Symbol | One Landolt C in the middle, gap up/down/left/right | Sloan letters C D H K N O R S V Z in a crosshair | 1-2 digit number hidden in colored dots |
| Answer | Arrow key, on-screen arrow, or swipe toward the gap | Letter key or on-screen letter | Number pad, N for no number |
| Contrast | Adaptive Psi-marginal method, 20 rings per color | Fixed fade: 10 steps of 0.16 log units, 2 letters each | 25 red-green plates at 5 color strengths, optional 12 blue-yellow |
| Timing | Stays until answered (default, matches the clinic test she took) or 5 s limit | 1.0-1.6 s flash, then blank, or no limit | Stays until answered (default, matches the clinic test she took) or 5 s |
| Size | 1.24 deg ring (13 mm at 60 cm) | 20/330 and 20/440 letters | ~6.9 deg plate, capped to fit the screen |
| Score | Threshold on the Rabin scale, 0-175 | Letters correct x 5, 0-100 | Plates correct, of 25 |
| FAA pass | 55 per color, each eye | 55 per color, each eye | 21 of 25 (as reported by providers) |

## Practice features

- Exam mode (no hints) or practice mode (right/wrong after each answer).
- Demo at strong contrast to learn the controls.
- Clinic scores can be entered and are marked on each practice result.
- "Drill" button repeats the weakest color from the last run.
- Results with staircase chart (ring), dot strip (letters) or accuracy-by-strength chart (plates).
- Progress charts per test and a history table, stored only in the browser.
- Layout works in portrait and landscape on phones and tablets.

## How the colors are computed

1. The display color space (sRGB or Display P3) is converted to cone excitations (Smith & Pokorny fundamentals).
2. Ring and letter symbols change only one cone type's excitation. Faint symbols use per-pixel dithering;
   at 1% contrast the measured average is within 0.005% of target.
3. Plates: number and background dots differ by equal and opposite L- and M-cone contrast. Each dot also gets random
   lightness (0.55-1.45x) and random blue-yellow hue (S-cone +/-35%), so protans and deutans are left with only weak,
   masked cues. The strongest difference is capped to what the screen can show without clipping.

## Verified

- Ring test, 300 simulated takers per threshold: median score within 1 point of the true score;
  a single 20-ring run varies about +/-8 points (10th-90th percentile).
- Plates: number visible to normal color vision; hidden in simulated deuteranope and protanope views (Machado 2009).
- End-to-end runs on iPhone, iPad, laptop and landscape phone sizes in Chromium, including timeouts and auto-submit.

## Limits

- Home screens are not calibrated, so scores can differ from the clinic by a few points.
- The ring test's adaptive method follows the published description, not the device's code.
- Plates are generated from the same principle as Waggoner plates, not copied. Plate difficulty for normal color
  vision has not been checked with a real person yet.
- Practice cannot change cone function. It helps with format, speed and guessing.

## Sources

- Rabin J, Gooch J, Ivan D. Rapid quantification of color vision: the cone contrast test. Invest Ophthalmol Vis Sci. 2011;52:816-820. https://pubmed.ncbi.nlm.nih.gov/21051721/
- FAA Guide for Aviation Medical Examiners, Item 52. https://www.faa.gov/ame_guide/app_process/exam_tech/item52/et
- FAA Color Vision FAQs (updated 2025-08-27). https://www.faa.gov/ame_guide/media/Color_Vision_FAQS.pdf
- AFRL-RH-WP-TR-2019-0122, Comparison of cone contrast tests for color vision. https://apps.dtic.mil/sti/trecms/pdf/AD1154166.pdf
- Quantitative cone contrast threshold testing (ColorDx methods). https://link.springer.com/article/10.1186/s40942-023-00442-3
- Cone contrast test-HD in red-green dichromacy. https://www.researchgate.net/publication/368972059
- Evaluation of the performance of the Waggoner computerised colour vision test (2025). https://avehjournal.org/index.php/aveh/article/view/1027
- Ng JS et al. Evaluation of the Waggoner Computerized Color Vision Test. Optom Vis Sci. 2015. https://journals.lww.com/optvissci/fulltext/2015/04000/evaluation_of_the_waggoner_computerized_color.14.aspx
- Machado GM, Oliveira MM, Fernandes LAF. A physiologically-based model for simulation of color vision deficiency. IEEE TVCG 2009.

## Calibration notes from real use

- Ring test: after 3-4 practice runs, her left-eye green score was about 40, the same as her clinic score of 40.
  This suggests the ring score scale matches the clinic device for her.
- Clinic ring test and Waggoner plates both stayed on screen until answered; the defaults match this.
