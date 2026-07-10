# Snake Game

A minimal browser Snake game — one HTML file, no dependencies, no build step.

## Play

Open `index.html` in any browser (double-click it, or serve the folder with any static server).

You (green) race a purple AI snake to **10 ladybugs**. First to 10 wins.

## Controls

- **Move**: arrow keys (keyboard only).
- **Play again**: button on the win screen resets the match.
- **AI speed**: pick Easy / Normal / Hard below the board — this sets how fast the AI snake moves (slower / same / twice your speed). The setting carries across matches.

## Rules

- Two **ladybugs** roam the board, wandering slowly one square at a time. Catch one with your head to grow and score, and a new one appears.
- **6 stones** are scattered randomly at the start of each match — hitting a stone kills you, so weave around them. The AI avoids them too.
- First snake to **10 ladybugs wins** — the match then ends with a win/lose screen.
- If **your head** hits the other snake, a stone, a wall, or yourself, **you die**.
- If the **AI's head** hits your snake, a stone, a wall, or itself, **it dies**.
- Head-on collision kills both.
- A dead snake **respawns after 5 seconds** at a random spot at least 3 squares from the survivor (and never on a stone) — death costs you time, not the match.

## How it works

Everything lives in `index.html`: inline CSS and vanilla JS driving a `<canvas>` game loop (`setTimeout`-based tick). The AI is a one-step greedy heuristic that steers toward the nearest ladybug while dodging walls, stones, and both snakes. Ladybugs and stones are drawn directly on the canvas.

No install, no npm, no framework — just open the file.
