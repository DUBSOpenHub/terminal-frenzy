# Copilot Instructions — Copilot CLI Terminal Frenzy

This repository contains a single-file HTML5 arcade game (`index.html`).

## Key facts
- The entire game is one self-contained HTML file (~2,900 lines)
- No build step, no dependencies, no server required
- All styling is inline CSS, all logic is inline JavaScript
- Sound effects are synthesized via Web Audio API (no audio files)
- Mascot artwork is embedded directly in `index.html`
- High scores persist via `localStorage`
- The leaderboard is capped to the global top 10, one best score per handle, and syncs through the configured npoint CORS endpoint

## When making changes
- Keep everything in `index.html` — do not split into separate files
- Test changes by opening the file directly in a browser (`open index.html`)
- Check for JS syntax errors with: `node -e "const fs=require('fs');const h=fs.readFileSync('index.html','utf8');const m=h.match(/<script>([\s\S]*?)<\/script>/);try{new Function(m[1]);console.log('OK')}catch(e){console.log('ERROR:',e.message)}"`
- The game features GitHub mascot characters — roster changes require updating the `MASCOTS` array AND the `TYPING_PHRASES_ALL` array
- All user-facing text should use "urgent request" (not "boss" or "manager")
- No `text-transform: uppercase` — use natural casing throughout
- Mascot appearances use a shuffled round-robin picker so Mona, Copilot, and Ducky stay balanced during play
- The end-game screen includes an MVP teammate card with character name and requests-cleared count

## Character roster
The `MASCOTS` array contains GitHub mascot character names and artwork URLs. The `TYPING_PHRASES_ALL` array contains mascot request phrases. Both must stay in sync.

## Hosted at
- GitHub Pages: `https://dubsopenhub.github.io/copilot-cli-terminal-frenzy/`
