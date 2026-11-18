# Adaptive Tutorial Automation — Type B Demo

Built for the r/DevsForHire lead (u/7PWU): automate a mobile-game tutorial on an Android emulator with adaptive detection, retries, and proof of 10 consecutive runs.

## Live Demo
https://slavh.github.io/adaptive-automation-demo/

## Files
- `automation.py` — working framework: adaptive detection, retry logic, stability test
- `index.html` — public demo page with proof log and approach
- `styles.css` — styling
- `README.md` — this file

## Run
```bash
python3 automation.py          # MOCK mode — verifies full pipeline, 10/10 runs
USE_EMULATOR=1 python3 automation.py   # LIVE — ADB + OpenCV (needs game templates)
```

## How it maps to the requirements
| Requirement | Implementation |
|-------------|----------------|
| No fixed coordinates | `detect_element()` finds elements by visual features; positions shift each mock run |
| Adapt to changing layouts | Template matching (OpenCV) + confidence threshold; re-scan on retry |
| OpenCV / image recognition | `_detect_live()` stub with `cv2.matchTemplate` documented for handover |
| Retry failed actions | Up to 3 retries per step with adaptive re-detection |
| 10 consecutive runs proof | `stability_test()` runs fresh 10x and logs PASS/FAIL proof |
| Deliverables | Working source + setup notes + proof log |

## Note
The lead's $30 fixed budget is below our $40–$250 range and commenters flagged it as low; outreach should present the demo as proof of capability and quote fairly.
