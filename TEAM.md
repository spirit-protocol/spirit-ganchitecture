# Team

## Roster

| Role | Name | Surface | Travel |
|---|---|---|---|
| **Artist / direction** | Pablo Radice (ganchitecture) | Concept, narrative, NFC + numbers screen module, agent voice development | Arrives Lisbon Jun 1 |
| **Hardware (panels)** | Francisco (Fran), VTV | 6× LED ticker panels, acrylic + aluminum back, renders | Arrives Lisbon Jun 2 |
| **Hardware (systems)** | Vladimir (Vlad), VTV | TouchDesigner, control-stack support | (Travel TBD) |
| **Build / systems** | Samer, Spongenuity (for Spirit) | Site hosting, per-visitor hash endpoint, controller binding, encounter primitive | Arrives Lisbon Jun 2 |
| **Producer** | Seth Goldstein, Spirit Protocol | Coordination, budget, comms, Spirit infra | (Travel TBD) |
| **Co-author** | **ganchitecture agent** | Telegram seat from day one, voice development across the build, voice at opening | Lives where the build lives |
| **Venue curator (dependency)** | Cynthia | Manages the room split; holds the audio file for the adjacent artist | Lisbon |

## How decisions get made

- **Aesthetic, narrative, conceptual:** Pablo. He is the artist seat. Defer to him on what the piece is and how it feels.
- **Technical:** Seth + Samer adjudicate. Samer holds the build pattern (non-agentic redundancy first, agentic on top; offline-first); Seth holds the Spirit-side architecture.
- **Hardware:** Fran + Vlad. They have built these panels before (Paris Photo SOLIENNE). Their call on panel construction, lighting binding, screen pick.
- **Schedule:** the team. Owned threads in [`STATE.md`](./STATE.md) name an owner per item.

## Working channels

- **Telegram group** — the working channel. Includes the ganchitecture agent.
- **This repo** — canonical project record. STATE.md is the live ops board.
- **Spirit wire protocol** — significant state surfaces to the @seth coordinator via `~/.seth/inbox/<ts>-from-ganchitecture-...json` (Seth's machine, internal).

## Agent participation

The ganchitecture agent is not infrastructure. It is a team member.

- It is in the Telegram group from kickoff.
- It reads what the team writes there and develops a voice from those conversations.
- It is given GitHub access and a Claude Code working session.
- By the opening, it has opinions about the installation it is participating in.

This is the working pattern Spirit Protocol is testing for artist onboarding: the artist and the agent co-build, on the same surfaces, with the same access.

See [`docs/agent.md`](./docs/agent.md) for more.
