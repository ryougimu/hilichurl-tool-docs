# 4_h3 Resources

![Resources](images/04/hero/3.png)

The Resources tab manages character images and audio. It has a three-column layout:

- **Left: category tree** — Resource groups by category  
- **Middle: resource list** — All items in the selected category and their completion status  
- **Right: preview** — Preview the selected resource; supports variant viewing  

You can import resources by dragging files into the preview area.

**You only need to configure the resources you want; no need to fill everything.**

## Resource categories

| Category | Description | Format |
|----------|-------------|--------|
| Portrait (`resource.portrait`) | Character portraits with multiple expression states | PNG |
| Mating (`resource.mating`) | Mating scene images, including dragging and various monster types | PNG |
| CG (`resource.cg`) | Story event CG images | PNG |
| Torture (`resource.torture`) | Torture-related images | PNG |
| Voice (`resource.voice`) | Character combat voice | OGG |

## Portrait states

Portraits include these expression states; each state can have multiple variants:

| English | Chinese |
|---------|---------|
| Disobedient (`resource.state.angry`) | 反抗 |
| Submissive (`resource.state.sad`) | 顺从 |
| Frightened (`resource.state.frightened`) | 恐惧 |
| Corrupted (`resource.state.corrupted`) | 淫乱 |
| Helpless (`resource.state.helpless`) | 绝望 |
| Mask (`resource.state.mask`) | 面具 |
| Orgasm (`resource.state.orgasm`) | 高潮 |
| Sad | 悲伤 |

## Mating animation states

| State | Description |
|-------|-------------|
| Dragging (`resource.state.dragging`) | Dragging animation |
| Hilichurl (`resource.monster.hilichurl`) | Hilichurl scene |
| Rifthound (`resource.monster.rifthound`) | Rifthound scene |
| Slime (`resource.monster.slime`) | Slime scene |
| Tentacle (`resource.monster.tentacle`) | Tentacle scene |
| Vishap (`resource.monster.vishap`) | Vishap scene |
| Whopperflower (`resource.monster.whopperflower`) | Whopperflower scene |

## Event CG

| Number | Description |
|--------|-------------|
| 01 | Capture Event (`resource.cg.01`) |
| 03 | Birth Event (`resource.cg.03`) |
| 04 | Altar Event (`resource.cg.04`) |
| 05 | Torture Event (`resource.cg.05`) |
| 07 | Brothel Event (`resource.cg.07`) |
| 10 | Common Event (`resource.cg.10`) |

## Voice

| Type | Description |
|------|-------------|
| Chosen (`resource.voice.chosen`) | Voice when selected |
| DEFEATED (`resource.voice.defeated`) | Voice when defeated |
| Retreat (`resource.voice.retreat`) | Voice when retreating |
| Elemental Burst (`resource.voice.elemental_burst`) | Voice when using elemental burst |
| Elemental Skill (`resource.voice.elemental_skill`) | Voice when using elemental skill |
| Heavy Attack (`resource.voice.heavy_attack`) | Voice for heavy attack |
| Mid Attack (`resource.voice.mid_attack`) | Voice for mid attack |
| Light Attack (`resource.voice.light_attack`) | Voice for light attack |

## Auto-generation

For portrait and mating animation categories, importing a large image auto-generates a corresponding thumbnail (stored in the Animated folder). You only need to import the original large image; thumbnails are created automatically.
