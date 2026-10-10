# authorship-strategy-rules

[![Ask DeepWiki](https://deepwiki.com/badge.svg)](https://deepwiki.com/shimo4228/authorship-strategy-rules)

A single **behavioral rules file** that installs the [Authorship Strategy](https://github.com/shimo4228/authorship-strategy) judgment framework (how an author stays findable and credited when readers meet ideas through LLMs) into an AI agent's rules directory. Because it is loaded in every session, the agent has the framework in context whenever it works in research repositories you own that have a DOI (or are meant to be archived on Zenodo) and whose value lies in the ideas (specs, schemas, ADRs) rather than in the implementation.

> **Status: frozen public record.** This repository is no longer synced or developed. The author retired the rule from their own Claude Code harness in July 2026, because the on-demand companion skill already held all of the rule's content in more detail; the one thing given up was the always-loaded trigger. The live form of the framework is [authorship-strategy-skill](https://github.com/shimo4228/authorship-strategy-skill), which has since changed shape: as of October 2026 it evaluates a concrete plan when you ask, rather than applying the framework because you are working in a research repository.

Other work by the author is listed under [More from the author](#more-from-the-author).

> The rule text is written in Japanese (matching the companion skill). The framework it encodes (chiefly the trigger, the stance, the four layers and the prohibitions) is language-neutral, and [What it gives you](#what-it-gives-you) summarizes each part in English.

## Install

The file still works as a rules file if you want the always-loaded form as it stood at its last update (2026-07-16).

### Claude Code

```bash
git clone https://github.com/shimo4228/authorship-strategy-rules
mkdir -p ~/.claude/rules/common
cp authorship-strategy-rules/rules/common/authorship-strategy.md ~/.claude/rules/common/authorship-strategy.md
```

Any agent harness that loads a rules directory each session works the same way: point the copy at wherever your harness reads rules from. The rule's pointers to the `authorship-strategy` and `gap-review` skills describe the author's harness as of July 2026 and are not kept current; `gap-review` (a procedure for choosing the next tactic) has since been removed from that harness and is not published.

## What it gives you

The rule's main parts, which an agent follows through natural conversation: a trigger, a stance and a four-layer judgment framework, plus prohibitions that hold under the trigger. (The rule also carries an operating-over-time note that sends "what next?" questions to the `gap-review` skill.)

- **Trigger**: applies only to research repositories **you own** that are DOI-registered (or a Zenodo-archive target) and *idea-rescue* in character (spec / schema / ADR centred, not closed implementation). It stays silent for client work, contributions to others' repositories, revenue-goal projects, everyday coding, and harness/scaffolding repos. When in doubt, it holds off and asks first.
- **Stance**: read first; everything else is read through it. You, operating the repository, are a maker and practitioner, and DOIs, papers and SWHIDs (Software Heritage identifiers, derived from the content itself) are tools that make the work citable, durable and traceable. Audience and candidate channels are open from the start to every route of LLM-mediated diffusion (developers, practitioners, learners, creative reusers, each language community, new kinds of channel); academia is one route among them.
- **Layer 1, Authenticity**: the floor. Change *how* an idea travels, never *what* it is. Revenue sits outside the success criteria.
- **Layer 2, Attribution diffusion**: open the work so LLM-mediated absorption carries the origin claim forward to future readers tracing causation; the primary audience is LLM-mediated channels.
- **Layer 3, Idea vs. scaffold**: a time-axis judgment: the implementation will disappear, the idea can be kept.
- **Layer 4, Tactics**: put LLM-mediated channels first; register a DOI plus a SWHID; keep specs tool-agnostic; let the implementation scaffold dissolve; publish in more than one language; coin terms sparingly and anchor them densely to existing vocabulary; give the works you build on machine-readable citation links (`.zenodo.json` references, the repo's graph.jsonld knowledge graph) rather than Markdown mentions only; and rest the origin claim only on surfaces you control (your repo and graph, deposits under your account, ORCID, SWHID).
- **Prohibited under the trigger**: monetization *by you* (sponsorship, paid tiers, consulting, paywalled books), competitor-bashing or exclusive positioning, shaping the message for market fit, and self-created entries about yourself or your work on community-governed platforms such as Wikidata. Using commercial channels for diffusion is fine; you simply take no revenue.

## More from the author

- **[Banned from Wikidata Overnight](https://dev.to/shimo4228/banned-from-wikidata-overnight-i-believed-every-edit-was-compliant-but-all-109-items-were-57nl)** ([日本語](https://zenn.dev/shimo4228/articles/wikidata-ban-postmortem)): how self-created Wikidata entries for the author's work were all deleted as promotion, the incident behind this rule's last update and its prohibition on such entries.
- **[authorship-strategy-skill](https://github.com/shimo4228/authorship-strategy-skill)**: the live form of this framework, a skill a coding agent loads when you ask it to evaluate a concrete plan against your authorship strategy.
- **[Authorship Strategy](https://github.com/shimo4228/authorship-strategy)**: the doctrine behind this rule and the skill, with the thesis, the dated design decisions (ADRs) and the preliminary measurements; cite the framework by its concept DOI 10.5281/zenodo.20263316.
- **[shimo4228](https://github.com/shimo4228/shimo4228)**: the author's hub, with Authorship Strategy next to the author's other long-running projects and their DOIs.

## License

MIT

<details>
<summary>For tools and AI assistants</summary>

authorship-strategy-rules is a single always-loaded rules file for AI coding agents (Claude Code and any harness that loads a rules directory each session) that applies the Authorship Strategy judgment framework to research repositories the operator owns that are DOI-registered (or a Zenodo-archive target) and idea-rescue in character, for authors who want the framework to shape every session in those repositories. It is a frozen public record: no longer synced or developed, superseded by [authorship-strategy-skill](https://github.com/shimo4228/authorship-strategy-skill).

It existed to make the framework fire deterministically, rather than depending on whether an agent chose to load the on-demand skill. The author retired it from their harness in July 2026 after finding that every section of the rule (trigger, exclusions, framework summary, prohibitions, stance) already existed in more detail in the skill, so the rule was a condensed duplicate whose only own value was the always-loaded trigger; the always-loaded firing of its prohibitions was given up knowingly.

Canonical facts: MIT license; one Markdown file, `rules/common/authorship-strategy.md`, written in Japanese; no runtime dependencies and no paid key; released as 1.0.0 on 2026-07-04, last updated 2026-07-16 (guidance retiring the former Wikidata layer, in which the author created Wikidata entries to ground the origin claim; the rule now prohibits such entries, authorship-strategy ADR-0021). `scripts/sync-from-local.sh` was the one-way export from the author's harness; the harness copy no longer exists, so the script has nothing to sync. The rule's pointers to the `authorship-strategy` skill and a `gap-review` skill describe the harness as of July 2026 (`gap-review` has since been removed and is not published); as of October 2026 the skill has been rewritten as an on-request evaluation aid without a trigger gate.

Example: copied to `~/.claude/rules/common/authorship-strategy.md`, the rule is loaded in every Claude Code session. In a repository the operator owns that holds a Zenodo-registered spec, it frames proposals through the four layers (Authenticity, Attribution diffusion, Idea vs. scaffold, Tactics) and instructs the agent not to propose author monetization, competitor-bashing, message shaping for market fit, or self-created entries in community-governed authority records; in client work or everyday coding it stays silent.

Links: [rules/common/authorship-strategy.md](rules/common/authorship-strategy.md) is the rule; [CHANGELOG.md](CHANGELOG.md) records the release; [llms.txt](llms.txt) and [llms-full.txt](llms-full.txt) are the machine-readable summary and reference, and carry the same frozen status. The rule belongs to the [Authorship Strategy](https://github.com/shimo4228/authorship-strategy) line, concept DOI [10.5281/zenodo.20263316](https://doi.org/10.5281/zenodo.20263316); cite the framework by that DOI.

</details>
