# Ganchitecture × Lisbon — STATE

_Last updated: 2026-05-15 (full extended kickoff transcript captured)_

## Status

**Phase:** Concept locked. Team assembled. Hardware on-hand confirmed. Dates set. Repo standing up.
**T-22 days to June 6, 2026 opening. T-18 days to June 2 install.**

## Dates (locked)

- **June 1** — Pablo arrives Lisbon
- **June 2** — Francisco (VTV) + Samer arrive; install begins
- **June 6** — Opening
- Build window from kickoff = ~3 weeks remote + 4 days on-site

## Decisions (locked)

### Concept
- 6× VTV LED ticker panels (Paris Photo SOLIENNE precedent) = the monolith
- Countdown clock from ~7B years (sun expiration) is the narrative anchor
- Visitor "offers" their device (laptop preferred, phone accepted) → device gets *possessed* with audio/visual reaction
- BYO-terminal: laptop = intentional + vulnerable + fits Spirit canvas pattern. Phone accepted for inclusivity.

### Sound architecture
- **Frequency, not music** (Seth call): each device emits a planet-frequency, collective = a bigger hum (Tibetan-chant stacking, 440Hz + 480Hz = symphony). Pablo's band/instruments framing was illustrative only.
- **Decentralized per-device audio / centralized master + lights** (Samer): per-device frequency plays locally on the device, no sync needed — frequencies harmonize naturally. Lights + master audio run from one controller (already self-synced). Do NOT attempt per-device ↔ central sync — that path = latency / fail.

### Light architecture
- **18m total LED strip in 1m sticks = 18 addressable nodes.** Each connected visitor lights one node. 10 visitors = bright room. 2 visitors = intimate. Pixel-level addressable per stick.
- Ambient red when empty, blink rate modulates by visitor count.
- Lights driven by central controller — single source of truth for the room.

### Device pairing
- **NFC tap > QR** (Pablo + Samer agree): small VTV screen shows numbers, NFC reader behind it; tap → Spirit Protocol site.
- **Per-visitor unique hash** (Samer): on link visit, the server returns a unique number/hash. Drives that device's frequency + visible number on its own screen.
- **MAC-as-hash precedent** (Samer): Art Blocks–style generative output keyed off device identity. Implementation likely via the unique-hash-on-visit pattern; MAC over BLE is a fallback if needed.

### The deception
- The 0-9 digits on the LED ticker panels are a **fixed loop video**, not programmable. Visitors believe the obelisk is counting down.
- Visitor laptops show **real, agent-driven numbers** — "you are the 9, he's the 7." The obelisk is theatre; the agent is real.
- Frame: ryoji ikeda + teamLab Japan. "You are not controlling, you are being controlled."

### Build sequence
- **Non-agentic redundancy first, agentic layer on top** (Samer) — deterministic hash → frequency/lights baseline, then layer agentic conversation/reaction
- **Offline-first connectivity bias** (Samer) — router only, no internet dependency

### Coordination
- **Telegram group** = the working channel (Seth call)
- **The ganchitecture agent gets a seat in the group** — develops voice, learns from the team, gains opinions about the installation. Agent-as-co-author, not tool.
- **GitHub + Claude Code session** provisioned for Pablo so the agent has working infra
- **Samer hosts the site** + custom link for the piece (tailored, not generic encounter chat)

## What we can / can't control

- ✅ Screens (panel content beyond the digit video) — programmable
- ✅ Lighting — programmable (18-node addressable strip)
- ✅ Sound — programmable (per-device frequency + central master)
- ✅ The numbers on visitor laptops (real, agent-driven)
- ❌ The 0-9 digit video on the LED tickers — locked by panel hardware

## Hardware on-hand (confirmed in kickoff)

- 6× LED ticker panels — Chinese ticker, fixed 0-9 video loop, dual acrylic (frosted + translucent white)
- Aluminum back structures for panels
- Raspberry Pi 4 + 5
- Arduino + ESP32 — **Samer leans ESP32** for clean small footprint (lights are on/off, ESP can handle it)
- DMX controller (or MIDI — TBD)
- Small screens (5" / 7" / 6.9") — candidate NFC tap surfaces
- TouchDesigner license (Vladimir, paid; free tier fine if no video out)

## Threads (live, by owner)

### Pablo (artist, ganchitecture)
- [ ] **NFC + numbers screen surface** — build the small-screen-with-NFC-behind module
- [ ] **Cynthia / adjacent-room audio file** — get the constant minimal sound from the artist next door; harmonic alignment required (windows along top of dividing wall = sound bleeds)
- [ ] **Venue specs** — confirm address, exact dims (10m × 3-4m tall confirmed), power capacity, network presence, load-in/strike windows
- [ ] **Develop the ganchitecture agent's voice** — Pablo's seat as the artist co-authoring with the agent

### Fran + Vlad (VTV, hardware)
- [ ] **Mirror renders** to `~/Projects/spirit/ganchitecture/assets/renders/` (Fran shared link in kickoff)
- [ ] **DMX vs MIDI** decision for light control
- [ ] **Small-screen pick** for NFC surface — 5" / 7" / 6.9" available; choose one
- [ ] **TouchDesigner access** — confirm whether video out (paid) or free tier
- [ ] **LED panel schematics** for Samer (he needs them to spec the controller binding)

### Samer (Spongenuity / Spirit build)
- [ ] **Push spirit protocol live encounter** to a hosted endpoint Pablo can hit
- [ ] **Custom link** tailored to the piece — numbers + chat (not generic encounter UI)
- [ ] **Per-visitor unique-hash endpoint** — return a unique number on each visit
- [ ] **Device-ID spike** — MAC over BLE vs NFC-only retrieval; offline-only mode
- [ ] **Socket.io each-device-as-instrument prior-art** — Samer remembers a 2014 app; dig up for reference architecture
- [ ] **Back in London** (next week): test ESP32 / Arduino / RPi against the 18-node strip
- [ ] **Reuse vs fork** `solienne-live-canvas` encounter primitive — Samer's localhost update is likely the base

### Seth (producer)
- [ ] **Set up Telegram group** — add Pablo, Fran, Vlad, Samer, ganchitecture agent
- [ ] **Set up GitHub repo + Claude Code session for Pablo** (THIS — in flight)
- [ ] **Budget envelope** — give Fran/Pablo a number before they plan hours. "On the cheap" today, needs a real number.
- [ ] **Funding source** — Spirit treasury vs separate vehicle? Affects whether this rolls into Spirit Protocol comms or stays adjacent.
- [ ] **Pre-event tease cadence + first asset** — moody monolith tease early, no mechanic reveal until visitors enter the room. Who drafts? Which channel?
- [ ] **Agent register call** — conversational ("speak with your agent") vs aggressive monologue ("the world is ending, guys"). Floated in transcript, still open.

## Reference

- Kickoff call transcript: `transcripts/2026-05-15-kickoff.md`
- Hardware precedent: Paris Photo SOLIENNE installation (VTV panels)
- Spirit canvas / live encounter primitives: `~/Projects/spirit/canvas-kit/` + `~/Projects/solienne/live-canvas/`
- Adjacent artist (next-door room): unnamed; Cynthia = curatorial contact
- Reactive-density frame: ryoji ikeda installations + teamLab Japan app-driven environments

## Open questions for Seth

- Budget envelope?
- Spirit treasury or separate vehicle?
- First tease asset — what / who / when?
- Conversational agent or doom-monologue agent at the monolith?
- Repo destination: org (spirit-protocol vs brightseth vs new), visibility (public for onboarding ref / private for now), license, final repo name
