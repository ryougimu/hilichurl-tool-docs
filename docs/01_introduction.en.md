# Chapter 1: Meet the editor

## What is this?

A lightweight game mod editor. It currently supports creating new hero characters and editing some story events.

The editor is under active development; more features will arrive over time.

## What can it do?

- **Hero editing** — Configure a character’s basic info, combat stats, resources, events, and more  
- **Project management** — Create and manage multiple independent projects, each with multiple characters  
- **Export & pack** — Pack character data and assets into a format the game can load  

For details, see [Quick start](02_quick_start.md) and the following chapters.

## Overall workflow

A typical workflow looks like this:

```
Preparation              Creation                    Release
───────────              ────────                    ───────
Download options    →    Create project         →    Export & pack
Prepare mod assets       Add characters               Choose pack mode
(portraits / CG /        Edit stats
 voice, etc.)            Arrange events
                         Import assets
```

- **Preparation**: Download the options bundle and prepare your mod assets (portraits, CGs, voice files, etc.). The options bundle supplies base data the editor needs (hero templates, item lists, sound libraries, etc.). See [Where options come from](03_options_source.md).  
- **Creation**: Day-to-day work—create projects, add characters, edit fields, and import your assets.  
- **Release**: Export finished character data into a game-ready format. See [Export & packing](05_export.md).

## UI overview

The editor has two main screens:

### Welcome screen

![Welcome screen](images/01/1.png)

When you launch the editor, you first see the welcome screen. It lists recently opened projects. You can:

- Open a project by clicking its name  
- Create a **New** project  
- **Open** an existing project folder  
- Change the UI language (中文 / English / 日本語)

On first launch, you must set two paths: the **Options directory** and the **Godot executable**. You can change these later in **Settings**.

### Main window

![Main window](images/01/2.png)

After opening a project, the main window has three areas:

- **Left: character sidebar** — Lists all characters in the project; supports search and collapse  
- **Center: editor area** — Tabs for the current character type  
- **Bottom: Log** — Operation log to confirm saves, imports, etc.

The top bar provides **Project** (New / Open / Close), **Tools**, **Pack**, and **Settings**.

## Design notes

**Auto-save** — Changes are saved automatically; you do not need a manual Save button.

**Data-driven options** — Event types, selectable lists, and similar content come from the options bundle. Updating the bundle updates what the editor offers.
