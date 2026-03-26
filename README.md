# Armory

**Standalone Claude Code skills forged from real problems.**

**Every skill in this repo started as a problem I watched people work around instead of solve.** I built the structural fix, tested it, and published it here so anyone can use it. No frameworks, no dependencies, no setup. Copy the skill folder into your project's `.claude/skills/` and it works.

## Install any skill

```
cp -r systematic-debugging/ your-project/.claude/skills/
```

Done.

## Skills

**Skills marked with `†` are also included in [Citadel](https://github.com/SethGammon/Citadel).** If you have Citadel, you already have them.

| Skill | What it solves |
|-------|----------------|
| [ascii-diagram](./ascii-diagram/) | LLMs misalign ASCII diagrams because they predict tokens sequentially. This skill uses a programmatic character-grid so alignment is guaranteed by math, not prediction. 31 test cases, zero false positives. |
| [systematic-debugging](./systematic-debugging/) `†` | Prevents shotgun debugging. Forces 4-phase root cause analysis — observe, hypothesize, verify, fix — with an emergency stop after 2 failed fix attempts. |
| [review](./review/) `†` | 5-pass structured code review: correctness, security, performance, readability, consistency. Language-agnostic. |
| [refactor](./refactor/) `†` | Safe multi-file refactoring with automatic rollback. Establishes a type/test baseline before touching anything, verifies zero regressions after. |
| [test-gen](./test-gen/) `†` | Generates tests by reading the project's own framework and patterns — happy path, edge cases, error paths. |
| [research](./research/) `†` | Converts a question into structured findings with confidence levels and source citations. Produces information, not decisions. |
| [research-fleet](./research-fleet/) `†` | Parallel multi-scout research. Decomposes a question into independent angles, runs scouts simultaneously, compresses findings between waves. |
| [doc-gen](./doc-gen/) `†` | Generates documentation by reading existing style first and matching it. Three modes: function-level, module-level, API reference. |
| [experiment](./experiment/) `†` | Automated optimization loop. Proposes changes in isolated worktrees, measures with a metric command, keeps improvements, discards failures. |
| [scaffold](./scaffold/) `†` | Generates new files by reading 2+ existing exemplars first. Output matches project conventions exactly because it is derived from them. |
| [triage](./triage/) `†` | GitHub issue and PR investigator. Searches the codebase for root cause, proposes fixes with file:line references, optionally implements them. |
| [session-handoff](./session-handoff/) `†` | Synthesizes a session into a structured handoff for clean context-window transfers. |
| [qa](./qa/) `†` | Browser QA via Playwright — navigates, clicks, fills forms, verifies flows. Web projects only. Gracefully skips if Playwright is not installed. |
| [live-preview](./live-preview/) `†` | Mid-build screenshot verification loop. Exits cleanly on non-UI repos. Catches invisible features before they compound. |

## How skills get added

**I find a problem nobody's solved structurally, build and test a skill that solves it, publish it here.** The bar is: works on any codebase, zero project-specific assumptions, drops in with a single copy command.

---

If you want the full orchestration infrastructure these skills were born from: github.com/SethGammon/Citadel
