# Snake Game

A minimal browser Snake game — one HTML file, no dependencies, no build step.

## Play

Open `index.html` in any browser (double-click it, or serve the folder with any static server).

## Controls

- **Desktop**: arrow keys to move.
- **Mobile/touch**: tap the on-screen ↑ ↓ ← → buttons.
- **Restart**: click the "Restart" button, or press any key after Game Over.

## How it works

Everything lives in `index.html`: inline CSS for styling and vanilla JS driving a `<canvas>` game loop (`setTimeout`-based tick). The snake grows when it eats food (red square) and the game ends on hitting a wall or itself.

No install, no npm, no framework — just open the file.
