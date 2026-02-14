# double-decision

Single-file HTML5 cognitive training game focused on dual decisions:
- identify central object (car/truck)
- identify peripheral location target

## Current gameplay model
- Continuous adaptive session loop (no segmented phases)
- Session modes:
  - Timed mode (default 6 minutes, configurable 3–12)
  - Trial-count mode (default 45 trials, configurable 20–80)
- Adaptive staircase options:
  - 1-up/1-down (~50% target)
  - 2-down/1-up (~70.7% target)
- Dynamic difficulty dimensions:
  - stimulus duration (`D`) tuning
  - distractor count and central similarity escalation/de-escalation
- Micro-break overlays every 10 trials or 75 seconds with auto-resume

## Key outputs
- Live HUD with remaining time/trials, level, duration, and last-trial outcomes
- End-of-session summary:
  - best level
  - estimated threshold from reversal values
  - central/peripheral/combined accuracy
  - median RT and IQR
  - time-series chart of `D` over trials
- Last 10 sessions persisted to `localStorage`

## Run
Open `double-decision.html` (or `index.html`) directly in a modern browser.

## GitHub Pages compatibility note
- `index.html` is the GitHub Pages entrypoint and intentionally redirects to `double-decision.html`.
- Keep all gameplay/UI updates in `double-decision.html`; do not duplicate game logic in `index.html`.
- If the entry behavior changes, verify the redirect still works on both local file open and GitHub Pages hosting.
