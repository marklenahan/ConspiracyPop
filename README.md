# Conspiracy Hunter

A single-page HTML/JS click-dodge game with a conspiracy theory theme. Suspicious objects pop up around the screen — click them before they vanish, but watch out for the bomb.

Open [index.html](index.html) directly in a browser to play. No build step, no dependencies.

## How to play

- Click "Start Game," wait for the 3-2-1 countdown, then objects start appearing around the screen.
- Click (or tap) an object before it disappears to score **+1**.
- Miss one (it goes 1 second unclicked) and it explodes for **-1**.
- One in ten objects is a **bomb**:
  - Click it and lose **-5** points.
  - Leave it alone and it fizzles out harmlessly after 2 seconds — no penalty.
- You have **60 seconds** on the clock. When time runs out, you'll see your final score and the all-time high score (saved in the browser's `localStorage`), with a "Play Again" button to restart.

## Difficulty pacing

Objects spawn slowly at first (1 every 2 seconds) and ramp up gradually to a peak rate of 2 per second, reached near the end of the 60-second round. Objects are placed so they never overlap each other.

## Object set

Bomb aside, objects are drawn from a themed pool of icons:

Duck, black hat, white hat, binoculars, test tube, UFO, grey alien, target, dollar sign, red letter Q, pyramid (with Eye of Providence), magnifying glass, ball of red wool, airplane, syringe, moon, royal crown.

## Sound

Pop and boom sound effects are synthesized live with the Web Audio API (no audio files) — a quick pitch-drop blip for a successful click, and a low sweep + noise burst when the bomb goes off.

## Responsive layout

- Desktop: the score/timer/high-score panel sits in a column on the right.
- Narrow viewports (≤700px wide, e.g. phones): the panel collapses into a compact bar across the top, and the play area fills the rest of the screen.

## Deploying

This is a static site — no server or build process required. It can be hosted for free on [Render](https://render.com) as a **Static Site** (not a Web Service, which would be subject to cold starts on the free tier):

1. Push this repo to GitHub (already done for this repo).
2. On Render: New → Static Site → connect this repo.
3. Leave the build command blank.
4. Set the publish directory to `.`.
5. Deploy.
