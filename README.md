# L Game Variant

Minimal, playable Godot 4 project for a local 2-player board game based on a custom variant of the L Game.

## Overview

- Engine: Godot 4.x
- Language: GDScript
- Type: 2D
- Players: Local 1v1 or vs Computer
- Board: 4x4 grid

This project implements a compact L Game variant with:

- 2 player L-pieces
- 2 neutral 1x1 pieces
- mouse and keyboard controls
- a simple computer opponent

## Variant Rules

Each turn:

1. Move your own L-piece.
2. You may rotate or flip it before placing.
3. The L-piece must:
   - stay inside the 4x4 board
   - not overlap the other L-piece
   - not overlap neutral pieces
   - move to a different set of cells
   - still touch its previous position
4. After moving the L-piece, you may move at most 1 neutral piece.
5. A neutral piece:
   - may move only 1 square
   - may not move diagonally
   - may move only up, down, left, or right
   - may move only to an empty cell
6. End your turn after moving 0 or 1 neutral piece.
7. You win if the opponent has no legal L-piece move after your turn ends.

## Controls

### L-piece

- Left Click: Select and place your L-piece
- Right Mouse Button: Rotate
- Middle Mouse Button: Flip
- `R`: Rotate
- `F`: Flip

### Neutral piece

- Left Click: Select a neutral piece, then click a legal neighboring cell

### UI

- `End Turn`: Finish the turn
- `Restart`: Reset the match
- `1v1`: Local 2-player mode
- `1v` + monitor icon: Play against the computer opponent

## Computer Opponent

The current computer opponent is intentionally simple:

- it generates legal full turns
- it chooses one valid turn
- it is meant as a lightweight, easy opponent rather than a strong strategy AI

## Project Structure

```text
scenes/
  Main.tscn

scripts/
  Main.gd
  LGameState.gd

themes/
  ui_theme.tres
```

## Main Files

- `scenes/Main.tscn`
  Main scene and editable UI layout.

- `scripts/Main.gd`
  Input, drawing, UI state, and computer opponent flow.

- `scripts/LGameState.gd`
  Core rules and board state logic.

- `themes/ui_theme.tres`
  Central theme settings for UI font sizes.

## Run

1. Open the project in Godot 4.
2. Open `scenes/Main.tscn` or run the project directly.
3. Play in local mode or toggle the computer opponent.

## Notes

- The UI is intentionally simple and editor-friendly.
- Text and layout are designed to be adjusted directly inside Godot.
- The game uses no external gameplay assets.
