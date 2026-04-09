---
title: Blindspot Audit
summary: A Claude Code skill that runs an 8-pass structured audit on any plan, strategy, or idea — surfacing hidden assumptions, omitted variables, and failure modes before you commit.
repo: https://github.com/GitGotGood/claude-skills/tree/main/blindspot-audit
tech: ["Claude Code", "Prompt Engineering", "Skill"]
featured: true
date: 2026-04-09
---

**A constructive-divergence audit for plans that "look coherent" but haven't been stress-tested.**

## What it is

Blindspot Audit is a Claude Code skill (invoked via `/blindspot-audit`) that systematically surfaces what you're not seeing in a plan, strategy, product idea, or analysis. It's not a generic devil's advocate — it runs a structured 8-pass sequence designed to find the specific assumptions, omissions, and framings that could quietly sink your work.

## The 8-pass audit

1. **Frame extraction** — identifies the stated and implied problem, constraints, and success definitions
2. **Alternative frame generation** — develops 3–5 plausible reframings of the situation
3. **Assumption extraction** — catalogs explicit and implicit assumptions by category
4. **Assumption fragility ranking** — prioritizes by impact, likelihood, and testability using a 1–5 severity rubric
5. **Omission scan** — identifies missing stakeholders, dependencies, and second-order effects
6. **Perspective shift** — evaluates from multiple viewpoints (user, competitor, regulator, etc.)
7. **Metric audit** — examines how your KPIs could show green while reality goes red
8. **Premortem** — models plausible 6–12 month failure scenarios with early warning signs

## What you get

A structured markdown report with a **Priority Summary** highlighting:

- Top blindspot
- Most dangerous assumption
- Best alternative frame
- Metric most likely to mislead
- Cheapest high-value test you can run next

Assumptions are scored on a 1–5 fragility scale with evidence labeled as Observed, Inferred, Guessed, or Inherited — so you know exactly how load-bearing each one is and how confident you should be.

## Who it's for

- **Strategy reviews** — stress-test a direction before committing resources
- **Product planning** — find the assumption that kills the roadmap
- **KPI audits** — check whether your metrics actually measure what you think they do
- **Research synthesis** — verify you're not inheriting someone else's blind spots
- **Pre-mortems** — model failure before it happens, not after

## How to use it

Install the skill by copying the folder to `~/.claude/skills/blindspot-audit/` (personal) or `.claude/skills/blindspot-audit/` (project-local). Then in any Claude Code session:

```
/blindspot-audit
```

Paste your plan, strategy, or idea when prompted. The audit runs in-context and produces the full report.

## No dependencies

Pure prompt engineering — no APIs, no external services, no code to run. It's a structured markdown skill definition that works anywhere Claude Code runs.
