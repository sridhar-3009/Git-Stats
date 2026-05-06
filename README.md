# AURA.SYS — GitHub Developer Intelligence

> Cyberpunk analytics dashboard that turns any GitHub profile into a real-time intelligence card.

![AURA.SYS](https://img.shields.io/badge/AURA.SYS-v2.0-00ffe0?style=for-the-badge&labelColor=00040e&color=00ffe0)
![GitHub Pages](https://img.shields.io/badge/GitHub_Pages-live-00ffe0?style=for-the-badge&labelColor=00040e)
![Vanilla JS](https://img.shields.io/badge/Vanilla_JS-no_framework-f5a623?style=for-the-badge&labelColor=00040e)

**[→ Live Demo](https://sridhar-3009.github.io/Git-Stats/)**

---

## Features

- **Aura Score** — composite rank (Bronze → Legend) based on stars, forks, followers, commits, repos
- **SVG Score Ring** — animated arc gauge with tier-colored glow
- **Language Breakdown** — doughnut chart + progress bars for top 5 languages
- **Contribution Heatmap** — 84-day activity grid with thermal color scale
- **Repository Insights** — top repos by stars/forks, recently updated
- **Activity Timeline** — last 10 public events with timestamps
- **Compare Mode** — load two profiles side by side
- **Export** — save card as PNG or PDF
- **Share** — Web Share API + Twitter/LinkedIn links
- **GitHub Token support** — add personal token for 5000 req/hr vs 60 req/hr unauthenticated
- **10-min cache** — localStorage cache to minimize API calls

## Design

Cyberpunk terminal aesthetic — hex grid background, scanlines, Space Mono monospace, neon cyan `#00ffe0` accent, corner-bracket panels, animated constellation particle field, hexagonal avatar with spinning conic ring, glitch text effects.

## Stack

| Tool | Purpose |
|---|---|
| Vanilla JS | Everything — no framework |
| Chart.js | Doughnut, bar, line charts |
| GSAP + ScrollTrigger | Entrance animations, scroll reveals |
| Lucide Icons | UI icons |
| html2canvas + jsPDF | Export to PNG / PDF |
| GitHub REST API v3 | All data |

## Usage

```
# Open locally
open index.html

# Or visit
https://sridhar-3009.github.io/Git-Stats/?user=torvalds
```

### URL parameters
| Param | Example | Description |
|---|---|---|
| `user` | `?user=torvalds` | Pre-load a profile |
| `compare` | `?compare=gaearon` | Pre-load compare target |

### Adding a GitHub token
Click **⚿ TOKEN** in the header → paste a classic personal access token (zero scopes needed for public data) → Save. Stored in browser localStorage only — never in code.

## Rate Limits

| Mode | Limit |
|---|---|
| No token | 60 req/hr per IP |
| With token | 5,000 req/hr |

Live rate counter shown in header after first API call.

## Aura Tiers

| Tier | Score |
|---|---|
| 🔴 Legend | 1150+ |
| 💎 Diamond | 850–1149 |
| ⚪ Platinum | 620–849 |
| 🟡 Gold | 400–619 |
| ⚫ Silver | 220–399 |
| 🟤 Bronze | 0–219 |

## Local Development

Single `index.html` file — no build step, no dependencies to install.

```bash
git clone https://github.com/sridhar-3009/Git-Stats.git
cd Git-Stats
open index.html
```

## License

MIT
