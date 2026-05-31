# Stellar Catcher

> A zero-install browser game — drag a black-hole ring to catch coloured particles, merge same-colour ones to score, and survive the chaos.

![version](https://img.shields.io/badge/version-1.8-blue)
![platform](https://img.shields.io/badge/platform-browser%20%7C%20mobile-lightgrey)
![license](https://img.shields.io/badge/license-MIT-green)

---

## Demo

Open the file directly in any browser — no build step, no dependencies, no install.

```bash
open "Stellar Catcher v1.8.html"
```

Works on desktop and mobile out of the box (touch + mouse both supported).

---

## Gameplay

| Action | Result |
|--------|--------|
| Drag the ring | Move the black hole and reposition its gravity field |
| Same-colour particles collide inside | Merge → score points + build combo |
| Different-colour particles collide inside | Lose points + screen shake |
| Wave target reached | **Fusion Moment** — freeze, all particles turn one colour, 8–12 bonus particles rush in, chain merges begin |

---

## Game Modes

### Challenge Mode
- **30 levels**, each with a unique task type
- Task types: reach a score / eat N balls of a specific colour / reach a combo / complete N merges
- Difficulty scales linearly: 3 colours at slow speed → 6 colours at high speed
- Completing levels unlocks skins and achievements

### Endless Mode
- **Roguelike wave** structure with no level cap
- After each wave, choose 1 of 3 upgrade cards (10 upgrades across 4 rarities)
- **Stability** acts as HP — drops on bad collisions; hits zero and the run ends (one revive available)
- Three difficulty tiers with score multipliers: Easy ×1.0 / Medium ×1.5 / Hard ×2.0
- Scores sync in real time to a **global leaderboard** (Supabase)

---

## Visual Themes

Cycle through three full themes from the main menu. Each theme has its own background renderer, particle shapes, and UI style. Preference is saved locally.

| Theme | Style | Special Mechanic |
|-------|-------|-----------------|
| 🌌 Space | Nebula + planet particles + black-hole ring | — |
| 🏜️ Western | Cartoon desert road + hand-drawn UI | — |
| 🧬 Cell | Deep-green bio background + organic membrane ring | Bacteriophages invade after 3 000 pts; Fusion Moment clears all phages |

---

## Power-ups & Viruses

**Power-ups** — spawn randomly, activate on contact with the ring

| Icon | Name | Effect |
|------|------|--------|
| 🛡 | Shield | Only absorbs the dominant colour; deflects all others |
| 🧲 | Magnet | Widens gravity field; prioritises dominant colour |
| ×2 | Double Score | All points ×2 |
| 🐢 | Slow | All particle speed −50% |

**Viruses** — fly in randomly, trigger on ring contact

| Effect | Description |
|--------|-------------|
| Reverse Absorb | Can only absorb non-dominant colour particles |
| Range Overload | Gravity field expands uncontrollably |
| Half Score | All points ×0.5 |
| Speed Surge | All particle speed ×2 |

---

## Roguelike Upgrades

| Rarity | Example Upgrades |
|--------|-----------------|
| Common | Score boost +18% / Shield duration +2.5 s |
| Uncommon | +4 pts per combo level / Virus resistance +25% |
| Rare | Merge score ×1.5 → ×2 / Auto-shield at wave start |
| Epic | 8-second double-score frenzy at the start of every wave |

---

## Achievements & Skins

- **20 achievements** spanning combo milestones, merge counts, score thresholds, and full-clear of all 30 levels
- **8 skins** unlocked by reaching specific levels or completing achievements

---

## Tech Stack

```
Single-file HTML + Canvas 2D
├── Rendering    Vanilla Canvas API — no framework
├── Audio        Web Audio API — procedural BGM + SFX
├── Storage      localStorage (progress & settings)
├── Leaderboard  Supabase REST API
└── Compat       ES5 polyfills; touch & mouse dual-input
```

---

## Repository Structure

```
Stellar Catcher v1.8.html   — full game (all code in one file)
Stellar Catcher 项目文档.md  — design document (Why / What / Roadmap)
README.md                    — this file
```

---

## Local Development

No build process required. Edit the HTML file directly and preview live:

1. Install the [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) extension in VS Code.
2. Right-click the HTML file → **Open with Live Server**.

---

## License

[MIT](LICENSE)
