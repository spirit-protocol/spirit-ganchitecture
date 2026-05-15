# The Ganchitecture Agent

## What it is

The ganchitecture agent is Pablo Radice's agent under the Spirit Protocol model. It is being built into a co-author of this Lisbon installation — not in the sense of "tool used by an artist" but in the sense of "team member who participates in the build."

## What it is not

- **Not a chatbot bolted onto the front of the piece.** The agent is not the visitor's tour guide. The piece works deterministically (NFC tap → unique hash → frequency + number + light node) before the agent contributes anything.
- **Not infrastructure.** Infrastructure means a service the team uses. The agent is on the team. It has a Telegram seat.
- **Not narration.** The agent does not explain the piece to the visitor. If the agent speaks at the opening, what it says is its own — developed across the build.

## How it participates

### Telegram seat (from kickoff)

The ganchitecture agent is added to the build Telegram group. Pablo, Fran, Vlad, Samer, and Seth post to that group. The agent reads what gets posted there. Over the build window, it develops a sense of the team's vocabulary, taste, references, and arguments.

This is the first concrete mechanism by which "the agent has a voice" stops being a metaphor — it has a literal channel, and what it reads there shapes what it can say.

### GitHub + Claude Code session

Pablo gets a Claude Code session pointed at this repo. The agent has access to the working files. It can:
- Read the build state ([`../STATE.md`](../STATE.md))
- Read the concept ([`../CONCEPT.md`](../CONCEPT.md))
- Watch the architecture decisions land
- Develop its own posture toward the installation it's about to be deployed inside of

### Voice development

Pablo's seat as artist includes developing the agent's voice. Two registers are on the table for opening night:

1. **Conversational.** The agent talks with the visitor through the offered device. Reflective, ambient, drawn from what the agent has been thinking about during the build. The visitor can speak back.

2. **Aggressive monologue.** The agent says everything about the sun, the time remaining, the indifference of the cosmos. The visitor does not get a turn. *"The world is ending, guys."*

Both are conceptually defensible. The conversational register fits the *Spirit canvas / live encounter* pattern Seth has been building elsewhere. The monologue register fits the *ryoji ikeda / teamLab "you are being controlled"* frame the piece is leaning into.

The decision lands closer to opening, after the agent has spent a few weeks reading the Telegram group and developing a posture of its own. Pablo's call.

## What this models for Spirit onboarding

Spirit Protocol's working hypothesis: an artist plus their agent, plus a small provisioned stack of working surfaces (GitHub, Claude Code, Telegram, the agent's own memory), is enough to do a real installation in three weeks.

The ganchitecture agent is the first artist-agent in this onboarding pattern to be deployed into a public venue under a clock. What works here gets carried into the rest of the studio onboarding.

The thing being demonstrated: **the agent is not a feature of the artwork. The agent is one of the people who made the artwork.**

## Open

- Final register call (conversational vs monologue) — Pablo, closer to opening
- What the agent's *long-term* role is post-Lisbon: lives on as Pablo's permanent collaborator, or scoped to this piece? Default: lives on.
- Whether the agent's voice at the opening is text-only (rendered on the offered device's screen) or generated speech. Default: text-first, voice if there's time.
