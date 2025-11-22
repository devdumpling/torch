# Torch
## Learning Project for Wick

**Engine:** Godot 4.5  
**Scope:** 1-3 days  
**Purpose:** Learn Godot fundamentals before building Wick

---

## Core Concept

You're a scout exploring a small ruined temple. You have a torch with limited fuel. Find 3 sacred relics and return to the entrance before your torch dies.

---

## Scope

**Single Area:**
- Small ruined temple (5-6 connected rooms)
- 20x20 tile map maximum

**Core Mechanics:**
- Isometric 8-direction movement
- Torch with fuel that depletes over time
- Fog of war that reveals as you explore
- Simple collision detection

**Win/Loss:**
- Win: Collect all 3 relics, return to entrance
- Lose: Torch fuel runs out

**No Combat, No Narrative** - Pure exploration mechanics

---

## Learning Goals

- [ ] Godot scene/node system
- [ ] Isometric tilemap setup
- [ ] Player movement and collision
- [ ] Light radius system (Area2D or shader)
- [ ] Fog of war implementation
- [ ] Resource management (fuel gauge)
- [ ] UI elements
- [ ] Basic game state (win/lose)

---

## Technical Approach

**Player:**
- Node2D root
- Sprite2D for visual
- CollisionShape2D for physics
- Script for movement

**World:**
- TileMap for level geometry
- Fog of war layer
- Light system

**UI:**
- Fuel gauge
- Relic counter
- Win/lose screens

---

## Art Style

Programmer art only. Focus on mechanics, not aesthetics.

---

## Implementation Steps

### Phase 1: Player Movement (Day 1)
1. Create Player scene with Sprite2D
2. Add movement script (8-direction isometric)
3. Add collision shape
4. Test basic movement

### Phase 2: World & Collision (Day 1)
1. Create World scene with TileMap
2. Set up isometric tiles (programmer art)
3. Add collision layers
4. Test player collision with walls

### Phase 3: Light & Fog of War (Day 2)
1. Add light radius around player
2. Implement fog of war reveal system
3. Add torch fuel mechanic (depletes over time)
4. Create fuel gauge UI

### Phase 4: Game Loop (Day 3)
1. Add 3 relic collectibles
2. Implement win condition (all relics + return to start)
3. Implement lose condition (fuel runs out)
4. Add simple UI feedback
5. Polish and bug fixes

---

## Technical Notes

**Isometric Movement:**
- Input axes need to be transformed for isometric grid
- Diagonal movement should be normalized
- Use `Vector2` for 2D positioning

**Fog of War:**
- Option 1: TileMap layer that clears tiles as player explores
- Option 2: Shader-based darkness that reveals via Area2D
- Start with TileMap approach (simpler)

**Light System:**
- Area2D for detection radius
- PointLight2D for visual glow
- Separate visual light from gameplay light radius

**Fuel Management:**
- Simple float that decreases over time
- `delta` in `_process()` for time-based depletion
- UI ProgressBar for visual feedback

---

## File Structure

```
torch/
├── project.godot
├── README.md
├── GAME_DESIGN.md
├── .gitignore
├── scenes/
│   ├── player/
│   │   └── player.tscn
│   ├── world/
│   │   └── world.tscn
│   └── ui/
│       ├── fuel_gauge.tscn
│       └── game_over.tscn
├── scripts/
│   ├── player.gd
│   ├── world.gd
│   └── game_manager.gd
└── assets/
    ├── sprites/
    │   └── (placeholder images)
    └── tilesets/
        └── temple_tiles.tres
```

---

## Success Criteria

You've successfully completed this learning project when:
- Player moves smoothly in 8 directions (isometric)
- Fog of war reveals explored areas
- Torch fuel depletes and game ends when empty
- Relics can be collected
- Win/lose states work correctly
- You understand Godot's scene/node system well enough to start Wick
