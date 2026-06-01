# SONICPC Expansion Plan

## Audit

The project is a static canvas game contained in `index.html`.

Existing reusable systems:

- Canvas render loop with fixed 60 FPS update.
- Tile map and collision system.
- Player movement, jump, dash/run, projectiles and invulnerability.
- Entity arrays for coins, items, enemies, spikes and particles.
- HUD, title/pause/win/game-over overlays and short study toast.
- Quick quiz and final oral exam overlays.
- Static deployment shape suitable for Vercel.

Constraints:

- Keep the current visual identity, sprites, palette, animations and side-scrolling feel.
- Add systems as layers over the existing engine.
- Avoid large educational screens, dashboards or long text.
- Keep legal text short enough to read while playing.

## Feature Flags

All expansion systems should be gated behind `FEATURE_FLAGS` inside `index.html`:

- `progression`
- `relics`
- `npcMissions`
- `legalCases`
- `microEvents`
- `codex`

This allows staged rollout without risking the core platformer loop.

## Roadmap

### Stage 1: Official Expansion Layer

- Persistent XP, level, rank and streaks.
- Relics with rarity and short arcade-style bonuses.
- NPCs placed in the existing map with two-line dialogue.
- Microevents under 30 seconds.
- Timed legal cases using the existing quiz overlay.
- Codex collection panel unlocked by gameplay.

### Stage 2: World Identity

- Rename map sections into procedural/legal worlds without changing the map geometry.
- Add more section-specific enemies and questions.
- Add boss phases for ordinary, executive, proof, remedies and constitutional themes.

### Stage 3: Long-Term Progression

- Add run records.
- Add achievement toasts.
- Add relic synergies.
- Add optional challenge modes without touching the base route.

## Implementation Notes

- Use existing `showStudy`, `addFloat`, `particles`, `score`, `coinCount`, `lives`, `quizState` and `drawHUD` hooks.
- Store progression in `localStorage`.
- Keep all new UI in dark arcade panels matching the existing overlays.
- Prefer short strings and immediate feedback over explanatory text.

