# Future Ideas (not in v1 — parked on purpose)

Ideas go here instead of into the code, until the current build is shipped and working end to end.

- Persist settings across relaunches (currently in-memory only per the `Storage` adapter — wire it
  to `localStorage` or Capacitor Preferences when this moves toward the native shell)
- Real app icon pass — current icon is a placeholder programmatically-generated dragon head; worth
  a proper design pass once this ships
- Leaderboard of longest-length-reached-this-session (still local-only, no server)
- Spectator/replay of your last death (would reuse the existing history/resampling data)
- Apple App Store build via Capacitor, once there's budget for a developer account
