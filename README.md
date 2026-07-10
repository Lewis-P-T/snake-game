# Snake Game

A minimal browser Snake game — one HTML file, no dependencies, no build step.

## Play

Open `index.html` in any browser (double-click it, or serve the folder with any static server).

You (green) race a purple AI snake to eat apples. Highest apple count wins — there's no end, just an ongoing contest.

## Controls

- **Desktop**: arrow keys to move.
- **Mobile/touch**: tap the on-screen ↑ ↓ ← → buttons.

## Rules

- Eat the red apple to grow and score. Score for both snakes shows above the board.
- If **your head** hits the other snake (or a wall, or yourself), **you die**.
- If the **AI's head** hits your snake (or a wall, or itself), **it dies**.
- Head-on collision kills both.
- A dead snake **respawns after 5 seconds** at a random spot at least 3 squares from the survivor. Death is never game-over — you just sit out the countdown, then rejoin.

## How it works

Everything lives in `index.html`: inline CSS and vanilla JS driving a `<canvas>` game loop (`setTimeout`-based tick). The AI is a one-step greedy heuristic that steers toward the apple while dodging walls and both snakes.

No install, no npm, no framework — just open the file.
