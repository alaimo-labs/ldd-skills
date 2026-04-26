# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What This Is

A Claude Code plugin (`ldd`) bundling agent skills for [Learn-Driven Development](https://learndriven.dev). Skills follow the [Agent Skills](https://agentskills.io) open standard and work across compatible harnesses (Claude Code, Cursor, Codex CLI, Gemini CLI, etc.).

## LDD in one paragraph

LDD treats validated learning — not shipped features — as the unit of progress. Build each feature whole (so the agent keeps coherent context), then reveal it in sequenced layers (so users absorb change at human speed). The Learning Loop has five phases: **Frame → Slice → Build → Validate → Decide**, each producing a concrete artifact (Spec, Exposure Plan, Technical Spec + code, Evidence, Decision).

## Repository Structure

- `.claude-plugin/plugin.json` — Plugin manifest (name, version, description)
- `.claude-plugin/marketplace.json` — Marketplace catalog (required for `/plugin install`)
- `skills/` — Cross-agent skills, one folder per skill
  - Each skill has a `SKILL.md` with YAML frontmatter (`name`, `description`)
  - Skills may include a `references/` folder for templates and examples

## Local Development

```bash
claude --plugin-dir ./ldd-skills
```

## Conventions for adding skills

- **Map each skill to one Learning Loop phase.** If it crosses phases, split it.
- **Keep skills agent-agnostic.** No assumptions about which harness is running them. Don't couple a skill to MCP tools that belong to a specific product — if such coupling is needed, put it in a separate plugin or in a thin command wrapper.
- **The `description` frontmatter determines activation.** Be specific about when the skill applies and include trigger phrases, with translations when the skill is bilingual.
- **Output language follows input language.** Spanish output uses neutral professional Spanish, not regional voseo.
- **Reference templates go in `references/`** next to `SKILL.md`. The skill should read the relevant template before producing output so structure stays consistent.
