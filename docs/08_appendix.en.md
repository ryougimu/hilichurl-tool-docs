# Chapter 8: Appendix

## Downloads {: #downloads }

Download link: [MEGA](https://mega.nz/folder/3qRU0Z6Y#zc6ftC1U3HUCB7ZWve_UbA)

![Download page](images/08/1.png)

| File | Description |
|------|-------------|
| `Hilichurl's Edit Tool_v*.7z` | Editor executable |
| `options.7z` | Options bundle (unzip, then specify directory in Settings) |
| `godot4.3.7z` | Godot engine (needed to export PCK packs) |
| `old` | Older tool versions, for rolling back if a major update fails |

## Known limitations

The current version has these limitations; future versions will improve them:

- Event categories and sub-events are preset; cannot create custom ones  
- CG and background blocks cannot be edited in the visual interface (workaround: [Source editing](04_h5_event_editor.md#source-editing))  
- Some data translations are incomplete; untranslated items show original English IDs  
- Appear condition data is auto-extracted from the game and may not be fully accurate  
- Sub-hero feature  
- Custom options  
- New World compatibility (at least editable)  

## Feedback

If you encounter bugs, data issues, or have feature suggestions, please report them on Discord.

## FAQ

### Settings dialog appears on launch?

First launch or missing settings file triggers it automatically. You need to configure Options directory and Godot executable path. See [Quick start](02_quick_start.md).

### Export says Godot path not configured?

Specify the Godot executable path in **Settings**. If you don't need PCK packing yet, turn off "Export as PCK" to export loose files directly.

### Filled in the wrong character ID?

Character ID cannot be changed after creation. To change it, create a new character and reconfigure the data.

### Can't edit event CG/background?

In the current version, CG and background are marked as base blocks and cannot be edited in the visual interface. Use [Source editing](04_h5_event_editor.md#source-editing) to modify them.

### Files in export directory disappeared?

The `export/` directory is auto-cleared before each export. If you need to keep manually modified files, copy them elsewhere before exporting.

### After switching language, some options still show English?

Data translations may be incomplete; untranslated items show original English IDs.

### Appear conditions don't work in-game?

Condition data is auto-extracted from the game and may not be fully accurate. Please report issues.

## Glossary

| Term | Description |
|------|-------------|
| Options | Editor base data bundle, containing hero templates, items, sound effects, and other game data |
| PCK | Godot resource pack format; packs multiple files into a single file |
| Install script | GDScript file generated on export; runs when the game loads to register character data |
| Block | Smallest instruction unit in an event, like one dialog line or one background switch |
| Page break | "Wait for Click" block in an event; divides the event into pages; in-game requires player click to continue |
| Base block | Block preset by event template; cannot add/edit/delete, can only move |
| Variant | Different variants of the same image (like different expression states); editor can auto-generate thumbnails |
| event_assets | Project-level shared resource directory; all characters can share backgrounds, portraits, voice |
| Source editing | Directly edit event block commands in text format; bypasses visual interface limitations |
