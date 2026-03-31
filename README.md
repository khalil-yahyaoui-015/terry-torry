# Terry Torry — Territory Conquest

A browser-based territory conquest game built as a single HTML file with vanilla JavaScript. No frameworks, no dependencies.

> **Note:** Developed in collaboration with Claude AI. I designed the game mechanics, iterated on the logic, and learned the codebase in depth.

🎮 **[Play it live](https://github.com/khalil-yahyaoui-015/terry-torry)** 

---

## Gameplay

Move your mouse to paint territory. Outmaneuver 3 AI enemies across a 2-minute match. Most territory controlled at the end wins.

- **Trail painting** — your movement leaves colored cells behind
- **AI enemies** — 3 opponents using random-walk with occasional targeting
- **Real-time scoreboard** — live territory % per faction

---

## Technical breakdown

Everything runs in a single `index.html` file (~680 lines).

| Concept | Implementation |
|---|---|
| Territory grid | `Uint8Array` — flat 2D array, 1 byte per cell (owner ID) |
| Rendering | HTML Canvas 2D API, `requestAnimationFrame` game loop |
| Player movement | Normalized vector toward mouse position |
| Enemy AI | Random walk + 1% chance/frame of random retargeting |
| Trail effect | FIFO queue of last 24 positions, opacity/width lerp |
| Particles | Simple particle system with velocity, friction, decay |

---

## Run locally

No build step needed — just open the file:

```bash
git clone https://github.com/khalil-yahyaoui-015/terry-torry
cd terry-torry
open index.html 
```

---

## Stack

`HTML` `CSS` `Vanilla JS` `Canvas API`
