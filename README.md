# Arena Deathmatch

A browser-based 3D first-person shooter. No downloads, no installs — just open `arena-shooter.html` in any modern browser and play.

---

## How to Play

1. Open `arena-shooter.html` in Chrome or Firefox
2. Choose your difficulty on the start screen and press **ENTER**
3. Click the canvas to lock your mouse for aiming
4. Survive as long as possible, clearing waves of armoured enemies

---

## Controls

| Input | Action |
|---|---|
| **Mouse** | Aim |
| **Left Click** or **Space** | Shoot |
| **W / ↑** | Move forward |
| **S / ↓** | Move backward |
| **A / D** | Strafe left / right |
| **← / →** | Turn (keyboard fallback if mouse isn't locked) |
| **R** | Reload |
| **Q** | Swap weapon |
| **ESC** | Pause / resume |
| **F** | Toggle fullscreen |
| **ENTER** | Start game / quick restart |

---

## Difficulty

Choose before each run — you can change it any time from the end screen.

| Level | What changes |
|---|---|
| **Easy** | Enemies move slower, deal less damage, and have worse aim |
| **Normal** | Balanced challenge |
| **Hard** | Enemies are faster, more accurate, and hit harder |

---

## Weapons

You carry two weapons. Press **Q** to swap at any time.

### Pistol
- 30 rounds per magazine
- Fast fire rate
- Reliable at any range

### Shotgun
- 6 shells per magazine
- Fires 5 pellets in a spread — devastating up close
- Slow fire rate and longer reload

---

## Waves

- Killing all enemies on screen ends the wave
- Each new wave adds more enemies (up to 3 at once) with more health and speed
- There is no final wave — survive as long as you can

---

## Health Packs

Three health packs are placed around the arena. Walk over one to restore **+30 HP**. They reset between waves.

---

## HUD at a Glance

```
┌──────────────────────────────────────────────┐
│  WAVE 3  |  KILLS 7        [enemy HP bar]    │
│                                               │
│                  crosshair                    │
│                                               │
│  ♥ ████████░░   SHOTGUN  ◉ ◉ ◉ ◉ ◎ ◎         │
└──────────────────────────────────────────────┘
```

- **Health bar** — 10 segments, green → yellow → red as you take damage
- **Ammo display** — bullet icons for the pistol, shell icons for the shotgun
- **Wave + kill counter** — top centre
- **Enemy HP bar** — appears when an enemy is in view
- **Crosshair** — turns red when you're on target; flashes orange on a confirmed hit
- **Minimap** — top-right corner; shows walls, your FOV cone, pulsing enemy blips, and health pack locations

---

## End Screen

When you die the game shows:

- **Wave reached** and **total kills**
- **Accuracy** (shots that hit vs. shots fired)
- **Time survived**
- Your **personal best** (saved automatically)

Two buttons appear:

| Button | What it does |
|---|---|
| **RESTART** | Replay immediately on the same difficulty |
| **CHANGE DIFFICULTY** | Returns to the start screen so you can pick a new difficulty |

---

## Tips

- **Stay mobile.** Enemies strafe when they close in — a stationary player is easy to hit.
- **Use health packs early.** They respawn each wave, so there is no reason to hoard them.
- **Shotgun at close range, pistol at distance.** The shotgun's spread wastes pellets at long range.
- **Watch the minimap.** Enemy blips pulse faster when they have line of sight on you.
- **Harder difficulties react faster.** On Hard the enemy spots you from further away and shoots more frequently.
