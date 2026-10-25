# Pinefall — Wilderness & Salvage

An original browser wilderness survival game rendered with Three.js. Explore, build a camp, scavenge abandoned caches, craft equipment, and drive through Blackpine Valley. The world uses procedural models and textures, with no external asset requests. Three.js r170 is bundled locally.

## Wilderness & Salvage update

- Smooth, textured terrain and rocks; layered organic tree crowns; up to 14,000 animated grass blades.
- Atmospheric sky, stars, moon, environment lighting, soft shadows, animated reflective-looking water, and shader-based campfire flames.
- Padded armor and scrap plate armor with damage absorption, durability, and repair crafting.
- Scrap pistol, pipe shotgun, and automatic salvaged rifle; magazines, reserve ammo, reloading, aiming, muzzle flashes, and obstruction-aware hit detection.
- Craftable motorbike and buggy with third-person driving, steering, braking, fuel consumption, refueling, and collision checks.
- Twelve scavenging sites with scrap, cloth, and fuel; supplies restock each morning.
- Graphics presets from Performance to Ultra plus render scale, shadows, view distance, vegetation density, water animation, fog, exposure, and FPS display.
- Field of view, look/aim sensitivity, invert Y, camera motion, recoil animation, crosshair color, touch-control size, and objective visibility settings.
- Master/ambient/effects volume, peaceful/survival/hostile wildlife, day length, and an endless mode.

## Play

Gather wood and stone, build a campfire and shelter, then construct a rescue beacon. Rescue arrives at dawn on day 3 unless endless mode is enabled. Wolves avoid burning fires. Shelter restores health. Eat berries and drink at the lake shore. Amber flags mark salvage caches.

Guns are crafted empty: make rounds or shells in the Weapons workshop, then reload. Armor equips when crafted. Repair worn armor from the Armor tab. Vehicles spawn on clear ground in front of the player; approach one and interact to drive.

### Desktop controls

| Action | Control |
| --- | --- |
| Move / drive | WASD or arrow keys |
| Look | Mouse; right-drag when pointer lock is unavailable |
| Sprint / jump | Shift / Space |
| Interact / enter or leave vehicle | E |
| Attack / automatic rifle | Left click / hold left click |
| Aim | Right mouse while pointer-locked, or F |
| Reload / refuel while driving | R |
| Cycle weapons | 1 |
| Pistol / shotgun / rifle | 2 / 3 / 4 |
| Build / inventory / eat | B / I / Q |
| Brake / pause | Space while driving / Escape |

### Mobile controls

The left joystick moves or drives; right-side swipes look around on foot. E interacts, the attack button swings or fires, R reloads (or refuels while driving), and ADS toggles aim. The arrow jumps on foot and becomes STOP while driving. Bottom buttons cycle weapons, consume berries, and open crafting/inventory. Hold the attack button for automatic rifle fire.

## Persistence

Saves remain in browser-local storage and do not sync across devices. Version 1 expeditions migrate to version 2 with their original inventory, camp, and collected resources intact. Armor, ammo, weapons, and parked vehicles persist. Settings save independently.

## Serve and validate

Serve `dist` with a static HTTP server; no build step is needed. For example:

```sh
python3 -m http.server 8000 --directory dist
```

WebGL 2 is required. Use Performance or Balanced settings if your device struggles.

```sh
node --check dist/game.js
node tests/game-logic.mjs
```

The 55 simulation checks use real Three.js geometry and raycasting with a mocked renderer and DOM. They verify gathering, crafting, damage, ammo/reload behavior, cover, vehicles, settings, save migration, and win/loss conditions. The preview browser reported disabled WebGL; actual GPU rendering, shader compilation, visual quality, and physical touch performance remain unverified in this environment.
