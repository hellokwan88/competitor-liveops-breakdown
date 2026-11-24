# Competitor Live Ops Breakdown

A GitHub Copilot agent skill for analyzing and documenting competitor live ops events in games.

## What It Does

When you share screenshots, documents, or references of a competitor's live ops event, this skill guides Copilot through a structured teardown:

- **Classifies** the event type (battle pass, gacha banner, seasonal event, etc.)
- **Analyzes** 8 dimensions: overview, progression, rewards, monetization, economy, content reuse, retention, and strategic read
- **Reverse-engineers** a PRD and design doc (deep dive mode)
- **Stores** findings in a consistent, searchable format

Two tiers available:
- **Quick capture** — 1 paragraph per dimension, fast competitive intel
- **Deep dive** — full analysis with reverse-engineered PRD and design doc

## Installation

### Option 1: GitHub CLI

```bash
gh skill install hellokwan88/competitor-liveops-breakdown competitor-liveops-breakdown
```

### Option 2: Manual

1. Download the `.github/skills/competitor-liveops-breakdown/` folder
2. Place it in one of these locations:
   - **Project skill** (one repo): `.github/skills/` in your repository
   - **Personal skill** (all repos): `~/.copilot/skills/` in your home directory

## Usage

In GitHub Copilot (VS Code, CLI, or coding agent), provide:

1. Screenshots or documents of the competitor event
2. A one-line briefing: game name, event name, approximate dates
3. Tier: "quick capture" or "deep dive"

Example prompt:
> Here are screenshots of Genshin Impact's Lantern Rite 2025 event. Quick capture.

## Event Categories

| Category | Description |
|----------|-------------|
| `battle-pass` | Seasonal/event pass with free + premium track |
| `challenge` | Time-limited competitive mode |
| `seasonal-event` | Themed content drop tied to a season or holiday |
| `limited-time-mode` | Temporary game mode with modified rules |
| `collaboration` | Crossover/IP collab events |
| `login-campaign` | Daily login reward sequences |
| `gacha-banner` | Limited-time character/item pools |
| `guild-event` | Clan/guild-specific competitive or cooperative events |

## Compatibility

This skill follows the open [agentskills.io](https://agentskills.io) standard and works with:
- GitHub Copilot in VS Code (agent mode)
- GitHub Copilot CLI
- GitHub Copilot coding agent
- Claude Code

## License

MIT License — see [LICENSE](LICENSE) for details.
