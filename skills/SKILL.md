---
name: competitor-liveops-breakdown
description: Use when the user shares screenshots, documents, or references of a competitor's live ops event or feature to analyze, break down, and store as competitive intelligence.
---

# Competitor Live Ops Breakdown

When the user shares screenshots, documents, or references of a competitor's live ops event or feature, follow this workflow.

## Required Input

The user must provide:
1. **Screenshots, documents, or reference materials** of the event
2. **One-line briefing**: game name, event name, approximate dates
3. **Tier**: "quick capture" or "deep dive"

If the briefing or tier is missing, ask before starting.

## Step 1 — Classify the Event

Map to one of these fixed mechanic categories:
- **battle-pass** — seasonal/event pass with free + premium track
- **challenge** — time-limited competitive mode (tournaments, global challenges)
- **seasonal-event** — themed content drop tied to a season or holiday
- **limited-time-mode** — temporary game mode with modified rules
- **collaboration** — crossover/IP collab events
- **login-campaign** — daily login reward sequences
- **gacha-banner** — limited-time character/item pools
- **guild-event** — clan/guild-specific competitive or cooperative events

If no category fits, ask the user to pick the closest or propose a new one.

Check the index README for existing entries under this game/mechanic to assign the next sequential event number.

## Step 2 — Teardown (Both Tiers)

Analyze every screenshot, document, and reference provided. Organize findings into these 8 dimensions:

### 1. Event Overview
- One-paragraph summary: what it is, what players do
- Core loop of the event (what is the player doing repeatedly?)
- Duration and phase structure
- How it modifies or connects to the base game loop

### 2. Progression & Mechanics
- Progression system (linear track, branching, milestones, points/currency)
- Key mechanics unique to this event
- Difficulty curve and pacing observations
- Session design — typical play session length within the event
- Social/multiplayer mechanics (co-op, leaderboards, guilds)

### 3. Reward Structure
- Free vs. premium reward tracks (if applicable)
- Reward types (cosmetics, currency, characters, power items, exclusive/limited)
- Reward pacing — how frequently do players receive rewards?
- FOMO mechanics — what expires, what's exclusive, what returns?
- Milestone vs. continuous rewards

### 4. Monetization Design
- Direct purchase opportunities (bundles, packs, offers)
- Premium pass or tier pricing
- Currency sinks and conversion points
- Estimated spend depth (low spender / mid spender / whale path)
- Value perception tactics (anchoring, discounts, bonus items)

### 5. Economy Integration
- How event currencies and rewards connect to the permanent game economy
- New currencies introduced vs. existing currencies used
- Inflation risk — does the event inject too much of a permanent resource?
- Sink design — what pulls resources out during the event?
- Post-event economy impact — what persists after the event ends?

### 6. Content Reuse & Cost
- What is newly created for this event (art, modes, mechanics)?
- What is reused or reskinned from existing content?
- Estimated build cost relative to other events (light / medium / heavy)
- Asset requirements (UI, characters, environments, audio, localization)
- Template or framework reuse — does this follow a repeatable event structure?

### 7. Retention Mechanics
- Daily hooks — what brings players back each day during the event?
- Weekly hooks — longer-cycle engagement drivers
- Re-engagement triggers — notifications, reminders, social prompts
- Login incentives tied to the event
- Urgency mechanics — countdown timers, limited stock, escalating rewards

### 8. Strategic Read
- What problem does this event solve for the game? (retention, revenue, acquisition, reactivation, content gap fill)
- What is clever or novel about the design?
- What are the risks or weaknesses?
- Comparable implementations in other games

**For quick captures:** Write 1 paragraph per dimension. Keep it tight. Done.

**For deep dives:** Write thorough analysis per dimension with tables, numbers, and screenshot references where relevant. Then continue to Step 3.

## Step 3 — Reverse-Engineered PRD (Deep Dive Only)

Write this as if you are the competitor's product manager who shipped this event. This is the document they would have written to get the event approved. Use their voice, not yours.

Sections:
- **Objective** — what player behavior or business outcome is this event designed to drive?
- **Target player segment** — who is this for? (new players, lapsed, whales, mid-core, etc.)
- **Feature description** — the event in product terms: what it is, what players can do
- **Success metrics** — the KPIs they would have set (engagement rate, conversion, ARPU lift, retention delta, reactivation rate)
- **Go/no-go criteria** — what would make them pull or extend this event?
- **Risks accepted** — what trade-offs or known weaknesses did they ship with?
- **Dependencies** — what had to be true for this event to work (content pipeline, tech, partnerships)

## Step 4 — Reverse-Engineered Design Doc (Deep Dive Only)

Write this as if you are the competitor's game designer handing this to their engineering and art team. Technical, specific, buildable.

Sections:
- **Design goals & principles** — what the design optimizes for
- **Detailed mechanic specs** — rules, formulas, tables, numbers (use tables liberally)
- **Economy math** — currency generation rates, conversion ratios, expected player earnings per day/week
- **Content requirements** — art assets, audio, text/localization, UI screens needed
- **Technical considerations** — server events, client UI, data tracking, A/B test hooks
- **Edge cases & error states** — what happens when players miss days, hit caps, exploit, etc.
- **QA test scenarios** — key things to verify before launch

## Step 5 — Format & Store

### File Structure

One file per event with this structure:

```markdown
# [Game Name] — [Event Name]

**Mechanic:** [category]
**Dates:** [start — end]
**Analyzed:** [date]
**Depth:** [quick / deep]
**Duration:** [X days]

---

## Teardown

### 1. Event Overview
...
### 2. Progression & Mechanics
...
(all 8 dimensions)

---

## PRD (Reverse-Engineered)
(deep dive only)
...

---

## Design Doc (Reverse-Engineered)
(deep dive only)
...
```

### Save Location

Save the teardown file to your project's liveops library using this structure:

```
liveops-library/
├── README.md                          # Index of all analyzed events
├── <game>/
│   └── <mechanic>/
│       └── <###>-<event-name>/
│           ├── index.md               # The teardown document
│           └── 01-<description>.png   # Screenshots (if available)
```

Use kebab-case for all folder and file names. Event numbers are zero-padded to 3 digits (001, 002, etc.), sequential within each game/mechanic combination.

### Save Screenshots

Save all screenshots and images the user provided alongside the teardown file:

- **Naming:** `01-<brief-description>.png`, `02-<brief-description>.png`, etc. (sequential, with a short kebab-case description of what the screenshot shows, e.g. `01-event-banner.png`, `02-shop-offers.png`, `03-reward-track.png`)
- **Update screenshot references** in the teardown to use relative paths (e.g. `![Event banner](./01-event-banner.png)`).

### Update the Index

After saving, update (or create) the index at:

`liveops-library/README.md`

The index is a cross-reference table:

```markdown
# Live Ops Library — Index

| Game | Mechanic | # | Event Name | Date Analyzed | Duration | Key Insight | Depth |
|------|----------|---|------------|---------------|----------|-------------|-------|
```

"Key Insight" is one sentence — the single most notable thing about this event that makes it worth remembering.

## Formatting Notes

- Language: English only. Note Chinese source terms in parentheses where useful.
- Use tables for reward tracks, pricing tiers, progression milestones, and economy math.
- Reference specific screenshots by description ("as shown in the shop screenshot...").
- Bold key insights and callouts.
- Keep the tone analytical and neutral — competitive intelligence, not a review.
- When data is estimated or inferred (not directly visible), mark it as [estimated] or [inferred].
- This is pure competitor documentation — no reframing or comparison to your own products.
