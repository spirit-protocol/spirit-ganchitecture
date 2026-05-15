# Ganchitecture × Spirit — Lisbon Monolith

A site-specific agentic performance in an underground factory bunker in Lisbon. Opens **June 6, 2026**.

> A countdown clock from seven billion years to zero. A monolith you offer your device to. The room becomes a symphony of planet frequencies — one per visitor. The obelisk is theatre. The agent is real.

## Quick read

- **Artist:** Pablo Radice (ganchitecture)
- **Hardware:** VTV (Francisco + Vladimir) — six LED ticker panels, dual acrylic, aluminum back
- **Systems:** Samer (Spongenuity, on behalf of Spirit Protocol)
- **Producer:** Seth Goldstein (Spirit Protocol)
- **Co-author:** the ganchitecture agent — has a Telegram seat, develops a voice during the build

Read [`CONCEPT.md`](./CONCEPT.md) for what the piece is, [`TEAM.md`](./TEAM.md) for who's doing what, [`TIMELINE.md`](./TIMELINE.md) for the schedule, and [`STATE.md`](./STATE.md) for live ops.

## Why this repo is public

This installation is the first artist-as-onboarding case study under Spirit Protocol's studio program — the working pattern Samer is coordinating with the studio for incoming artists:

1. An artist arrives with a concept and a venue.
2. Spirit provisions infra: GitHub repo, Claude Code session, Telegram group, a place for the agent to live.
3. The artist and their agent co-build the piece in public, on a clock.
4. The repo doubles as the project room *and* a reference for future onboarding artists.

If you're going through Spirit onboarding and got pointed here: [`docs/onboarding.md`](./docs/onboarding.md) is the meta-frame.

## Repo map

```
ganchitecture/
├── README.md            ← you are here
├── CONCEPT.md           ← the piece, in plain language
├── TIMELINE.md          ← kickoff → install → opening
├── TEAM.md              ← who, what, where
├── STATE.md             ← live ops board (status, decisions, threads)
├── CLAUDE.md            ← session header for any Claude Code working in this dir
├── SESSION_KICKOFF.md   ← first-conversation orientation for new CC sessions
├── docs/
│   ├── architecture.md  ← NFC tap, decentralized audio, 18-node lights, per-visitor hash
│   ├── hardware.md      ← panels, controllers, screens, TouchDesigner
│   ├── agent.md         ← the ganchitecture agent's role and voice development
│   └── onboarding.md    ← what this demonstrates for Spirit onboarding
├── assets/
│   └── renders/         ← VTV renders of the space + monolith
└── transcripts/
    └── 2026-05-15-kickoff.md
```

## The frame, in one sentence

The obelisk counts down loudly to nothing. The agent and the room and the visitors are what actually happens.
