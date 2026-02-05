# Compound Engineering Plugin Summary

## What It Is
Every’s compound engineering plugin is a Claude Code workflow that applies a repeating loop—plan, work, review, compound—to make each unit of engineering work easier than the last.

## Tooling Notes
- Every uses Claude Code primarily, but the workflow is tool-agnostic and can also be run with other agent tools like Factory’s Droid and OpenAI’s Codex CLI.

## Core Workflow
1. Plan
- Define the problem, research codebase and relevant docs, and produce a clear plan.
2. Work
- Implement according to the plan, run tests, and finish the feature.
3. Review
- Evaluate output quality and capture lessons learned.
4. Compound
- Turn lessons into reusable knowledge to improve future cycles.
5. Repeat

## Installation (Claude Code)
```text
/plugin marketplace add https://github.com/EveryInc/compound-engineering-plugin
/plugin install compound-engineering
```

## Installation (OpenCode + Codex, experimental)
This repo includes a Bun/TypeScript CLI that converts Claude Code plugins to OpenCode or Codex formats.

```bash
# convert the compound-engineering plugin into OpenCode format
bunx @every-env/compound-plugin install compound-engineering --to opencode

# convert to Codex format
bunx @every-env/compound-plugin install compound-engineering --to codex
```

### Local development
```bash
bun run src/index.ts install ./plugins/compound-engineering --to opencode
```

### Output locations and notes
- OpenCode output goes to `~/.opencode` by default, with `opencode.json` at the root and `agents/`, `skills/`, and `plugins/` alongside it.
- Codex output goes to `~/.codex/prompts` and `~/.codex/skills`. Each Claude command becomes a prompt and a skill, with the prompt instructing Codex to load the corresponding skill.
- Generated Codex skill descriptions are truncated to 1024 characters (Codex limit).
- Both provider targets are experimental and may change as formats evolve.

## Commands and When to Use Them
- `/workflows:plan`
Turn feature ideas into detailed implementation plans.
- `/workflows:work`
Execute plans with worktrees and task tracking.
- `/workflows:review`
Run multi-agent code review before merging.
- `/workflows:compound`
Document learnings to make future work easier.

## Agent Roles and Responsibilities
- Compound engineer (human)
Orchestrates agents, evaluates output, and feeds results back into the system.
- Agents
Run in parallel to plan, write, and evaluate code.
- Compound step
Captures lessons so the system learns from successes and failures.

## Operational Guidelines
- Expect most effort in planning and review (the philosophy frames it as roughly 80% planning + review, 20% execution).
- Plan includes research: codebase, commit history, and relevant external best practices.
- Codify learnings so each cycle improves the next.

## Key Takeaways
- Each cycle compounds: plans inform future plans, reviews catch more issues, and patterns get documented.
- The process emphasizes planning and review over execution.
- The plugin is a practical way to run Every’s internal workflow.

## Access Notes
- The Every article may display a “continue reading” gate in some environments. If you have full access, verify any sections not visible here and update the summary.

## References
- `https://github.com/EveryInc/compound-engineering-plugin`
- `https://every.to/chain-of-thought/compound-engineering-how-every-codes-with-agents`
