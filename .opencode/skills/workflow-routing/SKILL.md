---
name: workflow-routing
description: Route user requests into the minimum-sufficient execution workflow by selecting the right subagents, skills, MCP/tools, and delegation shape before implementation starts. Use when requests are ambiguous, multi-step, cross-domain, or require explicit orchestration (especially Notion-related work, visualization requests, deep-research requests, and reasoning-heavy tasks).
---

# Workflow Routing
## Workflow
1. Classify user intent into one primary route family.
2. Load only the route-specific reference file.
3. Select subagents, skills, and MCP/tools from the capability matrix.
4. Decide delegation shape:
   - sequential: downstream step needs upstream output
   - parallel: independent workstreams
5. Produce delegation block(s) using the required template.

## Route Families
### Notion-related
- Trigger: Notion, meeting-prep, scrum, legal workflow tied to Notion workspace/pages/databases.
- Subagents: context-engineer, daily-subagent.
- Skills: notion-use, playwriter (only when browser automation is required).
- MCP/tools: notion tools first, playwriter only for UI-gated actions.
- Load: `references/routing-taxonomy.md`, `references/capability-matrix.md`, `references/delegation-templates.md`, `references/source-priority.md`.

### Visualization
- Trigger: Any request to explain, compare, or communicate with visual artifacts.
- Subagents: daily-subagent.
- Skills: visual-explainer.
- MCP/tools: local templates/references first.
- Load: `references/routing-taxonomy.md`, `references/capability-matrix.md`, `references/delegation-templates.md`.

### Deep Research
- Trigger: Explicit deep-research, evidence-backed recommendation, source triangulation.
- Subagents: context-engineer, daily-subagent.
- Skills: research, reference-find, thinking-models.
- MCP/tools: web search/fetch only after local context scan.
- Load: `references/routing-taxonomy.md`, `references/capability-matrix.md`, `references/delegation-templates.md`, `references/source-priority.md`.

### Thinking
- Trigger: Deliberation, decision framing, decomposition, uncertainty reduction.
- Subagents: daily-subagent.
- Skills: thinking-models.
- MCP/tools: local notes and repository context first.
- Load: `references/routing-taxonomy.md`, `references/capability-matrix.md`, `references/delegation-templates.md`.

### Fallback
- Trigger: User request does not match known route families.
- Subagents: daily-subagent.
- Skills: none unless route becomes clear.
- MCP/tools: gather minimum missing context, then re-route.
- Load: `references/routing-taxonomy.md`, `references/delegation-templates.md`.

## Required Delegation Template
```markdown
### Delegation
- Target Agent: daily-subagent
- Assigned Skill: [Skill Name] (e.g., meeting-prep)
- Task: [Specific User Intent]
- Context: [Outputs from Context Engineer]
```

## Reference Usage
- `references/routing-taxonomy.md`: trigger vocabulary and route family boundaries.
- `references/capability-matrix.md`: allowed combinations for subagents, skills, and MCP/tools.
- `references/delegation-templates.md`: copy-ready delegation blocks by route family.
- `references/source-priority.md`: context source loading order per route.