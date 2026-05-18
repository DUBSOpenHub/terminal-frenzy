# Security Policy

## Supported Versions

| Version | Supported |
|---------|-----------|
| 1.0.x   | ✅ Yes |

---

## Reporting a Vulnerability

**Do not open a public GitHub issue for security vulnerabilities.**

Please report vulnerabilities via [GitHub Security Advisories](https://github.com/DUBSOpenHub/copilot-cli-terminal-frenzy/security/advisories/new) or email the repository owner directly.

Include:
- A description of the vulnerability and its potential impact
- Steps to reproduce or a proof-of-concept
- Your preferred contact method for follow-up

**Expected response times:**

| Stage | Target |
|-------|--------|
| Acknowledgement | ≤ 48 hours |
| Initial triage | ≤ 5 business days |
| Fix / mitigation | ≤ 30 days |

---

## Security Posture

This is a **client-side only** HTML game with no server component and no authentication.

### What it does
- Uses embedded GitHub mascot artwork
- Stores local gameplay data in the browser's `localStorage`
- Syncs top-10 leaderboard scores to a public CORS-enabled npoint JSON endpoint
- Synthesizes audio using the Web Audio API
- Runs entirely in your browser tab

### What it does NOT do
- ❌ No bundled server or backend
- ❌ No cookies, no tracking, no analytics
- ❌ No user accounts or authentication
- ❌ No analytics or behavioral tracking
- ❌ No external JavaScript dependencies
- ❌ No service workers or background processes

### Content Security

- All game logic is inline in a single HTML file
- No external scripts are loaded
- Mascot artwork is embedded as data URLs in `index.html`, so character art does not require remote image requests
- Player handles and scores may be stored locally and submitted to the configured public leaderboard endpoint

### localStorage Usage

The game stores local gameplay data in `localStorage`:
- `copilot-cli-terminal-frenzy-v1` — high score and achievement data (JSON)
- `copilot-cli-terminal-frenzy-player` — the locally remembered player handle
- `copilot-cli-terminal-frenzy-arcade` — local leaderboard cache

Legacy `terminal-frenzy-*` keys are read when present so existing local scores and player handles can migrate naturally after the rename.

Local data is cleared when browser data is cleared.
Local leaderboard data is capped to each player's best score and the top 10 overall. The same handle, score, and date fields are submitted to the shared npoint leaderboard document.

### Global Leaderboard Data

The leaderboard endpoint is intentionally public so the GitHub Pages game can read and write scores without accounts. Do not submit sensitive information as a player handle. The game sanitizes handles to letters, numbers, and hyphens before writing scores.

---

## Known Limitations

### No Content Security Policy header
Since the game is a local HTML file (or hosted on GitHub Pages), CSP headers are not set. If hosting on a custom domain, consider adding appropriate CSP headers.

### Mascot image loading
Mascot artwork is embedded as data URLs in `index.html`, so gameplay does not depend on a remote image host for character art.
