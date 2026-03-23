# 4_h5 Event Editor

![Event Editor](images/04/hero/5.png)

The Event Editor arranges story events for a character. Each event is a series of "blocks" that execute in order during gameplay.

## UI layout

The Event Editor has two areas:

- **Left: event navigation tree** — Lists all editable events by category  
- **Right: edit & preview area** — Side-by-side preview panel and block edit panel  

You can drag the divider between preview and edit panels to adjust width.

## Event navigation

The left tree organizes events by category.

Some events have multiple sub-events by character state:

| Code | State |
|------|-------|
| a | Disobedient (`event_editor.status_angry`) |
| b | Submissive (`event_editor.status_sad`) |
| c | Helpless (`event_editor.status_helpless`) |
| d | Corrupted (`event_editor.status_corrupted`) |

| Category | Contained events |
|----------|------------------|
| Appeared (`event.appeared`) | Appeared Event |
| Captured (`event.captured`) | Capture Event |
| Give Birth (`event.give_birth`) | a / b / c / d states |
| Altar (`event.altar`) | 1=Start / 2=End |
| Torture (`event.torture`) | Normal / Corrupted / Broken |
| Brothel (`event.brothel`) | a / b / c / d states (see special note below) |
| Bride (`event.wedding`) | a / b / c / d states |
| Bride SP (`event.wedding2`) | a / b / c / d states |

Click an event name to open editing.

### Event notes

**Base blocks**

Most events contain preset base blocks (like CG, Background) auto-generated from templates. These cannot be deleted but can be moved.

**Prerequisite resources (frontload)**

All events except Appeared need corresponding CG images. Each event requires different CG numbers (e.g., Capture uses 01 series, Give Birth uses 03 series). If required CGs are missing, a ⚠ warning appears in the toolbar. Hover over the warning to see which files are missing.

**Extra info**

Some event categories (like Wedding2/Bride SP) need extra info. In the event tree, these categories show a ✎ edit button next to their name.

Currently supported extra: **Title setting**—the title the player gets after defeating this character. Fill in translations for three languages (Chinese/English/Japanese). If not set, the category shows a ⚠ prompt. When you enable events in this category, title translations are written to game data on export.

**Brothel event note**

Brothel only allows Helpless(c), Corrupted(d), and Mask state characters. Mask state is special—at runtime it follows the current actual state logic (Disobedient/Submissive/Helpless/Corrupted are all possible), so edit permission is retained. At minimum, you can edit just Corrupted(d).

### Enable/disable events

Each event has an **Enable** (`event.enable`) toggle in the top-right. Only enabled events are included on export.

### Resource warnings

Some events need corresponding CG images. If required images are missing, a **⚠** warning appears next to the event name. Import the matching CGs in the Resources tab to clear the warning.

## Block list

The right panel shows all blocks in the current event as colored cards.

### View modes

Two view modes, switch via top buttons:

- **All** (`event_editor.view_all`) — Shows all blocks in the event  
- **Paged** (`event_editor.view_paged`) — Uses "Wait for Click" blocks as page boundaries. Preview panel and edit panel have independent page navigation.

### Block operations

- **Add Block** (`event_editor.add_block`) — Click to pick a block type from the menu  
- **Edit block** — Click a block card to open an edit window  
- **Delete block** — Click the ✕ button in the block card's top-right  
- **Drag to reorder** — Hold the ≡ handle on the left side of the card and drag up/down  
- **Source edit** — See [Source editing](#source-editing) below

Base blocks from event templates cannot be deleted but can be moved.

## Block types

18 block types in several categories:

### Dialog

| Block Type | Game Command | Purpose |
|-----------|--------------|---------|
| Speaker (`event_editor.type_name`) | `name:` | Set current speaker name; leave empty to clear |
| Dialog (`event_editor.type_dialog`) | `dialog:` | Show dialog box text |

### Visual

| Block Type | Game Command | Purpose |
|-----------|--------------|---------|
| Background (`event_editor.type_background`) | `background:` | Switch background image |
| CG (`event_editor.type_cg`) | `CG:` | Show/clear CG image (layered over background) |
| Set Figure (`event_editor.type_figure`) | `figure1:` / `figure2:` | Place portrait at right(1) or left(2); leave empty to show current character |
| Hide Figure (`event_editor.type_hide_figure`) | `hide_figure1:` / `hide_figure2:` | Remove portrait at specified position |
| Turn Black (`event_editor.type_turn_black`) | `turn_black:` | Black screen mask until next background block |
| Shake (`event_editor.type_shake`) | `shake:` / `shake_x:` | Screen shake, vertical or horizontal, adjustable intensity |

### Audio

| Block Type | Game Command | Purpose |
|-----------|--------------|---------|
| BGM (`event_editor.type_bgm`) | `bgm:` | Switch background music; leave empty to stop |
| Sound Effect (`event_editor.type_sound`) | `sound:` | Play one-shot sound effect, adjustable volume |
| Voice (`event_editor.type_voice`) | `voice:` | Play custom voice file (Voice/ directory), adjustable volume |
| Preset Voice (`event_editor.type_preset_voice`) | `preset_voice:` | Play preset voice keyword, adjustable volume |
| Loop Voice (`event_editor.type_cont_voice`) | `continue_voice:` | Start looping voice, adjustable volume and speed |
| Stop Loop Voice (`event_editor.type_cont_voice_end`) | `continue_voice_end:` | Stop looping voice |
| Loop Sound (`event_editor.type_cont_sound`) | `continue_sound:` | Start looping sound effect, adjustable volume and speed |
| Stop Loop Sound (`event_editor.type_cont_sound_end`) | `continue_sound_end:` | Stop looping sound effect |

Voice is mainly for character voice and needs to be imported first. In the current tool implementation, voice and preset_voice are essentially the same.

### Control

| Block Type | Game Command | Purpose |
|-----------|--------------|---------|
| Delay (`event_editor.type_auto`) | `auto:` | Wait specified seconds then auto-advance; player click can skip |
| Wait for Click (`event_editor.type_pause`) | (blank line) | Pause for player click; also serves as page boundary |

> **Note**: The game engine also supports `hide_background`, `signal`, `icon`/`end_icon`, etc. The editor doesn't provide corresponding block types yet. To use these commands, enter them manually via source edit mode.

## Editing block content

Click a block card to open an edit window. Content varies by block type:

- **Text** (speaker/dialog) — Input box or multi-line text box  
- **Image** (background/CG/portrait) — Image picker with left list, right preview, supports import  
- **Audio** (BGM/sound/voice) — Audio picker with search, preview, and import  
- **Numeric** (volume/speed/shake intensity) — Number slider  
- **Options** (portrait position/shake direction) — Drop-down menu  

## Preview panel

The center preview panel renders event effects in real time:

- Background and CG layered display  
- Portraits on left and right sides  
- Dialog box (speaker name + dialog text)  
- Current BGM name  
- Black screen mask effect  

In paged mode, the preview accumulates state by current page—backgrounds, portraits, etc. set on previous pages carry forward.

## Resource sources

Images and audio in events are searched in this priority:

1. **Character directory** — Current character's Figure/CG folders  
2. **Project shared** — Project's event_assets directory (shared by all characters)  
3. **Global presets** — Preset resources in the options bundle  

Resources imported via the import button in edit windows are auto-stored in the project shared directory.

## Source editing {#source-editing}

Click **Source Edit** (`event.source_edit`) in the toolbar to open a text edit window and directly edit the event's raw command format.

![Source Edit](images/04/hero/6.png)

### Why source editing?

In the current version, CG and background blocks are marked as base blocks and cannot be edited or deleted in the visual interface (a design limitation; future versions will improve this). If you need to customize these, source editing is currently the only way.

Additionally, the game engine supports some commands the editor doesn't yet have visual support for (like `hide_background`, `signal`, `icon`/`end_icon`). You can enter these manually via source editing.

### Format

One command per line, format `command:parameters`. A blank line means wait for click (page break).

```
background:bg_forest.webp
name:Alice
dialog:Where am I...

CG:anna_01_1.webp
shake:5
name:Alice
dialog:What happened?!

```

- `name:` sets speaker, `dialog:` shows dialog text; they are independent commands  
- Commands with multiple parameters use space-separated key-value pairs: `sound:sound=slash_1 vol=0`  
- Template variables are supported: `{{heroine}}` is replaced with the character type name in-game  

### Important notes

- Source editing directly manipulates raw data. Format errors may prevent the event from running  
- Resource files referenced in source must exist; the editor won't auto-import. Resource directories:
  - Backgrounds: `{project}/event_assets/Background/` or options presets  
  - Portraits: `characters/{characterID}/Figure/` or `{project}/event_assets/Figure/`  
  - CG: `characters/{characterID}/CG/`  
  - Voice: `characters/{characterID}/Voice/` or `{project}/event_assets/Voice/`  
  - BGM/sound: From options bundle (`audio/bgm/`, `audio/sound/`)  
- After saving, the visual interface syncs; you can verify effects in the preview panel
