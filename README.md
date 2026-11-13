# Dungeon Crawler

A turn-based, procedurally generated dungeon crawler built with [p5.js](https://p5js.org/). Pick a class, explore randomly generated floors, fight enemies, collect loot, trade with merchants, and defeat each floor's boss to go deeper.

**Contributors:** Maaz Ali, Urvi Yadav, Naitik Jain, Imroz Gill

**Tutorial:** [Google Doc](https://docs.google.com/document/d/1qXCOf1iQT_jbtc7IGTpX79HJmIzkSSSOtnIZziTbFjo/edit?usp=sharing)

## Features

- **Three classes:** Warrior (sword), Archer (bow), and Wizard (fire and poison wands)
- **Procedural levels:** every floor has new rooms, corridors, traps, a merchant, and a boss room
- **Turn-based combat:** enemies act after you do, and you can charge attacks for extra range
- **Status effects:** poison, fire, stun, bleed, and vines, applied by traps, weapons, and wands
- **Items and gear:** potions, melee and ranged weapons, wands, armor, and leggings
- **Inventory, quickslots, and a shop** to manage and buy gear
- **Minimap** showing the layout and nearby enemies

## Running the game

The game uses ES modules, so it has to be served over HTTP rather than opened as a file. From the project folder, run:

```bash
python3 -m http.server 8000
```

Then open <http://localhost:8000>. The VS Code "Live Server" extension works too.

Each push to `main` also deploys the game to GitHub Pages through the workflow in `.github/workflows/static.yml`.

## Controls

| Key | Action |
| --- | --- |
| ← / → then Enter | Choose a class on the title screen |
| W A S D | Move, or attack an enemy in that direction |
| Shift + W A S D | Charged attack |
| Arrow keys | Aim your weapon (shoots right away with ranged weapons) |
| E | Attack the aimed tile, or talk to a merchant to open the shop |
| O | Pick up the item on your tile |
| X | Open or close the inventory |
| Arrow keys + Enter | Move through and use inventory items, or buy from the shop |
| Backspace | Move the quickslot item to inventory, or drop the selected inventory item |
| 1 – 4 | Select a quickslot |
| R | Restart |

To reach the next floor, defeat the boss and step onto the stairs.

## Project structure

| File | Purpose |
| --- | --- |
| `index.html` | Entry point that loads p5.js and `main.js` |
| `main.js` | Game loop, turn handling, and keyboard input |
| `generateWorld.js` | Procedural room, corridor, trap, enemy, merchant, and boss generation |
| `entity.js` | Player, enemy, and boss stats, AI, combat, and status effects |
| `item.js` | Item definitions, attack ranges, inventory, and shop |
| `render.js` | Drawing the world, UI, health bar, inventory, shop, and minimap |
| `assets/` | Sprite sheets, tilesets, GUI art, and fonts |
