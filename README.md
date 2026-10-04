# Carblo

Carblo is a small isometric arena brawler written in Rust with [macroquad](https://github.com/grovesNL/macroquad). You control a stick-figure hero on a 20×20 tile map: click to move, fight off monsters that chase you, and grab gold before they drag you down.

## Features

- Isometric 20×20 tile map with walls and obstacles
- Click-to-move hero with BFS pathfinding
- Monsters that chase you with BFS and attack when adjacent
- Combat with floating damage numbers
- Gold pickups worth +100 score
- HP and score HUD
- Menu → Playing → Game Over flow with victory and defeat screens

## Getting Started

Prerequisites: a recent Rust toolchain (`rustc` and `cargo`).

```bash
cargo run
```

## How to Play

| Input | Action |
| --- | --- |
| `Enter` | Start a new game from the menu |
| Left click | Move the hero to the clicked tile (path computed with BFS) |
| Walk into a monster | Attack it (10 damage per hit) |
| `Enter` (after game over) | Return to the menu |

- Monsters deal 5 damage when they move next to you.
- Collect gold to raise your score.
- Wipe out all the monsters to win; the game ends when your HP hits 0.

## Project Structure

```
.
├── Cargo.toml      # package manifest (macroquad dependency)
└── src/
    └── main.rs     # the whole game: map, pathfinding, combat, rendering
```

## Tech

- Rust (edition 2024)
- [macroquad 0.4.16](https://crates.io/crates/macroquad) — game loop, input, and 2D drawing
