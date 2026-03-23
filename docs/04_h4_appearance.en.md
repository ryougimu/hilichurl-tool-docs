# 4_h4 Team

![Team](images/04/hero/4.png)

The Team tab (`tab.appearance`) has four configuration sections:

## Appear Condition (`appearance.appear_condition`)

Set the conditions the character must meet to appear in-game. You can add multiple conditions; the character appears when all are satisfied.

Newly created characters default to "Occupied Nameless Sword Grave."

### Condition types

Each condition has two parts: "type" and "target." Click **Add Condition** (`appearance.add_condition`), pick the condition type on the left, then pick the specific target on the right.

| Condition Type | Target Range | Meaning |
|----------------|--------------|---------|
| Appeared | Character | Specified character has appeared |
| Defeated | Character | Specified character has been defeated |
| Escaped | Character | Specified character has escaped |
| Occupied | Stronghold | Specified stronghold is occupied |
| Attacked | Stronghold | Specified stronghold is attacked |
| Destructed | Building | Specified building is destroyed |
| Has Item | Item | Player has specified item |

Each condition type can only be added once. Adding the same type again overwrites the old condition.

> **Note**: Condition types and target lists are auto-extracted from game data and may not be fully accurate. If a condition doesn't trigger properly or causes an error in-game, please report it.

## Appear Location (`appearance.appear_location`)

Choose the character's appear location from the stronghold list.

## Minion Configuration (`appearance.section_minion`)

Configure minions the character brings when appearing as an enemy.

- **Has Minion** (`appearance.has_minion`) — Whether to bring minions; checking this shows the options below  
- **Minion Unit** (`appearance.minion_unit`) — Choose the minion unit type  
- **Minion Count** (`appearance.minion_num`) — Set the number of minions  

## Other Settings (`appearance.section_other`)

- **Ally Minion Limit** (`appearance.minion_limit`) — Movement type restrictions for ally minions when this character is on your side  
- **Movement Speed** (`appearance.speed`) — The character's movement speed
