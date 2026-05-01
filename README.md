# Subnetting Trainer

An interactive, gamified learning experience for IPv4 subnetting. Self-contained in a single HTML file — no install, no server, no dependencies. Just open it in a browser and learn.

## Quick start

1. Download `subnetting-trainer.html`
2. Double-click to open in any modern browser (Chrome, Edge, Firefox, Safari)
3. The onboarding tour starts automatically. Click through to begin Mission 1.

That's it. Progress is held in memory for the session — refreshing the page resets state.

## What it covers

Foundational and intermediate IPv4 subnetting:

- Binary ↔ decimal conversion
- IPv4 classes (A/B/C/D/E), private ranges, loopback, APIPA
- CIDR notation and subnet masks
- Host counts and subnet math (`2^h − 2`, borrowed-bit logic)
- Network ID, broadcast address, and host-range calculation via the block-size shortcut
- VLSM (Variable Length Subnet Masking) and address-space planning

## Structure

The trainer has 10 areas accessed via tabs across the top.

### Six missions (M1 through M6)

Each mission follows a three-stage review loop visible at the top of the screen:

1. **📖 Study** — concise study guide with examples
2. **🧪 Lesson** — hands-on interactive practice (un-timed, no scoring, designed for discovery)
3. **🎯 Mission** — scored challenge using the mechanic that fits the topic

The mission stage stays locked until the lesson is cleared. Missions unlock sequentially.

| Mission | Topic | Lesson mechanic | Mission format |
|---------|-------|-----------------|----------------|
| M1 | Binary & octets | Bit Flipper (toggle 8 bits to match a target decimal) | Multiple choice, 5 Qs, 60s |
| M2 | IPv4 classes | Class Detector (slide a 0–255 marker across class zones) | Multiple choice, 6 Qs, 60s |
| M3 | CIDR ↔ mask | Mask Builder (toggle 32 bits, see CIDR + mask live) | Drag-and-drop matching, 7 pairs |
| M4 | Host count | Host Calculator (slider shows host bits and `2^h − 2`) | Fill-in-the-blank, 8 Qs |
| M5 | Network ID | Boundary Picker (mask, block size, all valid boundaries shown) | Fill-in-the-blank, 9 Qs |
| M6 | VLSM | VLSM Allocator (assign smallest valid prefix to each subnet) | Multiple choice, 10 Qs, 80s |

Question counts and timer pressure scale up with mission difficulty. Mission questions are drawn at random from larger pools (15–60 questions per mission), so replays produce different sets.

### 🧪 Sandbox

Always-available IPv4 calculator. Enter any IP/prefix combination to see network ID, broadcast, subnet mask, first/last usable host, host count, address class, and a color-coded binary breakdown showing which bits are network (blue) versus host (beige).

### 🗺️ Topology Builder

A visual network design canvas. Place routers, switches, and host groups, then connect them with links. The trainer auto-runs VLSM on every change and assigns subnets to each link based on actual host requirements. Includes preset scenarios (Small Office, Campus) and live validation flags for orphaned devices, unallocated links, and address-space exhaustion.

### ⚡ Challenge Mode

Unlocks after Mission 3. Three difficulty tiers with progressively tighter constraints, drawn only from the hardest question pool:

| Tier | Time/Q | Questions | Pass | Multiplier | Hints |
|------|--------|-----------|------|------------|-------|
| 🥉 Veteran | 8s | 10 mixed | 90% | 2× | On |
| 🥈 Expert | 6s | 10 mixed | 90% | 3× | Off |
| 🥇 Nightmare | 4s | 12 mixed | 100% | 5× | Off |

Mixed format means MC and fill-in questions are interleaved randomly within each run.

### 🐉 Final Boss

Unlocks after all six missions clear. The "Subnet Sphinx" has three HP bars (Multiple Choice, Fill-in, Drag-Match), each requiring 3 correct answers to deplete. **A wrong answer in any category resets that bar to zero**, so brute-forcing won't work. Defeat all three categories to claim the trophy.

### 🏅 Achievements

15 badges across four categories: Progression, Streaks, Speed & Precision, and Exploration. Each badge awards bonus points (5–100) and shows in the HUD as it unlocks. Notable ones:

- **Speedrunner** — finish a timed mission with 30+ seconds left
- **No Mistakes** — defeat the boss without resetting any HP bar (requires 9 consecutive correct answers across categories)
- **Triple Threat** — clear all three challenge tiers
- **Subnet Savant** — answer 20 questions in a row correctly

## Scoring

Points accumulate across all activities:

- Mission MC correct: 15 pts
- Mission fill correct: 20 pts
- Mission match correct: 15 pts each + 25 mission bonus
- Mission completion bonus: 25 pts (plus seconds remaining on timed missions)
- Lesson completion: 10 pts
- Challenge correct: 15–20 pts × tier multiplier
- Challenge first-clear bonus: 50 pts × tier multiplier
- Boss correct: 30 pts; defeat: 100 pts
- Achievement unlocks: 5–100 pts each

## Onboarding

A 5-step spotlight tour runs automatically on first load, walking through the title, HUD, tabs, mission flow, and Help button. The **? Help** button in the top-right replays the tour anytime.

## Browser & device requirements

- Modern desktop browser (Chrome 90+, Edge 90+, Firefox 88+, Safari 14+)
- JavaScript enabled
- Drag-and-drop interactions (matching, topology) require a mouse or trackpad — touch-only mobile devices may have reduced functionality on those specific stages
- Topology builder works best on screens 900px wide and up; below that the layout collapses to a single column

## Technical notes

- 100% client-side, no network calls, no telemetry, no cookies
- ~60KB single HTML file with embedded CSS and JS
- All randomization is per-session; reload to draw fresh questions
- Mission MC questions shuffle option order in addition to drawing from pools, so the correct answer never sits in a predictable slot

## Suggested usage

**Self-paced learning (≈ 60–90 min):** Work through M1 → M6 in order, taking the lesson seriously. Use the sandbox between missions to test edge cases. Tackle Challenge after M3 unlocks. Save the boss for the end.

**Refresher (≈ 20 min):** Skip directly to the topology builder — load a preset scenario, modify host counts, and observe how subnet allocations shift. Then run Veteran tier in Challenge Mode for a quick pulse check.

**Team training:** Have learners aim for the **Mission Master** (clear all 6) and **Sphinx Slayer** badges as the floor, with **Triple Threat** (all three challenge tiers) as the stretch goal. The boss's **No Mistakes** badge is the master-level signal.

## Files

- `subnetting-trainer.html` — the trainer (open this)
- `README.md` — this file
- `teams-post.md` — announcement post for Microsoft Teams

## License

Use freely for internal training. Not for commercial redistribution.
