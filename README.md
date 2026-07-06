# Conspiracy Hunter

A single-page HTML/JS click-dodge game with a conspiracy theory theme. Suspicious objects fall slowly down the screen — click them before they vanish, but watch out for the bomb.

Open [index.html](index.html) directly in a browser to play. No build step, no dependencies.

## How to play

- Pick a difficulty (see below), click "Start Game," wait for the 3-2-1 countdown, then objects start appearing and slowly falling down the screen.
- Click (or tap) an object before it disappears to score points.
- Miss one and it explodes for **-1**, breaking your combo and showing a fading skull icon with a "Chain broken!" message (if you had a streak going).
- One in ten objects is a **bomb** (shown on the start screen so you know what to avoid):
  - Click it and lose **-5** points, breaking your combo.
  - Leave it alone and it fizzles out harmlessly after 2 seconds — no penalty, and your combo is unaffected.
- You have **60 seconds** on the clock. When time runs out, you'll see your final score and a top-3 leaderboard (see below), with a "Play Again" button to restart.

## Difficulty

An Easy / Medium / Hard picker sits above the "Start Game" button and controls both how long an object stays clickable and how quickly the spawn rate ramps up over the round:

- **Easy** — 2 second clickable window; spawn-rate ramp 50% slower than default.
- **Medium** (default) — 1.5 second window; spawn-rate ramp at the default pace.
- **Hard** — 1 second window; spawn-rate ramp 30% faster than default.

Regardless of difficulty, spawning starts at 1 object every 2 seconds and ramps up to a peak of 2 per second. Objects are placed so they never overlap each other at spawn time.

## Combo multiplier

Chaining hits without a miss builds a streak. Every 3 consecutive hits bumps your multiplier up by one, capped at x5 — so points per click scale with accuracy, rewarding steady play over panic-clicking. The current multiplier is shown live in the "Combo" readout. Missing an object or clicking the bomb resets the streak back to x1.

## Falling icons

Objects spawn anywhere in the top 75% of the play area and drift slowly downward for as long as they're on screen. Fall speed is tuned so most objects stay comfortably in view, but some spawned deep in that zone may drift past the bottom edge before their timeout fires — that's expected, not a bug.

## Object set

Bomb aside, objects are drawn from a themed pool of icons:

Duck, black hat, white hat, binoculars, test tube, UFO, grey alien, target, dollar bill, red letter Q, pyramid (with Eye of Providence), magnifying glass, ball of red wool, airplane, syringe, moon, royal crown.

The start screen shows what the bomb icon actually looks like, right next to the warning about it.

## Sound

All sound effects are synthesized live with the Web Audio API (no audio files):

- A soft rising "shoop" blip plays whenever any object spawns (including bombs).
- A quick pitch-drop pop plays on a successful click.
- A subtle, sad descending tone plays when a non-bomb object times out unclicked.
- A low sweep + noise burst plays when the bomb goes off.

A mute button (top-right corner) is available on the start screen, during play, and on the end screen, and its state is remembered via `localStorage`.

## Visual feedback

- Missing an object shows a small skull icon that fades out over 1 second at that spot, in addition to the usual explode animation and `-1` floater. If you had an active combo, a "Chain broken!" message fades in alongside it.
- Clicking the bomb triggers a red screen flash and a bigger explosion animation.
- A faint, decorative "Matrix"-style rain of falling character columns runs in the background at all times. It's purely cosmetic (`pointer-events: none`) and never affects hit detection.

## Leaderboard

Your top 3 scores are kept in the browser's `localStorage` and shown in full on the end screen after each round. The in-game panel shows just your current best for a quick reference while playing.

## Responsive layout

- Desktop: the score/timer/high-score/combo panel sits in a column on the right.
- Narrow viewports (≤700px wide, e.g. phones): the panel collapses into a compact bar across the top, and the play area fills the rest of the screen.

## Deploying

This is a static site — no server or build process required. It can be hosted for free on [Render](https://render.com) as a **Static Site** (not a Web Service, which would be subject to cold starts on the free tier):

1. Push this repo to GitHub (already done for this repo).
2. On Render: New → Static Site → connect this repo.
3. Leave the build command blank.
4. Set the publish directory to `.`.
5. Deploy.
