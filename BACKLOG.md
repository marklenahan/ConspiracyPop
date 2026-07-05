# Backlog

Ideas for future enhancements. Nothing here is scheduled or implemented — just notes to revisit later.

## 1. Falling icons

Icons should slowly fall down the screen instead of staying static, and should only spawn in the top half of the play area (giving them room to fall before they'd reach the bottom).

## 2. Background rain animation

A faint, decorative background animation: small, low-opacity random letters and symbols slowly raining down the screen, Matrix-style. Purely cosmetic — no effect on gameplay, scoring, or hit detection.

## 3. Difficulty selection (Easy / Medium / Hard)

Add a difficulty picker next to the "Start Game" button, changing object lifetime and spawn-rate ramp:

- **Easy** — objects stay clickable for 2 seconds; spawn-rate ramp progresses 50% slower than current.
- **Medium** — objects stay clickable for 1.5 seconds; spawn-rate ramp as-is (current default).
- **Hard** — objects stay clickable for 1 second; spawn-rate ramp progresses 30% faster than current.

## 4. Local leaderboard (top 3 runs)

Instead of tracking a single high score, keep the top 3 scores from past runs. Still uses `localStorage`, no backend needed. Show all three (not just the top one) on the end screen.
