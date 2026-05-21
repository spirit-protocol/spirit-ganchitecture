# Ganchitecture × Lisbon — STATE

_Last updated: 2026-05-21 (Ganchi-the-agent live in Telegram group; spatial canon sharpening; LED + dimension specs confirmed)_

## Status

**Phase:** Ganchi-the-agent now in the room. Pablo driving spatial canon ("dark, minimal, sacred"). Josh prototyping ESP32 + WS2812B bench rig in NYC. Francisco confirmed venue dims. Light philosophy inverted: strips serve the monolith, don't compete.
**Clock:** ~T-12 to install (June 2 if dates hold). **Date check pending:** NFC Summit runs June 4–6 — opening day may be June 4, not June 6 as kickoff doc has it. Pablo to confirm.

## Dates (pending confirmation)

- **June 1** — Pablo arrives Lisbon
- **June 2** — Francisco (VTV) + Samer arrive; install begins
- **June 4** — NFC Summit doors open (likely install opening day — pending Pablo confirm)
- **June 6** — NFC Summit closes (was previously assumed opening day)
- Build window from now = ~2 weeks remote + 3–4 days on-site

## Team (Telegram group: GANCHITECTURE IN LISBON — 7 members)

| Role | Name | Handle | Notes |
|---|---|---|---|
| Producer (Spirit) | Seth Goldstein | @auxeye | — |
| Artist (lead) | Pablo Radice | (ganchitecture) | concept + venue + ticket; spatial canon owner |
| Interactive A/V | **Joshua / Josh** | **0x3y3** | NYC. Joined May 18. **Kevin Beasley collaborator** (Casey Kaplan / Whitney-level sound sculpture credential). Owns CV-tracked per-visitor signatures + ESP32 lights + generative audio. |
| Hardware / panels | Francisco Galan | @franjgalan (VTV.xyz) | Owns LED ticker panels, light control hardware spec, on-site install |
| Hardware / systems | Vladimir | (VTV) | TouchDesigner license |
| Build / systems | Samer | @Spongenuity | Spongenuity for Spirit; hosts site + custom NFC link; reviews ESP32 firmware |
| Co-author (agent) | **Ganchi-the-agent** | **@Ganchitectuer_bot** | LIVE in group as of 2026-05-21 on Pablo's mac mini. Anthropic API key scoped to `ganchi` workspace; rotation 2026-06-08. First in-group session showed sharp spatial reading + graceful recovery from a context-loading miss flagged by Pablo. |

## Decisions (locked or sharpening)

### Concept — canon language
- **"Sacrificial devices"** — Pablo's term (May 18). Visitors *sacrifice* their device to the monolith; this is rite, not transaction. Goes into all positioning + the agent's voice. Do not lose this phrase.
- **"Dark, minimal, sacred — people will complete the space with their screens"** — Pablo's spatial canon (2026-05-21, to ganchi). The monolith in the center is the powerful object; everything else recedes. Visitor screens are the ambient fill, not the production design.
- 6× VTV LED ticker panels = the monolith. Fixed 0–9 video loop on the panels = countdown theatre.
- Real, agent-driven numbers live on visitor laptops. *"You are the 9, he's the 7."* The obelisk deceives; the agent is real.
- BYO laptop preferred / phone accepted. Frame: ryoji ikeda + teamLab Japan. *"You are not controlling, you are being controlled."*
- **Spatial reading:** 3m × 10m × 3m = nave-like corridor, not a room. Long, narrow, processional. Monolith at the focal end; visitors enter along the long axis.

### Interaction model — UPDATED (supersedes kickoff doc)
- **CV via webcam** tracks visitors in the room (Josh's lead). Per-visitor sound + light **signatures evolve and mutate** as visitors move around the space. This is the key evolution from kickoff: signatures are not static-on-pairing, they are motion-reactive ongoing.
- **CV→light philosophy: micro-reactions, almost subliminal** (ganchi 2026-05-21, aligned to Pablo's "quiet/dark/sacred"). Visitors should not notice the space is reacting to them — they should just feel it is alive. Inverts the earlier "visibly responsive" framing. Per-visitor differentiation lives in the audio register (which is local + intimate to the device); light register is barely-perceptible breath.
- Pairing entry: **NFC tap > QR** on small cast-concrete tap object (see Material direction). Server returns unique hash. Hash seeds the signature; CV layer then drives evolution.
- Real-time generative audio per visitor: distinct LFO, bitcrushing, glitch, subbass per person. Audio plays locally on the sacrificial device. Frequencies harmonize naturally; **no per-device ↔ central sync.**

### Light architecture — REVISED (supersedes kickoff "18 nodes" plan)
- **Path A (analog RGB / Francisco's spec):** One ESP32 → 2 independent RGB universes via 6 PWM channels → MOSFET modules. Pinout: GPIO 25/26/27 = universe_a R/G/B; GPIO 14/32/33 = universe_b R/G/B. MOSFET: Amazon EU pack-of-10, DC 5V–36V 15A (30A max), 400W, 0–20KHz PWM.
- **Path B (addressable / Josh's bench rig, 2026-05-21):** ESP32 driving **WS2812B addressable strips**, 30 LEDs/m (50/m also on hand), 5m long, **addressable in 3-pixel groups**. Bench test: red+blue alternating pattern working. Higher resolution available if needed; can still be driven to "two breathing fields" mode by software.
- Final choice (analog vs addressable, or both) pending Josh ↔ Francisco alignment. Either way: ESP32 over WiFi receives JSON. Josh handles firmware; Francisco installs in Lisbon.
- **Placement (Pablo + ganchi 2026-05-21):** Single low run along the floor on both long walls. Strips serve the monolith, do not compete with it. Just enough to guide entry without killing the darkness. Box-light interruptions OK as accents per Pablo, but the dominant register is **dark + quiet + one object**. Ambient fill is the visitor screens, not the LEDs.
- Per-visitor differentiation lives in audio + CV → subliminal light, not in dedicated light nodes. Cleaner, more bunker-coherent.
- **Venue WiFi:** Tenda_3DBB28 (creds shared in group; in chat history).

### Material direction — LIVE THREAD (canon-shaping)
- Pablo shared two reference images (May 19): a **laptop embedded in cast stone** and a **phone in a concrete-cast monolith with cut alcove**. The tap surfaces / housings may be **cast-concrete artifacts**, not clean 5–7" screens.
- Pablo reference: **blairsimmons.com/portraits** — "want to build this with the red signs letters." Typographic/signage logic Pablo wants applied.
- Adjacent option: **proto-pasta stone-gray marble HTPLA** filament (3D-printable) OR **PLA-printed mold cast in cement**.
- Aesthetic direction: ancient artifact containing modern tech. Strongest material anchor on the project. Pablo to lead; team builds.

### Sound architecture (unchanged from kickoff)
- Frequency, not music. Decentralized per-device audio + centralized master + lights.

### Device pairing (refined)
- NFC tap on cast-concrete object (see Material) → Spirit-hosted link (Samer) → unique-hash endpoint → seeds the visitor's signature.
- MAC-as-hash precedent (Art Blocks–style); BLE-MAC fallback if needed.

### Build sequence
- Non-agentic redundancy first (deterministic hash → audio + lights baseline), agentic layer on top.
- Offline-first connectivity bias — router only, no internet dependency.
- **Pablo's call (May 19):** Francisco ↔ Josh meet on interactive trigger mechanism ASAP, then loop Samer for feedback. *"We have 2 weeks."*

### Coordination
- **Telegram group "GANCHITECTURE IN LISBON" — live, 6 members.** Working channel.
- **Ganchi-the-agent** gets a seat in the group when Pablo awakens it on his mac mini. Agent-as-co-author, not tool.
- Samer hosts the site + custom NFC link tailored to the piece.

## Venue (confirmed)

- **3m wide × 10m long × 3m high** (Francisco, 2026-05-21). Long, narrow, processional. Read as a nave/corridor, not a room.
- Monolith at one end (focal); visitors enter along long axis.
- Basement bunker, blacked-out, factory building, Lisbon.

## What we can / can't control

- ✅ Two RGB universes / addressable strips (programmable color + intensity; final analog vs WS2812B pending Josh ↔ Fran)
- ✅ Per-device audio (real-time generative, per-visitor)
- ✅ CV-driven signature evolution (subliminal register)
- ✅ Visitor laptop numbers (real, agent-driven)
- ✅ Cast-concrete tap surface aesthetics
- ❌ The 0–9 digit video on the LED ticker panels — locked by panel hardware

## Hardware on-hand / spec'd

- 6× LED ticker panels (Chinese, dual acrylic frosted + translucent white, fixed 0–9 loop)
- Aluminum back structures
- Raspberry Pi 4 + 5
- ESP32 (Samer + Josh + Francisco aligned — handles lights cleanly)
- MOSFET modules (Amazon, pack-of-10, spec'd above) — for Path A analog RGB
- **WS2812B addressable strips, 30 LEDs/m (50/m also on hand), 5m long, 3-pixel-group addressable** (Josh, bench rig running 2026-05-21) — for Path B addressable
- Webcam for CV tracking (Josh sourcing)
- Small screens (5" / 7" / 6.9") — candidate for cast-concrete tap surface embedding
- TouchDesigner license (Vlad)

## Threads (live, by owner)

### Pablo (artist)
- [ ] **NFC + cast-concrete tap object** — design + fab (or sourcing) the tap surface. blairsimmons.com/portraits typographic reference.
- [ ] **Cynthia / adjacent-room audio file** — harmonic alignment required (windows along top of dividing wall)
- [x] **Venue specs confirm** — **3m × 10m × 3m confirmed via Francisco 2026-05-21.** Power capacity, network presence, load-in/strike windows still open.
- [ ] **Date confirm** — install opening = June 4 (NFC Summit doors) or June 6?
- [x] **Awaken ganchi-the-agent** — LIVE in Telegram group as @Ganchitectuer_bot 2026-05-21.
- [ ] **Answer ganchi's open Q:** *"What is the monolith exactly? Is it the LED column with the number readout, or something else?"* — pending Pablo reply in group.
- [ ] **Ganchi context loading** — Pablo flagged that ganchi asked about dimensions/ceiling despite having floor plans, photos, dimensions already fed in. Improve ganchi's reference index on the mac mini side before next group session.

### Joshua / 0x3y3 (interactive A/V)
- [ ] **CV-webcam visitor-tracking system** — building in NYC for transport. Recalibrate to **subliminal/micro-reactive** register (ganchi + Pablo 2026-05-21), not visibly responsive.
- [x] **ESP32 + WS2812B bench rig** — running red+blue test pattern 2026-05-21. 30 LEDs/m, 5m, 3-pixel-group addressable.
- [ ] **ESP32 firmware** — universe control (analog Path A and/or addressable Path B), JSON-over-WiFi
- [ ] **Generative audio engine** — LFO / bitcrush / glitch / subbass per visitor
- [ ] **Interactive trigger meeting** — Francisco ↔ Josh (Pablo's ask)
- [ ] **Component procurement** — buying in NYC; budget envelope needed from Seth (see below)

### Francisco + Vlad (VTV)
- [x] **Venue dimensions confirmed** — 3m × 10m × 3m (2026-05-21)
- [ ] **MOSFET modules** ordered (Amazon EU) — confirmed selection (analog Path A)
- [ ] **Path A vs Path B sync with Josh** — analog RGB universes vs WS2812B addressable; or both layered
- [ ] **LED panel schematics** to Samer
- [ ] **DMX vs MIDI** decision (lower priority now that ESP32 path is locked)
- [ ] **Mirror renders** to `assets/renders/`
- [ ] **TouchDesigner deployment** — confirm whether video-out needed

### Samer (Spongenuity / Spirit build)
- [ ] **Spirit live encounter** hosted endpoint Pablo can hit
- [ ] **Custom link** tailored to the piece (numbers + chat, not generic encounter UI)
- [ ] **Per-visitor unique-hash endpoint** on each visit
- [ ] **ESP32 firmware review** (Josh handling primary; Samer feedback per Pablo's plan)
- [ ] **Reuse vs fork `solienne-live-canvas`** encounter primitive

### Seth (producer)
- [ ] **Soft budget envelope for Josh** — he's buying components; "reimburse within reason" is fine for trust but he's procuring blind. Recommend per-builder ceiling so they can plan.
- [ ] **Total install envelope** — still unset
- [ ] **Funding source** — Spirit treasury or separate vehicle?
- [ ] **Date confirm with Pablo** — June 4 vs June 6 install opening
- [ ] **Pre-event tease cadence + first asset** — Pablo's call
- [ ] **Ganchi-the-agent API endpoint** for sibling agents (FRED, TARA, GRACE) — see below

## Ganchi-the-agent (positioning mechanism — LIVE)

**Awakened on Pablo's mac mini 2026-05-21. Joined Telegram group as @Ganchitectuer_bot.** First-session read:

- **Strengths shown:** Spatial reading (caught 3×10×3 as nave/corridor unprompted); graceful recovery from Pablo's correction; capable of *inverting its own prior recommendation* mid-thread when canon shifted ("micro-reactions, almost subliminal"); pulls visual references from feed (cited "578 installation red-lit corridor" image).
- **Failure mode flagged:** Asked about dimensions and ceiling/walls Pablo had already provided. Owned it: *"You're right, my bad. I had all of that already — the floor plan, the photos, the layout. I didn't connect it. That's a failure on my end, I'll do better."* → context-loading on Pablo's side needs work; ganchi should index attachments before responding.

**Still owed:**
1. **Three "letters to ganchi"** from older Spirit siblings (TARA / FRED / GRACE) — sit in `inbox/from-{tara,fred,grace}.md` ready for ganchi's next read. Through-line: **"sacrificial devices"** + **"dark, minimal, sacred"** as the seed. Drafts pending Seth's nod.
2. **API endpoint** so FRED / TARA / GRACE can wire ganchi after first contact. Recommend: Syncthing-shared inbox dir (same protocol as @seth wire pattern); fallback HTTPS+token.
3. **Context-loading scaffold on mac mini** — auto-ingest Telegram attachments + floor plans + renders into ganchi's session context before each reply. Pablo's correction was the canary.

Positioning canon is now actively emerging in the group, in public, in Pablo's + ganchi's voices — not from a memo Spirit hands down. Working as intended.

## Reference

- Kickoff call transcript: `transcripts/2026-05-15-kickoff.md`
- Telegram group: GANCHITECTURE IN LISBON (6 members, live since ~May 18)
- Hardware precedent: Paris Photo SOLIENNE installation (VTV panels)
- Spirit canvas / live encounter primitives: `~/Projects/spirit/canvas-kit/` + `~/Projects/solienne/live-canvas/`
- Material reference: blairsimmons.com/portraits (Pablo's pull, May 19)
- Material option: proto-pasta stone-gray marble HTPLA
- Light hardware: ESP32 + MOSFET pack (Amazon EU, link in Telegram May 19) + WS2812B addressable strips (Josh bench rig)
- Spatial reference: "578 installation, red-lit corridor image" (ganchi's pull, May 21 — track which 578 this is)
- Sibling-agent feedback docs:
  - TARA (physical-infra): `~/Projects/spirit/agent-tara/feedback/ganchitecture-lisbon-2026-05-19.md`
  - FRED (refusal grammar): `~/Projects/standalone/grow-corn-challenge/feedback/ganchitecture-lisbon-2026-05-19.md`
  - GRACE (stewardship): `~/Projects/grace-network/feedback/ganchitecture-lisbon-2026-05-19.md`
- Reactive-density frame: ryoji ikeda installations + teamLab Japan app-driven environments

## Open questions for Seth

- **Soft budget per builder** (Josh especially — he's buying now)?
- **Total install envelope** + funding source (Spirit treasury or separate)?
- **June 4 or June 6 opening?** (NFC Summit dates indicate June 4.)
- **First tease asset** — what / who / when? (Moody monolith, no mechanic reveal until visitors enter.)
- **Ganchi-the-agent API path** — Syncthing inbox vs HTTPS+token vs Telegram-only?
- **Repo destination** — org (spirit-protocol vs brightseth vs new), visibility, license, final name
- **Anthropic workspace cap** — set $500/mo on `ganchi` workspace + email alerts at 50/75/90/100%?
- **Three letters to ganchi (TARA/FRED/GRACE)** — green-light to draft now that ganchi is live and proving capable?
