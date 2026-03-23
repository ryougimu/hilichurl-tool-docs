# 4_h1 Basic Info

![Basic Info](images/04/hero/1.png)

The Basic Info tab has two areas:

## Left: Attribute form

The form is divided into three groups:

**Name**

- Chinese Name (`editor.name_chs`) / English Name (`editor.name_en`) / Japanese Name (`editor.name_jp`)

**Character Attributes** (`editor.section_character`)

| Field | Description |
|-------|-------------|
| Star Rating (`editor.star`) | Character star rating, affects various attributes |
| Leadership (`editor.leader_value`) | Leadership when used as ally unit |
| Womb Capacity (`editor.womb`) | Affects number of units produced per birth |
| Base Attack (`editor.attack_base`) | Attack bonus when used as ally unit |
| Base Defense (`editor.defend_base`) | Defense bonus when used as ally unit |
| Base HP (`editor.hp_base`) | HP bonus when used as ally unit |
| Element (`editor.element`) | Character's elemental attribute |
| Core Type (`editor.core`) | Character's core type |
| Vision Type (`editor.vision`) | Character's vision type |

**Combat Attributes (Enemy Unit)** (`editor.section_combat`)

| Field | Description |
|-------|-------------|
| Attack (`editor.attack`) | Enemy unit's attack power |
| Defense (`editor.defend`) | Enemy unit's defense power |
| HP (`editor.hp`) | Enemy unit's health points |
| Speed (`editor.speed`) | Affects movement range in battle |
| Initiative (`editor.initiative`) | Affects turn order in battle |
| Move Type (`editor.move`) | Unit's movement type on the battlefield |
| Capture Rate (`editor.catch_rate`) | Base capture rate |
| Combat Power (`editor.value`) | Base combat power for auto-battle evaluation |
| Boss Behavior (`editor.boss_behavior`) | AI behavior pattern when used as enemy |
| Elemental Resistance (`editor.res`) | Resistance to own element type |

## Right: Combat icon preview

Shows the current character's combat icon. Multiple tabs let you switch between different state icons (default, exhausted, special states, etc.).

Ways to import images:

- Click the preview area to select a file  
- Drag and drop an image file directly into the preview area

After importing, the editor auto-generates variants at different sizes.
