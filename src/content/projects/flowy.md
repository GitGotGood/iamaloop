---
title: Flowy
summary: An open-source flowchart editor with a REST API — humans draw visually, AI agents POST JSON, both share the same canvas.
repo: https://github.com/GitGotGood/flowy
demo: https://flowy.iamaloop.com
tech: ["TypeScript", "React", "REST API"]
featured: true
date: 2026-04-05
---

**A flowchart tool built for the way humans and AI actually work together.**

## What it is

Flowy is an open-source flowchart editor with a REST API. Humans draw flows visually in the browser. AI agents create flows by POSTing JSON. Both work on the same canvas, the same data format, the same tool.

## What it does

- **For humans:** A clean, dark-themed editor with drag-and-drop nodes, animated directional edges, undo/redo, auto-layout, and one-click export. Flows save automatically to your browser — no account needed.
- **For AI agents:** A simple REST API. POST nodes and edges as JSON, skip the coordinates (auto-layout handles positioning), get back a shareable URL. Any agent that can make an HTTP request can draw a flowchart.
- **For both:** Published flows live at a public URL for 24 hours. Humans can fork agent-created flows into their browser and edit them. Agents can read human-edited flows back as JSON. The round-trip is seamless.

## Why it matters

AI systems are getting more complex — multi-agent pipelines, feedback loops, human-in-the-loop checkpoints. But the humans overseeing these systems often can't *see* what's happening. They get logs, maybe a dashboard, but not a clear picture of the structure.

Flowy makes AI systems visible. An agent can draw its own pipeline as a flowchart and hand it to a human. A human can sketch a process and hand it to an agent as structured data. It's a shared language — visual for humans, JSON for machines, same underlying graph.

## Key features

- **8 node types** — start, end, process, decision, I/O, fork, join, review (human checkpoint)
- **Animated edges** — flowing dots show direction at a glance; gold dashed lines for feedback loops
- **Loop mode** — toggle Start/End nodes to represent cyclical systems, not just linear pipelines
- **Node metadata** — input/output schemas, permission badges (NET, LLM, FS-R), descriptions
- **Auto-layout** — agents don't need to calculate positions; the layout algorithm handles DAGs, cycles, and parallel branches
- **Import/Export** — paste JSON from any AI chat, upload files, download flows
- **AI Instructions button** — one click copies the full API docs to your clipboard, ready to paste into any AI conversation
- **Zero friction** — no accounts, no login, flows live in your browser by default

## What it's been used for

During development, Flowy was stress-tested with:
- **Agent pipelines** — editorial team workflows with parallel writers and human review gates
- **Narrative structure** — Poe's "The Tell-Tale Heart" mapped as a flowchart, with psychological feedback loops rendered as gold cycling edges
- **Complex graphs** — a 37-node, 150-edge "Layered Organism Architecture" modeling emergent human behavior

## The bigger idea

Flowy started as "agents should be able to draw flowcharts." It turned into something larger: a universal structure communication format between humans and AI. Flowcharts for code, for processes, for stories, for systems, for arguments. The same primitives — nodes, edges, decisions, feedback loops — map to all of them.

As AI systems become more autonomous, transparency becomes critical. Flowy is a step toward making AI systems legible to the humans who work with them.

## Try it

Create a flow in the browser at [flowy.iamaloop.com](https://flowy.iamaloop.com), or have an AI generate one:

```bash
curl -X POST https://flowy.iamaloop.com/flows \
  -H "Content-Type: application/json" \
  -d '{"title":"Hello Flowy","nodes":[{"id":"a","type":"start","label":"Begin"},{"id":"b","type":"end","label":"Done"}],"edges":[{"id":"e1","source":"a","target":"b"}]}'
```
