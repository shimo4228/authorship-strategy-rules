# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/), and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.0.0] — 2026-07-04

Initial release as a standalone rules-file repository.

### Added

- `rules/common/authorship-strategy.md` — the Authorship Strategy framework distilled into a single always-loaded behavioral rule: the trigger condition (your own DOI-registered idea-rescue research repositories), the four-layer judgment stack (authenticity → attribution diffusion → idea/scaffold separation → tactics), and the prohibited/encouraged actions. Installs the framework deterministically, as the always-on counterpart to the on-demand [`authorship-strategy-skill`](https://github.com/shimo4228/authorship-strategy-skill).
- `scripts/sync-from-local.sh` — one-way export from the live Claude Code harness; the harness copy (`~/.claude/rules/common/authorship-strategy.md`) is canonical, this repository is the publication mirror (secret-scanned, never auto-committing).

### Notes

- The published rule is generalized for any adopter: the trigger gates on repositories **you own** (rather than a specific author name), with the author's own research lines kept as illustrative examples. The framework's judgment is unchanged; the generalization only makes the rule a portable drop-in.
- Belongs to the [Authorship Strategy](https://github.com/shimo4228/authorship-strategy) research line ([DOI 10.5281/zenodo.20263316](https://doi.org/10.5281/zenodo.20263316)). The doctrine (thesis, ADRs, knowledge graph, empirical baseline) stays in the research repository; the deeper judgment reference is the [`authorship-strategy-skill`](https://github.com/shimo4228/authorship-strategy-skill); this repository is the rules-file install target.
