# Backlog

Ideas for future enhancements. Nothing here is scheduled or implemented — just notes to revisit later.

## 1. Some additional text labels — DONE
 1.1 On the launch screen, show below the instructions, in smaller font: "v1.0 html/js game by Claude Code and Mark Lenahan (LinkedIn, GitHub)" - with links to https://www.linkedin.com/in/marklen/ and https://github.com/marklenahan/ConspiracyPop.
Also add this text as a comment to top of the html, but show full URLs in subsequent comment lines.
 1.2. When a suspicious object (any icon, but not a bomb) times out, resulting in the loss of the chain combo, briefly display text "Chain broken!" below the skull that fades in the same way.
For each subsequent change in this backlog, increase the version number by 0.1, e.g change 2 gives v1.1, change 3 gives v1.2, and so on.

## 2. Some additional subtle sounds — DONE
Add these sounds at half the volume of the pop / click sound
 2.1. A very subtle appearance sound for every icon that appears, including same sound for the bomb
 2.2. A subtle, sad sound when an icon, other than bomb, times out without being clicked. (when the skull is displayed).

## 3. Falling icons — DONE

Icons should slowly fall down the screen instead of staying static, and should only spawn in the top half of the play area (giving them room to fall before they'd reach the bottom).

## 4. Background rain animation — DONE

A faint, decorative background animation: small, low-opacity random letters and symbols slowly raining down the screen, Matrix-style. Purely cosmetic — no effect on gameplay, scoring, or hit detection.

## 5. Difficulty selection (Easy / Medium / Hard) — DONE

Add a difficulty picker next to the "Start Game" button, changing object lifetime and spawn-rate ramp:

- **Easy** — objects stay clickable for 2 seconds; spawn-rate ramp progresses 50% slower than current.
- **Medium** — objects stay clickable for 1.5 seconds; spawn-rate ramp as-is (current default).
- **Hard** — objects stay clickable for 1 second; spawn-rate ramp progresses 30% faster than current.

## 6. Local leaderboard (top 3 runs) — DONE

Instead of tracking a single high score, keep the top 3 scores from past runs. Still uses `localStorage`, no backend needed. Show all three (not just the top one) on the end screen.
