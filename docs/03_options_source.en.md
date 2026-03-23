# Chapter 3: Where options come from

> **Note**: The options directory structure is still evolving; future versions may reorganize it. You don't need to understand every detail—just its purpose and how to configure it.

## What are options?

The editor is just a tool. It needs to know which hero templates, items, sound effects, backgrounds, and other base data exist in the game so it can offer the right choices in its UI.

This base data lives in a directory called **options**. Think of it as the editor's "asset library"—the editor reads from it to populate drop-downs, load icons, preview sounds, and so on.

## How to get it

Download the options bundle, unzip it anywhere on your local machine, then point the editor to that folder in **Settings** (`menu.settings`). For the download link, see [Appendix - Downloads](08_appendix.md#downloads).

## Directory structure

The options directory contains several areas:

```
options/
├── generated/       Hero, item, skill, and other game base data
├── audio/           Sound effects and BGM resources
├── images/          Backgrounds and other image resources
├── event/           Event template files
├── template/        Default template for new characters
└── md/              Built-in user guide (multi-language)
```

### generated/ — Game base data

The core part. Contains hero templates, items, skills, minion units, and other game data plus their icon assets. When you pick a hero template during character creation, or choose options in battle config, or see item drop lists, all that comes from here.

### audio/ — Sound effects & BGM

Sound effects and BGM available in the event editor.

### event/ — Event templates

Predefined event template files, one per event type (like `captured.json`, `give_birth_a.json`, etc.). When you create a new event, the editor can quickly generate initial content from these templates.

### images/ — Image resources

Backgrounds, UI images, battle unit sprites, and other images selectable in the event editor.

### template/ — Character template

Default data template used when creating a new character. If you don't pick a hero template, the character starts with this baseline.

### md/ — User guide

Built-in operation guide (multi-language support).

## Path search order

The editor looks for the options directory in this order:

1. **User setting** — The path you manually specify in **Settings** (recommended)  
2. **Adjacent to executable** — An `options/` folder next to the editor executable

## How the editor uses this data

| What you see in the editor | Source |
|----------------------------|--------|
| Hero template list when creating a character | generated/ |
| Attack modes, skill choices in battle config | generated/ |
| Item list and icons in drop config | generated/ |
| Backgrounds, portraits in event editor | images/ |
| BGM and sound effects in event editor | audio/ |
| Initial event template content | event/ |
| Multi-language display for options | generated/ |

## Design notes

**Why separate base data from the editor?**

Keeping base data separate has benefits:

- **Independent updates** — Update the options bundle without updating the editor itself  
- **Size control** — Options contain many icons and audio files; keeping them separate prevents the editor from bloating
