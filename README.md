# Snake Game

A minimal browser Snake game — one HTML file, no dependencies, no build step.

**▶ Play it live: https://lewis-p-t.github.io/snake-game/**

## Play

Open the live link above, or open `index.html` in any browser (double-click it, or serve the folder with any static server).

Race a rival snake to catch bugs. Play **1P vs AI** (you green, AI purple) or **2P local** (P1 green, P2 purple). PC / keyboard only.

## Controls

- **Start game / Play again**: buttons on the start & win screens. Each match opens with a **3‑2‑1 countdown**.
- **Move**: P1 = arrow keys, P2 = WASD (2P mode).
- **Pause**: Space (or P).
- Wins and your best race time are **saved** between sessions (shown above the board).

## Settings (below the board)

- **Mode**: 1P vs AI or 2P local.
- **Difficulty** (AI only): sets how *randomly* the AI plays — Easy every 2nd move random (dumbest), Normal every 4th, Hard every 8th (sharpest, uses pathfinding otherwise).
- **Bugs (1–5)** and **Rocks (5–10)** sliders — live preview on the start screen.
- **Win at**: 5 / 10 / 20 bugs.
- **Board**: Small / Medium / Large.

## Rules

- The board **wraps**: leave one edge, return on the opposite side (snakes and bugs).
- Red bugs roam one square at a time in a random direction (half your speed), never onto rocks, snakes, or each other. Catch one with your head to grow + score.
- **Health = size.** A fatal hit — a rock, yourself, the rival snake, or the predator — costs **one segment** instead of ending the game. Running into the other snake damages **both**. A snake can't shrink below size 1; a size-1 snake that takes a fatal hit dies and respawns after **3 seconds**.
- **Power-ups** (one on the board at a time, respawns 10s after eaten):
  - 🍄 **Mushroom** — 50% speed + invincibility for 10s (take no damage, phase through obstacles).
  - ❄️ **Freeze** — freezes the rival snake for 3s.
  - ⚡ **Bolt** — instantly shrinks the rival by one segment.
  - The AI grabs a power-up when it's closer than the nearest bug.
- 🕷️ A slow **predator** patrols the board, chasing the nearest snake's head — touch it and you take damage.
- First snake to the win target wins.

## How it works

Everything lives in `index.html`: inline CSS and vanilla JS driving a `<canvas>` game loop (`setTimeout`-based tick) with per-entity speed accumulators. The AI uses BFS pathfinding on the wrap-around grid toward the nearest bug or power-up (with a difficulty-tuned chance of a random move). Simple WebAudio blips and a screen-shake/flash add game feel; stats persist via `localStorage`. Everything is drawn directly on the canvas.

No install, no npm, no framework — just open the file.
