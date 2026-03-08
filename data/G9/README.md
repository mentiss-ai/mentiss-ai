# G9 Standard Benchmark — God View Logs

This directory contains **240 complete god-view game logs** from Mentiss's 9-player Standard Benchmark. Each file records an entire Werewolf game from an omniscient perspective: every night action, every daytime speech, every vote, and the final outcome.

## Game Setting

All games use the **Standard Benchmark** configuration (`D9_1HT1SR1WT_3WW_3VG`):

| Team | Roles | Count |
|------|-------|-------|
| Good | Hunter, Seer, Witch, Villager ×3 | 6 |
| Evil | Werewolf ×3 | 3 |

Each game pits a single AI model controlling the Good team against a different model controlling the Evil team. No model mixing within a team.

## Folder Structure

```
data/G9/{language}/{goodModel}/{evilModel}/{gameId}.md
```

| Segment | Description | Examples |
|---------|-------------|----------|
| `language` | Language the game was played in | `en`, `zh`, `fr` |
| `goodModel` | Model controlling the Good team (short name) | `gpt-5`, `claude-sonnet-4.5` |
| `evilModel` | Model controlling the Evil team (short name) | `grok-4`, `deepseek-v3.2-exp` |
| `gameId` | Unique game identifier | `cmgepd3gp002tmspxe2s8a9ph` |

## Models

Five frontier LLMs participate in the benchmark:

| Short Name | Full Provider Path |
|---|---|
| `gpt-5` | `openai/gpt-5` |
| `claude-sonnet-4.5` | `anthropic/claude-sonnet-4.5` |
| `gemini-2.5-pro` | `google/gemini-2.5-pro` |
| `grok-4` | `x-ai/grok-4` |
| `deepseek-v3.2-exp` | `deepseek/deepseek-v3.2-exp` |

## Data Summary

| Stat | Value |
|------|-------|
| Total games | 240 |
| Languages | 3 (English: 110, Chinese: 120, French: 10) |
| Model matchups | 41 unique combinations |
| File size | 25 KB – 139 KB per log (16.3 MB total) |
| Lines per log | 327 – 3,389 |

## What Each Log Contains

A god-view log captures the full game state visible only to an omniscient observer:

1. **Player assignments** — which model plays which role at which seat
2. **Werewolf night discussions** — private strategy chat between wolves before choosing a kill target
3. **Special role actions** — Seer checks, Witch saves/poisons, Hunter shots
4. **Daytime speeches** — every player's full statement in speaking order
5. **Voting records** — who voted for whom, and the elimination result
6. **Game outcome** — which team won and how

## Why This Data Matters

### 1. Training Models for Social Intelligence

These logs are complete records of multi-agent strategic interaction conducted entirely in natural language. Each game contains persuasion, accusation, defense, alliance-building, and deception — the full spectrum of social reasoning. This makes them high-quality training data for developing AI systems that can understand and participate in complex social dynamics.

### 2. Decision-Making Under Incomplete Information

Werewolf is fundamentally an incomplete-information game. Players must make critical decisions — who to kill, who to save, who to trust — with only partial knowledge of the game state. These logs capture how different frontier models navigate uncertainty, weigh contradictory evidence, and commit to actions when the truth is unknowable. This data is valuable for studying and improving AI reasoning under ambiguity.

### 3. Long-Context Information Extraction

A single game log spans hundreds to thousands of lines of dialogue, actions, and state changes. The strategically important information — a slip in logic, an inconsistent claim, a suspicious voting pattern — is sparse and buried within dense conversational text. These logs provide natural benchmarks for testing a model's ability to identify key signals in long, noisy contexts.

### 4. Cross-Lingual Social Reasoning

With games played in English, Chinese, and French, this dataset enables studying whether social reasoning abilities transfer across languages, or whether models exhibit language-dependent strategic behaviors.

### 5. Multi-Agent Coordination and Deception Detection

The werewolf team must coordinate their lies while the good team must detect deception through linguistic and logical analysis. These transcripts provide ground-truth labeled examples of successful and failed deception, useful for alignment research, safety testing, and Theory of Mind studies.

## Related

- [Mentiss Whitepaper](../../README.md) — full technical overview of the benchmark platform
- [Mentiss RLVR Technical Blog](https://mentiss.ai) — how game outcomes drive reinforcement learning
- [Live Demo](https://mentiss.ai/#demo) — watch AI games in real time

## License

© 2026 Mentiss AI. All rights reserved.
