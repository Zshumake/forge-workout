# FORGE — your open-and-go workout

A self-contained, offline workout app for your iPhone home screen. Open it, see exactly what to do today, tap through it, get rewarded for showing up. **No accounts, no backend, no subscription. Your data never leaves your phone.**

Built for: building muscle & tone with adjustable dumbbells (to ~50 lb) + resistance bands, 3 days/week, ~30 minutes, full-body.

## What's in v1
- **One-tap "today" card** — a 3-day full-body rotation (A/B/C) that hands you the exact moves, weights, and reps. Zero decisions.
- **Tap-to-log runner** — one move at a time, big ✓ to complete a set, ± steppers and weight chips (no keyboard), a built-in rest timer.
- **The Feel Engine** — instead of picking weights, you tap **Easy / Right / Hard**; the app adjusts your loads and reps automatically (double progression).
- **Weekly-streak gamification** — a "fill the week" ring, **Perfect Weeks**, XP, levels & belts, a companion (Ingot), achievements, and PRs. The streak is *weekly* (your 3× target), so rest days never break it.
- **Backup/restore** — one-tap JSON export to Files/iCloud, and import to restore.

## Run it locally (for development)
A service worker + the manifest need a real server (they don't work from `file://`).

```bash
# from the project root (the folder that contains /app and /tools)
node tools/serve.js
# then open http://localhost:8765
```

## Put it on your iPhone
1. **Host it free** (recommended — needed for offline + install):
   - **Cloudflare Pages** or **GitHub Pages** or **Netlify** — drag-and-drop or connect the `app/` folder as a static site. Any static HTTPS host works.
2. On your iPhone, open the hosted URL in **Safari**.
3. Tap the **Share** button → **Add to Home Screen**.
4. Launch it from the home-screen icon. It now opens instantly, works fully offline, and (because it's installed) your data is protected from Safari's storage cleanup.

> Tip: after a few weeks, use **Settings → Back up my data** and save the file to iCloud Drive. Reinstalling or clearing Safari can erase on-device data — the backup is your safety net.

## How progression works (so you can trust it)
- Each lift has a rep range (e.g. 10–12). You add reps each session; once you hit the top across all sets — or tap **Easy** — it bumps the weight (or the band's tension/level) and resets the reps. That's evidence-based **double progression**.
- When a dumbbell lift maxes out your 50 lb (legs first), it automatically switches to adding reps/sets instead of weight.
- Bands progress by **reps → slower tempo → next band level** (since band "weight" isn't a clean number).

## Files
- `index.html` — the entire app (logic, UI, content, styles). Buildless vanilla JS.
- `manifest.webmanifest`, `sw.js`, `icons/` — PWA install + offline support.
- The research, ideas, and plan this was built from live in `../docs/` and `../.research/`.

## Roadmap (not yet built)
- **v2:** Fixed-Equipment Intensity Engine (tempo/pause/unilateral escalation, plateau auto-swaps, band-wear tracking) · "Coach who knows your why" mindset layer.
- **v3:** Seasons & Evolution (themed 6-week blocks, goal drift, optional 4th day).
- Also planned: "Right-Sized Today" (adapt the session to your time/energy/travel) and "Welcome Back" comeback ramp — specced in the deepened plan.
