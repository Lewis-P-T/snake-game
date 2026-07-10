# Snake Game

A minimal browser Snake game — one HTML file, no dependencies, no build step.

## Play

Open `index.html` in any browser (double-click it, or serve the folder with any static server).

You (green) race a purple AI snake to **10 bugs**. First to 10 wins.

## Controls

- **Start game**: click the button on the start screen to begin.
- **Move**: arrow keys (keyboard only).
- **Play again**: button on the win screen resets the match.
- **Difficulty**: Easy / Normal / Hard below the board sets how *randomly* the AI plays — on Easy every 2nd AI move is random (dumbest), Normal every 4th, Hard every 8th (sharpest). The setting carries across matches.
- **Bugs / Rocks sliders**: choose how many bugs (1–5) and rocks (5–10) spawn. Adjust them on the start screen to preview live; changes apply from the next match.

## Rules

- The board **wraps**: go off one edge and you come back on the opposite side (snakes and bugs both).
- Red bugs roam the board, each move stepping one square in a random direction (half your snake's speed). They never move into rocks, snakes, or each other. Catch one with your head to grow and score, and a new one appears.
- **Health = size.** A fatal hit — a rock, yourself, or the other snake — costs you **one segment** instead of ending the game. A snake can't shrink below size 1; if a size-1 snake takes a fatal hit, *then* it dies and respawns after **3 seconds**.
- Running into the other snake damages **both** snakes by one.
- 🍄 **Mushroom** (one at a time): eat it for a **50% speed boost + invincibility for 10 seconds** — while boosted you take no damage and phase through rocks and snakes. A new mushroom appears 10s after one is eaten. The AI grabs the mushroom when it's closer than the nearest bug.
- First snake to **10 bugs wins** — the match then ends with a win/lose screen.

## How it works

Everything lives in `index.html`: inline CSS and vanilla JS driving a `<canvas>` game loop (`setTimeout`-based tick) with per-entity speed accumulators. The AI is a one-step greedy heuristic that steers toward the nearest bug or mushroom while dodging rocks and snakes, with a difficulty-tuned chance of a random move. Bugs, rocks, and the mushroom are drawn directly on the canvas.

No install, no npm, no framework — just open the file.
