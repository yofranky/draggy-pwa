# Draggy — Gobble, Giggle, Grow! 🐉

A colorful dragon arena game (Slither-style, grow-by-eating) built as an installable
Progressive Web App (PWA). Made by **BKAOS**.

**[▶️ Play it live](#)** — *https://yofranky.github.io/draggy-pwa/*

## What it is

Guide a hatchling dragon around a shared arena, eating glowing "essence" orbs to grow longer,
while dodging (or provoking) six AI-controlled rival dragons. Cross another dragon's tail and
you're out — and when a rival dies, their length scatters into orbs (some worth bonus "bounty"
value) for whoever's brave enough to grab them.

- Two control schemes: drag-anywhere or a fixed on-screen joystick, plus a boost button (hold or
  toggle) and full keyboard fallback for desktop testing
- Six AI dragons with simple seek-nearest-orb / wander / arena-edge-avoidance behavior
- Colorblind-safe palette (Okabe-Ito) with dragons distinguished by crest/horn silhouette, not
  just hue — so identity never depends on color perception alone
- High contrast, reduce motion, large UI, sound, and haptics — all independently toggleable
- Live minimap, arena rank tracking, and a boot sequence where an egg cracks open into the
  hatchling (tap to skip, never forced)

## Why it's built this way

This is a BKAOS project, so:
- **Zero network calls.** No analytics, no ad SDKs, no font CDNs, no accounts. This one was
  already clean on that front — it uses the system font stack from the start.
- **Installable, not app-store-gated.** It's a PWA: open the link, "Add to Home Screen" on iOS or
  Android, and it runs full-screen like a native app, offline, with its own icon.
- **Accessibility isn't an afterthought.** Dragon identity uses shape (crest silhouette), not just
  color, specifically so the colorblind-safe mode doesn't just recolor the problem away.

## Tech stack

Vanilla HTML/CSS/JS, `<canvas>` for rendering, Web Audio API for sound, the Vibration API for
haptics, a hand-written service worker for offline caching. No frameworks, no build step,
no dependencies — auditable in one read-through, deployable by pushing static files.

## Running it locally

```bash
npx serve .
# then open the printed localhost URL
```
Opening `index.html` directly via `file://` works for gameplay, but the service worker
(offline support / installability) needs `http(s)://` — a browser security rule, not a bug.

## Deploying (GitHub Pages)

1. Push this folder to a GitHub repo.
2. Repo Settings → Pages → deploy from the `main` branch, root folder.
3. Live URL: `https://<username>.github.io/<repo>/`.
4. Visit on your phone → browser menu → "Add to Home Screen".

## What I learned building this

- Arc-length resampling for the dragon's tail (`resampleBody`) so segments stay evenly spaced
  regardless of how fast the head was moving when each point was recorded — this is what keeps
  the tail from gapping during a boost or bunching up on a sharp turn.
- Object pooling for the essence orbs (150+ short-lived objects reused instead of constantly
  allocated/freed) versus *not* pooling the much smaller, cheaper tail-point objects — a concrete
  example of pooling paying off in one place and being unnecessary complexity in another.
- Using shape (crest silhouette), not just recolored hue, as the colorblind-safe identity marker —
  a more genuinely accessible solution than a palette swap alone.
- Converting a single-file app into an installable PWA: manifest, icons (including maskable
  variants), and a cache-first service worker — same pattern as Blocky, reused here to prove it's
  a repeatable process, not a one-off.

## Project status

See `FUTURE_IDEAS.md` for parked feature ideas. This build is intentionally scoped to be
**finished** — playable, installable, documented — before anything new gets added.

---
*Draggy is made by BKAOS.*
