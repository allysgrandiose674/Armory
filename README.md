# Armory — Standalone Claude Code Skills

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Claude Code](https://img.shields.io/badge/Claude_Code-compatible-blueviolet.svg)](https://docs.anthropic.com/en/docs/claude-code)

Standalone Claude Code skills forged from real problems.

**Every skill in this repo started as a problem I watched people work around instead of solve.** I built the structural fix, tested it, and published it here. No frameworks, no dependencies, no setup beyond a folder copy. Each skill works on any codebase, on any OS, the moment you drop it in.

## Install

**Prerequisites:** [Claude Code](https://docs.anthropic.com/en/docs/claude-code)

Clone the repo, then copy any skill folder into your project:

```bash
git clone https://github.com/SethGammon/Armory.git
```

**Mac / Linux:**
```bash
cp -r Armory/systematic-debugging your-project/.claude/skills/
```

**Windows (PowerShell):**
```powershell
Copy-Item -Recurse Armory\systematic-debugging your-project\.claude\skills\
```

**Windows (Command Prompt):**
```cmd
xcopy /E /I Armory\systematic-debugging your-project\.claude\skills\systematic-debugging
```

Or drag the folder in Explorer. There is no installer — the skill is the folder.

## Skills

**Skills marked with `†` are also included in [Citadel](https://github.com/SethGammon/Citadel).** If you have Citadel, you already have them.

### Debugging & Review
| Skill | What it solves |
|-------|----------------|
| [systematic-debugging](./systematic-debugging/) `†` | Prevents shotgun debugging. Forces 4-phase root cause analysis — observe, hypothesize, verify, fix — with an emergency stop after 2 failed fix attempts. |
| [review](./review/) `†` | 5-pass structured code review: correctness, security, performance, readability, consistency. Language-agnostic. |
| [triage](./triage/) `†` | GitHub issue and PR investigator. Searches the codebase for root cause, proposes fixes with file:line references, optionally implements them. |

### Code Generation
| Skill | What it solves |
|-------|----------------|
| [scaffold](./scaffold/) `†` | Generates new files by reading 2+ existing exemplars first. Output matches your project's conventions because it is derived from them. |
| [refactor](./refactor/) `†` | Safe multi-file refactoring with automatic rollback. Establishes a type/test baseline before touching anything, verifies zero regressions after. |
| [test-gen](./test-gen/) `†` | Generates tests by reading your project's own framework and patterns. Happy path, edge cases, error paths. |
| [doc-gen](./doc-gen/) `†` | Generates documentation by reading existing style first and matching it. Three modes: function-level, module-level, API reference. |

### Research & Optimization
| Skill | What it solves |
|-------|----------------|
| [research](./research/) `†` | Converts a question into structured findings with confidence levels and source citations. Produces information, not decisions. |
| [research-fleet](./research-fleet/) `†` | Parallel multi-scout research. Decomposes a question into independent angles, runs scouts simultaneously, compresses findings between waves. |
| [experiment](./experiment/) `†` | Automated optimization loop. Proposes changes in isolated worktrees, measures with a metric command, keeps improvements, discards failures. |

### Diagrams & Utilities
| Skill | What it solves |
|-------|----------------|
| [ascii-diagram](./ascii-diagram/) | LLMs misalign ASCII diagrams because they predict tokens sequentially. This skill uses a programmatic character-grid — alignment is guaranteed by math, not prediction. 31 test cases, zero false positives. |
| [session-handoff](./session-handoff/) `†` | Synthesizes a session into a structured handoff block for clean context-window transfers. |

### Visual Verification
| Skill | What it solves |
|-------|----------------|
| [live-preview](./live-preview/) `†` | Mid-build screenshot verification loop. Catches invisible features before they compound. Exits cleanly on non-UI repos. Requires Playwright (optional). |
| [qa](./qa/) `†` | Browser QA via Playwright — navigates, clicks, fills forms, verifies flows. Web projects only. Gracefully skips if Playwright is not installed. |

## How skills get added

**I find a problem nobody's solved structurally, build and test a skill that solves it, publish it here.** The bar is: works on any codebase, zero project-specific assumptions, drops in with a folder copy.

---

**Want the full orchestration infrastructure these skills were born from?**
[Citadel](https://github.com/SethGammon/Citadel) — autonomous campaign agents, parallel fleet coordination, lifecycle hooks, and the `/do` router that dispatches all of it.
