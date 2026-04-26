# LDD Skills

Agent skills for [Learn-Driven Development](https://learndriven.dev) (LDD) — a methodology for building software with AI agents where **validated learning, not shipped features, is the unit of progress**.

## What is LDD?

AI agents can build a complete feature in hours, but users can't absorb change at that pace. Shipping faster than people can adapt erodes the feedback loops that make the work worth doing in the first place.

LDD's response: **build whole, reveal selectively**. Each feature is constructed in one coherent pass while the agent holds full context, then delivery is decoupled from exposure — feature flags, progressive rollouts, canaries — so users meet the change at human speed.

### Core principles

1. **The Learning Loop is the Atom.** The smallest unit of work is a complete learning cycle, not a shipped feature.
2. **Users Set the Absorption Ceiling.** Pace is capped by how much change humans can absorb, not by how fast an agent can ship.
3. **Agents Drift When Context Is Rebuilt.** Thin-slice builds force agents to reconstruct context every slice, introducing drift. Build whole; reveal in slices instead.

### The Learning Loop

| Phase | Activity | Artifact |
|---|---|---|
| **Frame** | Shape the spec around a bet and testable hypothesis | Spec |
| **Slice** | Design what to reveal, to whom, in what sequence | Exposure Plan |
| **Build** | Produce technical spec and implement the whole feature with reveal controls | Technical Spec + code |
| **Validate** | Reveal progressively and gather evidence | Evidence |
| **Decide** | Double down, pivot, or abandon | Decision |

The full thesis lives at [learndriven.dev](https://learndriven.dev).

## What's included

### Skills (cross-agent compatible)

| Skill | Phase | Description |
|---|---|---|
| [`slice-this-feature`](./skills/slice-this-feature/) | Slice | Turn a feature spec's hypothesis into an accumulative Exposure Plan: 1–5 reveal levels, each testing one belief, with audience, duration, and validation criteria. Bilingual (EN/ES). |

All skills follow the [Agent Skills](https://agentskills.io) open standard and work with Claude Code, Gemini CLI, Cursor, Codex CLI, and other compatible harnesses.

More skills will land here as the loop's other phases get tooled.

## Setup (Claude Code)

### 1. Install the plugin

Inside a Claude Code session, add the marketplace and install the plugin:

```
/plugin marketplace add alaimo-labs/ldd-skills
/plugin install ldd@ldd-skills
```

### 2. Update the plugin

```
/plugin update ldd@ldd-skills
```

### Local development

```bash
claude --plugin-dir ./ldd-skills
```

## Using a skill

Each skill is triggered by activation phrases documented in its `SKILL.md`. For example, with a feature spec in context, say "slice this feature" (or "divide esta feature") to invoke `slice-this-feature` and produce an Exposure Plan.

## Author

[Martín Alaimo](https://alaimolabs.com)

## License

[MIT](./LICENSE)
