# Baby Dragon Addon - Bedrock Edition

A custom Baby Dragon mob addon for Minecraft Bedrock Edition. The dragon spawns in mountain biomes, can be tamed, fights monsters, and shoots fireballs.

---

## Features

### Spawning
- Spawns naturally in **Mountains** and **Extreme Hills** biomes
- Spawns in groups of 1-2
- Surface spawn only, in daylight

### Taming
- Tame with **Carrot**
- Once tamed, dragon follows owner
- Use **Stick** to toggle sit/stand

### Color Variants
- random color spawn
- 3 skin variants: Default, Wood, Ender
- Use **Feather** to cycle colors randomly

### Combat
- Automatically targets and attacks nearby piglin
- Shoots custom fireballs to piglin
- Fireball deals 8 damage + knockback on hit

### Animations
- Idle, Walk, Sit, Attack, Special Attack, Tamed celebration, Death
- All animations have matching sound effects

### UI Notifications (actionbar)
- Dragon Tamed
- Color Changed
- Dragon Sitting / Standing
- Dragon Attack Mode (manual test)
- Dragon Special Attack (manual test)
- Dragon has Fallen (on death)

---

## Controls

| Item in hand | Action |
|---|---|
| Carrot | Tame dragon |
| Stick | Sit / Stand toggle |
| Feather | Cycle color |
| Apple | Trigger attack animation (test) |
| Glass Bottle | Trigger special attack animation (test) |

---

## File Structure

```
full_version/
  behavior_packs/BabyDragonBP/
    entities/
      baby_dragon.json          - Main dragon behavior
      dragon_fireball.json      - Fireball projectile behavior
    spawn_rules/
      baby_dragon_spawn.json    - Biome spawn config
    loot_tables/entities/
      baby_dragon.json          - Death loot

  resource_packs/BabyDragonRP/
    entity/
      baby_dragon.entity.json   - Dragon client config
      dragon_fireball.entity.json
    animations/
      hp3_bp.pet_baby_dragon.animation.json
      dragon_fireball.animation.json
    animation_controllers/
      baby_dragon.controller.json
    models/entity/
      pet_baby_dragon.geo.json  - Dragon model (has firebreath locator at snout)
      dragon_fireball.geo.json  - Fireball cube model
    particles/
      dragon_fire.particle.json     - Impact burst
      dragon_fire_charge.particle.json - Charge-up glow
    textures/entity/
      pet_baby_dragon_cut.png   - Default skin
      pet_baby_dragon_wood_cut.png
      pet_baby_dragon_ender_cut.png
      dragon_fireball.png
    sounds/
      test.ogg                  - Placeholder sound (replace with real SFX)
    sounds.json                 - Entity sound event bindings
    sound_definitions.json      - Custom sound event definitions
    render_controllers/
      baby_dragon.render_controllers.json
      dragon_fireball.rc.json
    texts/
      en_US.lang
```

---

## Known Limitations

- Fireball does not set hit targets on fire (Bedrock `ignite` on_hit limitation)

---

## Sound Replacement Guide

To replace placeholder sounds, add `.ogg` files to `RP/sounds/` and update `sound_definitions.json`:



## Bedrock Version

Built and tested on Minecraft Bedrock V26.21
