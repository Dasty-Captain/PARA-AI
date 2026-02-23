---
title: Agent Workflow Capture (Context -> Obsidian -> Notion)
date: 2026-02-19
status: draft
---

Objective
- Capture agent session context, archive inputs/outputs in Obsidian as a unified knowledgebase, then publish a polished Notion document.

Workflow
```mermaid
flowchart TD
  A[1) Agent Session] --> B[Update context\ncontext-updater.md]
  B --> C[2) Save artifacts in Obsidian\nInitial prompt + final deliverable\n(unified knowledgebase)]
  C --> D[Final polish\n(structure, clarity, formatting)]
  D --> E[3) Notion Document\n(publish/share/canonical)]
```

Missing items (recommended minimum)
- Stable deliverable_id used across: context-updater.md, Obsidian note, Notion doc.
- Source-of-truth rule: Obsidian as immutable archive vs Notion as canonical/latest.
- Status + versioning: draft -> polished -> final -> published; published -> revised with version bumps.
- Backlinks: Obsidian note stores Notion URL; Notion doc stores Obsidian note path (or deliverable_id).
- Pre-Notion safety check: redact secrets/PII; set sensitivity (public/internal/restricted).
- QA checklist in final polish: completeness, link check, decisions captured, formatting.

Workflow Tree
Agent Session
├─ context-updater.md
├─ Obsidian
│  ├─ initial prompt (archived)
│  └─ final deliverable (archived)
├─ final polish
└─ Notion document (published)
