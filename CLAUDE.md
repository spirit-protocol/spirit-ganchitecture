# Ganchitecture × Spirit — Lisbon NFC Installation

## What this session is

PM seat for the Lisbon installation produced under the Spirit Protocol umbrella in collaboration with artist **Pablo Radice (ganchitecture)** and **VTV (Francisco + Vladimir)**, built with **Samer / Spongenuity** for Spirit. Distinct from `~/Projects/spirit/protocol-site/` (TGE admin) and `~/Projects/spirit/spirit/` (core protocol session). **Do not pull TGE / token / launch threads into this room.**

**T-22 days to opening June 6, 2026. T-18 days to install June 2. Install crew arrives Lisbon June 1–2.**

## People

| Role | Name | Notes |
|---|---|---|
| Producer (Spirit) | Seth Goldstein | — |
| Artist | **Pablo Radice** (ganchitecture) | concept lead; has venue + ticket |
| Hardware | **Francisco (Fran)** — VTV | LED ticker panels (Paris Photo SOLIENNE precedent) |
| Hardware / systems | **Vladimir (Vlad)** — VTV | TouchDesigner license |
| Build / systems | **Samer** — Spongenuity for Spirit | hosts site + custom link; device-ID + light controller |

## The piece (locked)

Blacked-out basement bunker in an old factory in Portugal. ~10m × 3–4m tall. At the center: a monolith made of **6 VTV LED ticker panels** running a **fixed-loop 0–9 video** that *appears* to count down ~7 billion years to the sun's death. **The countdown is theatre.** The real numbers live on visitors' laptops — agent-driven, unique per device. *"You are not controlling, you are being controlled."* Framing: ryoji ikeda + teamLab Japan.

Visitors **offer their device** (laptop preferred, phone accepted). NFC tap on small VTV screen routes to a Samer-hosted Spirit site → server returns a unique hash → that device emits **one planet-frequency** locally (440Hz / 480Hz / Saturn / Mars / etc). Collective room = Tibetan-chant stacking, not synced music. Lights = 18m addressable LED strip in 1m sticks (18 nodes), one node per connected visitor, central controller (ESP32 lean).

## Locked decisions

### Concept
- 6× VTV LED ticker panels = the monolith. Numbers are a fixed 0–9 video loop (Chinese hardware). Theatre, not programmable.
- BYO-terminal: laptop preferred (intentional / vulnerable / fits Spirit canvas pattern); phone accepted for inclusivity.
- Real countdown lives on the visitor's screen, agent-driven. The monolith deceives; the agent is real.

### Sound — *frequency, not music*
- Each device emits a planet-frequency locally. Frequencies harmonize naturally; **no per-device ↔ central sync.** That path = latency / failure.
- Central master audio + lights run from one controller (already self-synced).

### Lights
- 18 addressable nodes (18m × 1m sticks), pixel-level per stick.
- One node lights per connected visitor. 10 visitors = bright. 2 = intimate.
- Ambient red when empty; blink rate modulates by visitor count.
- Single controller = single source of truth.

### Device pairing
- **NFC tap > QR.** Small VTV screen shows numbers, NFC reader behind it; tap routes to Spirit site.
- Server returns a unique hash on each visit → drives that device's frequency + the visible number on its own screen.
- MAC-as-hash (Art Blocks–style precedent); MAC over BLE is a fallback if needed.

### Coordination
- **Telegram group** = the working channel. Pablo, Fran, Vlad, Samer, Seth, + **the ganchitecture agent gets a seat.** Agent-as-co-author, not tool — develops voice, learns from the team, gains opinions about the install.
- **GitHub repo + Claude Code session** for Pablo so the agent has working infra (this dir).
- **Samer hosts the site** + custom link tailored to the piece (numbers + chat — NOT generic encounter UI).

### Build sequence
- Non-agentic redundancy first (deterministic hash → frequency + lights baseline), agentic layer on top.
- Offline-first connectivity bias (router only, no internet dependency).

## What we can / can't control

- ✅ Programmable: screens (panel content beyond digits), lighting, sound, the numbers on visitor laptops.
- ❌ Locked by hardware: the 0–9 digit video on the LED tickers.

## Hardware on-hand

6× LED ticker panels (dual acrylic — frosted + translucent white) · aluminum back structures · Raspberry Pi 4 + 5 · Arduino + ESP32 (Samer leans ESP32 — lights are on/off, clean small footprint) · DMX controller (or MIDI, TBD) · small screens 5" / 7" / 6.9" · TouchDesigner license (Vlad).

## Working surfaces

- **STATE.md** = live thread board, current open Qs for Seth, owner-tagged actions
- **transcripts/** = kickoff + future calls (Granola first if recorded; manual MD if not)
- **assets/renders/** = VTV render mirror
- **Wire protocol** = `~/.seth/inbox/<ts>-from-ganchitecture-...json` for material decisions / state changes (coordinator picks up every 5 min)

## Posture

- Spirit-curated but **TGE-isolated.** Don't pull token / launch / investor threads in.
- **Samer branch rule** applies to any spirit repo we touch: feature branch + PR, never direct to main. CC opens PRs; Samer/Seth merge.
- **Pablo = artist seat.** Defer to him on aesthetic / narrative. Seth + Samer adjudicate technical.
- **Pre-event tease:** moody monolith, no mechanic reveal until the room. Seth call on cadence + first asset.
- **Granola any future calls** + check before drafting comms to Pablo / Fran / Vlad / Samer. Their words anchor recs, not my model of them.
- **Wire material decisions** to `~/.seth/inbox/` with `from: "ganchitecture"` so the coordinator surfaces them.
- **Path discipline:** never write outside `~/Projects/spirit/ganchitecture/` without explicit Seth confirmation.

## What this session does NOT do

- TGE admin / token / launch / investor work
- SOLIENNE programming
- Direct push to main on any spirit repo
- Send external comms (drafts only; Seth or Pablo sends)
