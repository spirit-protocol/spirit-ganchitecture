# Architecture

## Three independent layers

The piece does **not** depend on real-time synchronization across visitor devices. That path is latency-fragile and would fail in a basement with marginal network. Instead we run three loosely coupled layers that each work on their own and combine in the room by virtue of being in the room.

```
┌─────────────────────────────────────────────────────────────┐
│  LAYER 1: PER-DEVICE (decentralized, no sync)               │
│  Visitor taps NFC → loads Spirit site → gets unique hash    │
│  → device plays its own planet frequency locally            │
│  → device shows its own real number on its own screen       │
└─────────────────────────────────────────────────────────────┘
                              ║ (no sync between layers)
┌─────────────────────────────────────────────────────────────┐
│  LAYER 2: CENTRAL CONTROLLER (single source, self-synced)   │
│  ESP32 (or RPi/Arduino) drives:                             │
│    - 18-node LED strip (one node lit per active visitor)    │
│    - master ambient sound + light pulse                     │
│  Counts active sessions from Layer 1 to drive density       │
└─────────────────────────────────────────────────────────────┘
                              ║
┌─────────────────────────────────────────────────────────────┐
│  LAYER 3: THE OBELISK (fixed, theatre)                      │
│  6× VTV LED ticker panels play a pre-recorded 0–9 loop      │
│  Hardware-locked — not programmable                         │
│  Functions as conceptual anchor, not real state             │
└─────────────────────────────────────────────────────────────┘
```

## Layer 1 — Per-device (decentralized)

### Entry
Visitor approaches the monolith. A small screen at the structure shows numbers; an NFC reader sits behind it. They tap their phone or laptop against it.

### Pairing
The NFC tag carries a URL to the Spirit Protocol-hosted site. On visit, the server returns a **unique hash** for that session. The hash:

- Maps deterministically to a **planet frequency** (Saturn, Mars, Earth, etc. — finite palette, randomized assignment so two adjacent visitors don't collide)
- Maps deterministically to a **visible number** that displays on the visitor's own screen
- Maps to a **light node** index for the central controller to claim

### Audio output
The device plays its planet frequency locally. No central sound mixing of per-device tone. Frequencies harmonize naturally in air because the room is small and dark and the visitor's body is the speaker.

### Visual output
The device displays its number on its own screen. This is the *real* count moving — meanwhile the obelisk loops its fake countdown nearby.

### Why decentralized
Per-device audio sync is a non-goal. The Tibetan-chant model is additive: each tone is independently correct; together they form a harmonic mass. No timing problem to solve.

## Layer 2 — Central controller

A single device (likely ESP32, see [`hardware.md`](./hardware.md)) runs the room-level effects.

### Inputs
- Count of currently active visitor sessions (from Layer 1's hash service heartbeat)
- Optional: timestamp-driven ambient cycle for slow color drift

### Outputs
- **18-node LED strip:** one node lit per active visitor. Each visitor's session claims a node by index. Strip is sectioned into 1-meter sticks, addressable per stick.
- **Master ambient sound:** a deep continuous tone or breath layer behind the per-device frequencies. Optional, calibrated against Cynthia's adjacent-room audio for cross-room harmonics.
- **Ambient base light:** dim red pulse when empty; pulse rate modulates with visitor count.

### Why centralized here
Lights and master sound only have one physical instance, so they have one driver. No sync problem because there is nothing to sync to.

## Layer 3 — The obelisk

6× VTV LED ticker panels. Stacked into a monolith with dual acrylic (frosted + translucent white) for softening. Plays a fixed 0–9 looped video that **cannot be programmed**.

Treated as conceptual scenography. Functions as anchor for the countdown narrative; bears no real state.

## Connectivity

**Offline-first.** A local router in the venue is sufficient. The Spirit site Samer hosts is reachable from the venue network via the router's WAN port — but the in-room interactions (hash → frequency → light claim) all route through the local network. If the venue's upstream internet drops mid-show, nothing the visitor experiences degrades.

## Hash → effect determinism

The unique-per-visit hash is the single shared state primitive. Both the device side (frequency + number) and the controller side (light node) read off the same hash. No additional handshake needed.

This is the **MAC-as-hash** pattern Samer flagged in kickoff — Art Blocks–style generative output keyed off device identity. We use the server-issued hash rather than the raw MAC address for portability (NFC tap works for any device; raw MAC retrieval requires BLE handshake or shared Wi-Fi).

## Build sequence

1. **Deterministic baseline first.** Hash → frequency + number + light node. No agent. No conversation. The room works.
2. **Agentic layer on top.** Once the deterministic path is solid, layer in agent voice — what the visitor's device says back, whether conversational or apocalyptic monologue.

This sequencing — non-agentic redundancy first, agentic on top — is Samer's working pattern across Spirit builds and is the load-bearing discipline for an installation that has to *just work* opening night.
