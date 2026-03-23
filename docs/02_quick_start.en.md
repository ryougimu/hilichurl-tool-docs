# Chapter 2: Quick start

## First launch

When you launch the editor, you see the welcome screen. On first use, a settings dialog appears automatically, asking for two paths:

![Settings dialog](images/02/1.png)

- **Options Directory** (`editor.options_root`) — Where the editor's base data bundle lives. Download the options bundle first, unzip it, then point the editor to that folder. See [Where options come from](03_options_source.md).  
- **Godot Executable** (`editor.godot_executable`) — Path to the Godot engine, needed to export PCK packs. If you don't need exports yet, configure this later.

You can change these anytime via **Settings** (`menu.settings`) in the main window's top bar.

## Create a project

Click **New** (`menu.new`) in the welcome screen's top-right corner. Choose an empty folder as the project directory. The editor generates project structure files and enters the main window.

The folder name becomes the project name.

## Add a character

After entering the main window, if the project has no characters yet, the editor area shows an empty prompt.

Click the **+** button in the character sidebar's title bar:

![Add character dialog](images/02/2.png)

- **Character ID** (`dialog.character_id`) — Unique identifier; only English letters and numbers allowed (`dialog.id_hint`). This ID is used for folder naming and data export. **Cannot be changed** after creation.  
- **Hero template** (optional) — Pick an existing in-game hero as a template. The editor auto-fills that hero's base stats and combat config. You can also skip the template and configure from scratch.

Once confirmed, the character appears in the left-hand list, and the editor area loads that character's editing interface.

## Edit the character

The editor area has multiple tabs, each responsible for one aspect:

| Tab | Purpose |
|-----|---------|
| Basic Info (`tab.basic_info`) | Character name, attributes, rarity, combat icon, avatar preview |
| Battle Config (`tab.battle_config`) | Choose attack modes, skills, and equipment |
| Resources (`tab.resources`) | Browse and import character images and audio |
| Team (`tab.appearance`) | Appear conditions, locations, minion config |
| Events (`tab.events`) | Arrange story events |
| Other (`tab.other`) | Item drop rates, etc. |

All changes auto-save; no manual action needed.

For tab details, see [Hero editing](04_hero_editing.md).

## Switch and manage characters

- **Switch** — Click a character name in the left list  
- **Search** — Type keywords in the sidebar's search box (`ui.search_placeholder`)  
- **Delete** — Click the delete button next to a character name (shows confirmation dialog)  
- **Collapse sidebar** — Click the collapse button to hide the character list and free up editing space

## Switch language

The editor supports three UI languages: 中文, English, 日本語.

The language switcher is in the welcome screen's top-right drop-down. After switching, all UI text updates immediately.

## Project management

Via the **Project** (`menu.project`) menu in the main window's top bar:

- **New** (`menu.new`) — Create a new project  
- **Open** (`menu.open`) — Open an existing project folder  
- **Close** (`menu.close`) — Close the current project and return to the welcome screen

The welcome screen remembers recently opened projects for quick access. If a project folder is moved or deleted, that entry shows as invalid.
