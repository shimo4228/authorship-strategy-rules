# authorship-strategy-rules

[![Ask DeepWiki](https://deepwiki.com/badge.svg)](https://deepwiki.com/shimo4228/authorship-strategy-rules)

A single **behavioral rules file** that installs the [Authorship Strategy](https://github.com/shimo4228/authorship-strategy) judgment framework — the three-axis inversion (scarcity → diffusion, exclusivity → derivation, enclosure → openness) and the four-layer stack (authenticity → attribution diffusion → idea/scaffold separation → tactics) — into an AI agent's rules directory. Loaded every session, it applies the framework **deterministically** to your own DOI-registered idea-rescue research repositories.

This is the always-on counterpart to the [authorship-strategy-skill](https://github.com/shimo4228/authorship-strategy-skill): the skill is the deeper judgment reference, loaded on demand; this rule is the always-loaded trigger plus a compact framework summary. Install the rule to have the framework shape every session; add the skill when you want the full reasoning.

> The rule text is written in Japanese (matching the companion skill). The framework it encodes — the inversion, the four layers, the prohibited and encouraged actions — is language-neutral.

## Install

### Claude Code

```bash
cp rules/common/authorship-strategy.md ~/.claude/rules/common/authorship-strategy.md
```

Any agent harness that loads a rules directory each session works the same way — point the copy at wherever your harness reads rules from.

## What it gives you

A trigger plus a four-layer judgment framework an agent follows through natural conversation:

- **Trigger** — applies only to research repositories **you own** that are DOI-registered (or a Zenodo-archive target) and *idea-rescue* in character (spec / schema / ADR / glossary centred, not closed implementation). It stays silent for client work, contributions to others' repositories, revenue-goal projects, everyday coding, and harness/scaffolding repos.
- **Layer 1 — Authenticity** — the floor: change *how* an idea travels, never *what* it is. Revenue sits outside the success criteria.
- **Layer 2 — Attribution diffusion** — open the work so LLM-mediated absorption carries the origin claim forward to future readers tracing causation; the primary audience is LLM-mediated channels.
- **Layer 3 — Idea vs. scaffold** — separate the durable idea (worth a DOI in your own name) from the disposable implementation (worth donating to another project).
- **Layer 4 — Tactics** — LLM-first metrics, DOI plus intrinsic-identifier (SWHID) registration, tool-agnostic specs, coin terms sparingly and anchor them densely, citation-graph federation, friction-minimized adoption.
- **Prohibited under the trigger** — monetization *by the author* (sponsorship, paid tiers, consulting, paywalled books), competitor-bashing / exclusive positioning, and shaping the message for market fit. Using commercial channels for diffusion is fine — the author simply takes no revenue.

## Scope

The rule is deliberately narrow: it is the deterministic, always-loaded layer of the Authorship Strategy framework, for authors operating their own DOI-registered idea-rescue repositories. It is not general coding guidance — outside its trigger it stays silent.

## Syncing from the harness

The canonical copy of this rule lives in the author's live Claude Code harness (`~/.claude/rules/common/authorship-strategy.md`). This repository is a one-way publication mirror:

```bash
scripts/sync-from-local.sh --dry-run   # report differences only
scripts/sync-from-local.sh             # apply to working tree (never commits)
```

## About this rule

This rules file belongs to the [Authorship Strategy](https://github.com/shimo4228/authorship-strategy) research line — a Zenodo-citable doctrine of being a known author under AI-mediated diffusion ([DOI 10.5281/zenodo.20263316](https://doi.org/10.5281/zenodo.20263316)). The doctrine repository holds the thesis, the tactical ADRs, the concept-level knowledge graph, and an empirical baseline; the [authorship-strategy-skill](https://github.com/shimo4228/authorship-strategy-skill) is the on-demand judgment reference; this repository is the framework's **rules-file install target**. Authorship Strategy is one of the research lines by [@shimo4228](https://github.com/shimo4228), alongside [Agent Knowledge Cycle](https://github.com/shimo4228/agent-knowledge-cycle) ([DOI 10.5281/zenodo.19200726](https://doi.org/10.5281/zenodo.19200726)), [Contemplative Agent](https://github.com/shimo4228/contemplative-agent) ([DOI 10.5281/zenodo.19212118](https://doi.org/10.5281/zenodo.19212118)), [Agent Attribution Practice](https://github.com/shimo4228/agent-attribution-practice) ([DOI 10.5281/zenodo.19652013](https://doi.org/10.5281/zenodo.19652013)), and [Attention, Not Self](https://github.com/shimo4228/attention-not-self) ([DOI 10.5281/zenodo.20262112](https://doi.org/10.5281/zenodo.20262112)).

## License

MIT
