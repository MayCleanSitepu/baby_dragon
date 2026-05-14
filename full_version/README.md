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
- 3 skin variants: Default, Wood, Ender
- Use **Feather** to cycle colors randomly

### Combat
- Automatically targets and attacks nearby monsters within 35 blocks
- Shoots custom fireballs every 2-4 seconds
- Fireball deals 8 damage + knockback on hit
- Fireball has flame particle effect while flying

### Animations
- Idle, Walk, Sit, Attack, Special Attack, Tamed celebration, Death
- All animations have matching sound effects

### Sound Effects
- Ambient growl (periodic)
- Attack fire sound
- Special attack charge + flap sounds
- Death roar
- Hurt sound on taking damage

### Particles
- Fire charge glow during special attack charge-up
- Fire impact burst on fireball hit
- Particles emit from snout locator (mouth position)

### UI Notifications (actionbar)
- Dragon Tamed
- Color Changed
- Dragon Sitting / Standing
- Dragon Attack Mode (manual test)
- Dragon Special Attack (manual test)
- Dragon has Fallen (on death)

### Loot
- Drops Dragon Breath and Fire Charges on death

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
- `test.ogg` is a placeholder -- replace with proper sound files per event in `sound_definitions.json`
- Sound files must be `.ogg` format (Vorbis)

---

## Sound Replacement Guide

To replace placeholder sounds, add `.ogg` files to `RP/sounds/` and update `sound_definitions.json`:

```json
"baby_dragon.attack": {
    "category": "neutral",
    "sounds": [{ "name": "sounds/your_attack_sound", "volume": 0.8, "pitch": 1.3 }]
}
```

Events: `baby_dragon.idle`, `baby_dragon.attack`, `baby_dragon.charge`, `baby_dragon.flap`, `baby_dragon.death`

---

## Bedrock Version

Built and tested on Bedrock 1.20+. Minimum engine version: 1.20.0.
