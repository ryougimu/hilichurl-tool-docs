# Chapter 7: Configuration reference

## Project directory structure

After creating a project, the project directory file structure looks like this:

```
{ProjectName}/
├── project.json                 Project config file
├── characters/                  Character data directory
│   └── {characterID}/
│       ├── data.json            Character data (attributes/combat/appearance, etc.)
│       ├── event.json           Event metadata (enable status/extra info)
│       ├── Event/               Event block files (one JSON per event)
│       ├── Unit/                Combat icon (small)
│       ├── Unit_H/              Combat icon (large)
│       ├── Figure/              Portraits
│       ├── CG/                  Event CG images
│       ├── Mating/              Mating scene images
│       ├── Animated/            Thumbnails (auto-generated)
│       ├── Icon/                Avatar icons
│       ├── Torture/             Torture images
│       └── Voice/               Character voice
├── event_assets/                Project-level shared event resources
│   ├── Background/              Shared backgrounds
│   ├── Figure/                  Shared portraits
│   └── Voice/                   Shared voice
└── export/                      Export output directory (cleared before each export)
```

## Events

Current event categories and sub-events are preset; you cannot create custom ones. For a detailed event list, see [Event Editor](04_h5_event_editor.md).

Event files are stored in `characters/{characterID}/Event/`, with filenames formatted as `{eventID}_{characterID}.json` (e.g., `captured_mika.json`).

## Block data format

In event files, blocks are stored as a JSON array, each element a line of text command:

```json
{
  "event": [
    "background:bg_forest.webp",
    "name:Alice",
    "dialog:Hello!",
    "",
    "CG:mika_01_1.webp",
    "sound:sound=slash_1 vol=0",
    "dialog:What happened?",
    ""
  ]
}
```

- Each array element corresponds to one block  
- Empty string `""` means wait for click (page break)  
- Format is `command:parameters`; multiple parameters use space-separated key-value pairs  

## Character data structure

Character data is stored in `characters/{characterID}/data.json`. Main top-level fields:

| Field | Description |
|-------|-------------|
| translation | Character name translations (chs/en/jp) |
| heroine_info | Character attributes (star rating/leadership/element, etc.) |
| unit_info | Combat config (attack modes/skills/equipment) |
| unit_info_h | Combat config (enemy perspective) |
| appearance | Appearance settings (appear conditions/location/minions/speed) |
| brothel_info | Item drop rate list |
