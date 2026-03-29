# Arena Deathmatch

A browser-based 3D first-person shooter built entirely with vanilla HTML, CSS, and JavaScript — no libraries, no canvas frameworks, just raw raycasting.

![Game Screenshot](https://img.shields.io/badge/Play-In%20Browser-red?style=for-the-badge)

## Gameplay

Go head-to-head against a heavily-armoured AI opponent in a claustrophobic arena. The enemy has full state-machine AI — it patrols the map, chases you when you enter its line of sight, and strafes while shooting back. Survive long enough to put it down.

- **One life** — no respawns. Make your shots count.
- **30 rounds** per mag. Press `R` to reload (takes 1.5 seconds).
- Enemy accuracy scales with distance and drops as it takes damage.
- The crosshair turns red when you have a clear shot.

## Controls

| Key | Action |
|-----|--------|
| `↑` / `↓` | Move forward / backward |
| `←` / `→` | Rotate view |
| `Space` | Shoot |
| `R` | Reload |
| `Esc` | Pause |
| `Enter` | Restart after match ends |

## How It Works

The renderer is a classic **DDA raycaster** (the same technique used by Wolfenstein 3D and DOOM). Each frame:

1. One ray is cast per screen column using the DDA (Digital Differential Analyzer) algorithm.
2. Wall height is calculated from the perpendicular wall distance to prevent fisheye distortion.
3. A **z-buffer** is filled per column to allow correct sprite occlusion.
4. The enemy is rendered as a **billboard sprite** — transformed into camera space and drawn column-by-column, skipping any column that sits behind a wall in the z-buffer.

### Enemy AI States

| State | Trigger | Behaviour |
|-------|---------|-----------|
| `patrol` | Default / lost sight | Wanders with random direction changes; stuck-detection kicks in if it doesn't move |
| `chase` | Player in sight, distance > 5.5 units | Moves directly toward player at full speed |
| `attack` | Player in sight, distance ≤ 5.5 units | Strafes side-to-side and fires; accuracy falls with distance |

### Enemy Sprite

The enemy is a heavily-armoured demon soldier pre-rendered onto an offscreen `96×192` canvas at startup:

- Horned helmet with glowing angular eyes and a teeth grille
- Three shoulder spikes per pauldron
- Glowing chest reactor core (multi-ring)
- Knee spikes and knuckle armour
- Visible gun with muzzle brake on the right arm
- Damage state: cracks, scorch marks, sparks from the reactor, muzzle flash

## Running Locally

No build step needed. Just open `arena-shooter.html` in any modern browser.

```bash
# Clone and open
git clone https://github.com/YatharthSharma1309/arena-deathmatch.git
cd arena-deathmatch
open arena-shooter.html   # or double-click the file
```

## Technical Details

- **Renderer:** 2D Canvas API, 800×480 viewport
- **FOV:** ~66° horizontal (camera plane length 0.66)
- **Raycasting:** DDA per screen column, perpendicular distance for correct wall height
- **Sprite rendering:** Inverse camera matrix transform, z-buffer occlusion per column
- **Shooting:** Angle-based hit detection — checks angular offset to enemy then validates with a line-of-sight ray
- **No external dependencies**

## License

MIT
