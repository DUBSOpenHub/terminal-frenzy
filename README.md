# 🎮 Copilot CLI Terminal Frenzy

[![Play Now](https://img.shields.io/badge/Play%20Now-GitHub%20Pages-7c3aed?style=for-the-badge&logo=github)](https://dubsopenhub.github.io/copilot-cli-terminal-frenzy/)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Built with Copilot CLI](https://img.shields.io/badge/Built%20with-Copilot%20CLI-06b6d4.svg)](https://docs.github.com/en/copilot/github-copilot-in-the-cli)

**Copilot CLI Terminal Frenzy is a gamified awareness tool for the GitHub Copilot CLI.** How fast can you ship in the frenzy? Clear 12 terminal requests from Copilot, Mona, and Ducky in 60 seconds, ship through urgent command prompts, and keep the pipeline green — learning real CLI commands while you play.

It teaches the vocabulary of Copilot CLI (`gh pr review`, suggestions, approvals) while being genuinely fun and competitive.

### 🎬 Game Preview

[![Copilot CLI Terminal Frenzy gameplay preview](https://raw.githubusercontent.com/DUBSOpenHub/copilot-cli-terminal-frenzy/main/preview.gif?v=20260508-0610)](https://raw.githubusercontent.com/DUBSOpenHub/copilot-cli-terminal-frenzy/main/preview.gif?v=20260508-0610)

---

## ▶ Play Now

### 🌐 Browser (instant)

**[Play on GitHub Pages →](https://dubsopenhub.github.io/copilot-cli-terminal-frenzy/)**

[Open the preview GIF directly →](https://raw.githubusercontent.com/DUBSOpenHub/copilot-cli-terminal-frenzy/main/preview.gif?v=20260508-0610)

### 💻 From your terminal

```bash
# Clone and open
git clone https://github.com/DUBSOpenHub/copilot-cli-terminal-frenzy.git
open copilot-cli-terminal-frenzy/index.html
```

Or just download and double-click `index.html` — it's a single file with zero dependencies.

---

## 🎮 How to Play

| Step | What to do |
|------|-----------|
| **1** | Press the **key shown** on each mascot request card, or tap the card on mobile |
| **2** | Type the **Copilot CLI command** when urgent requests appear, or tap the urgent command card on mobile |

That's it: **12 terminals, 60 seconds**. How many can you clear?

### Scoring

- ✅ **Clear a request** → points × your pipeline multiplier
- ⭐ **Power-up cards** → double points, freeze timers, bonus clears, or key highlights
- 🔥 **Urgent requests** → type the shown Copilot CLI command for big bonuses
- ❌ **Wrong key** → lose points and break your combo
- 👑 **Final request** → Mona appears in the last 10 seconds. Type the full Copilot CLI command.
- 🏆 **MVP teammate** → the end screen highlights the character you cleared the most requests for.
- 🕹️ **Global Top 10** → the leaderboard keeps each player's best score only and shows the top 10.

### Ranks

| Score | Rank |
|-------|------|
| 0–399 | Terminal Rookie |
| 400–1199 | Queue Wrangler |
| 1200–2399 | CLI Speedrunner |
| 2400–3999 | Merge Wizard |
| 4000–6499 | Copilot CLI Frenzy Master |
| 6500+ | Copilot Singularity |

---

## 🐙 The Characters

GitHub's mascot characters — **Mona**, **Copilot**, and **Ducky** — drive every card, urgent request, and animated title line. In-game cards use a shuffled round-robin rotation so one character does not dominate a round, and the end screen shows your MVP teammate with their requests-cleared count.

---

## 🛠️ Technical Details

- **Single HTML file** — no build step, no dependencies, no server
- **~2,900 lines** of HTML, CSS, and JavaScript
- **Web Audio API** — all sound effects synthesized in real-time
- **Canvas** — Matrix rain background and particle effects
- **GitHub-inspired typography** — Mona Sans styling with a clean Copilot CLI Terminal Frenzy title
- **GitHub mascot artwork** — embedded directly in `index.html`
- **localStorage** — high score persistence and offline leaderboard cache across sessions
- **Global Top 10** — shared browser-safe npoint JSON endpoint with local fallback if sync is unavailable
- **Responsive controls** — keyboard on desktop, tap controls on mobile
- **Works offline** — mascot artwork ships inside the HTML file

### Leaderboard backend

The game trims leaderboard data to the best score per GitHub handle and keeps only the top 10. `LEADERBOARD_API_URL` in `index.html` points at the shared npoint JSON document used by the live GitHub Pages game.

On load, the game fetches the shared scores with a cache buster. On game over, it merges the new score with the current shared list, keeps the best score for each handle, writes the top 10 back to the endpoint, and caches the result locally. If global sync fails, the UI says so and shows the local browser cache instead of silently pretending the leaderboard is live.

---

## 📁 Repository Structure

```
copilot-cli-terminal-frenzy/
├── index.html          # The entire game (single file)
├── README.md           # This file
├── AGENTS.md           # AI agent architecture
├── SECURITY.md         # Security policy
├── LICENSE             # MIT License
└── .github/
    └── copilot-instructions.md
```

---

## 🤝 Contributing

This is a fun project! Ideas welcome:
- New mascot request phrases
- Visual effects and polish
- New urgent request commands
- Accessibility improvements

---

## 📄 License

[MIT](LICENSE) — play it, fork it, remix it.

---

🐙 Created with 💜 by [@DUBSOpenHub](https://github.com/DUBSOpenHub) with the [GitHub Copilot CLI](https://docs.github.com/copilot/concepts/agents/about-copilot-cli).

Let's play! 🎮✨
