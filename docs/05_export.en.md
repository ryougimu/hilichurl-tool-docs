# Chapter 5: Export & packing

> **Warning: Export fully clears the `export/` directory each time!** If you've manually modified files in the export directory, copy them elsewhere first or they'll be permanently lost.

After editing character data, export it to a game-loadable format. Click **Pack** (`menu.pack`) in the main window's top bar to open the export dialog.

## Export settings

![Export dialog](images/05/1.png)

| Setting | Description |
|---------|-------------|
| Package ID (`editor.export_id`) | Export package identifier (e.g., `21`), corresponding to output filename `patch_21.pck` |
| Export as PCK (`editor.export_as_pck`) | Whether to pack resources into a single PCK file. Turn off to output loose resource files |
| Simple Pack (`editor.export_simple_pack`) | Only available when PCK is on; generates a smaller PCK (see details below) |

The output path is fixed to the `export/` folder under the project directory.

The dialog remembers your last settings and restores them next time. Click **View Export Guide** (`editor.export_guide`) to see detailed export instructions.

## Export process

Export runs in these stages automatically (**Note: first clears the `export/` directory**):

1. **Resource consolidation** — Scan all character directories, copy resource files to output, generate Install script  
2. **Project config generation** — Generate Godot project config files (needed for PCK packing)  
3. **PCK packing** — Call Godot engine to pack resources into a `.pck` file (only when PCK is on)  
4. **Event file output** — Export all enabled events as individual JSON files  

## Pack modes

### PCK mode (default)

All resources packed into a single `patch_{id}.pck` file, plus Install script and event files.

### Simple Pack mode

Generates a smaller PCK file containing only scripts and voice resources. Larger resources like images are output separately, not packed into the PCK. Suitable for scenarios needing smaller PCK size.

### Non-PCK mode

No packing; directly output loose resource folders + Install script + event files.

## Output contents

After export completes, the `export/` directory contains:

| Content | Description |
|---------|-------------|
| `patch_{id}.pck` | Packed resource file (PCK mode only) |
| `Install_{id}.gd` | Install script; runs when the game loads to register character data |
| `Event/*.json` | Enabled event files, one per event |
| Resource folders | Unit/Figure/CG/Voice and other resource directories |

## Prerequisites

- Exporting PCK requires configuring the Godot executable path (in **Settings**)  
- At least one character with saved data
