# Initial Thoughts
***
- **Goal**: There are multiple subagents, MCPs, and skills. I'm trying to make a skill for my agents and subagents to find the right subagents, MCPs, and skills based on user request tiggers. This will be called ALWAYS at the first turn. Make it based on below high-level workflow: 
	- notion-related task: 
		- trigger: when Notion, meeting-prep, scrum, legal related task came out.
		- subagents: context-engineer, daily-subagent
		- MCPs: playwriter
		- skills: playwriter, notion-use
	- visualization: 
		- trigger: when user asks ANYTHING about visualization. 
		- subagents: X
		- MCPs: X
		- skills: visual-explainer
	- deep Research: 
		- trigger: when user mentions ANYTHING related to deep-research. 
		- subagents: context-engineer, daily-subagent
		- MCPs: X
		- skills: thinking-models, research, reference-find
	- Thinking
		- trigger: (almost everytime) when it requires some deep-reasoning or deliberation. 
		- subagents: daily-subagent
		- MCPs: X
		- skills: thinking-models
	- Also, it should make a right format to delegate properly. Use this format to call each subagents. 
```markdown
### Delegation
- Target Agent: daily-subagent
- Assigned Skill: [Skill Name] (e.g., meeting-prep)
- Task: [Specific User Intent]
- Context: [Outputs from Context Engineer]
```

# TO-DOs
***

- [x] **First - lock scope**: Confirm route families and hard triggers (Notion, visualization, deep research, thinking) plus default fallback route.
- [x] **First - define routing contract**: Finalize one delegation schema with required fields (`Target Agent`, `Assigned Skills`, `Task`, `Context Sources`, `Done Checks`, `Fallback`).
- [ ] **Next - map capabilities**: Build a matrix from existing assets (`.opencode/agents/*.md`, `.opencode/skills/*/SKILL.md`) to avoid unsupported agent/skill/tool combinations.
- [x] **Next - draft SKILL.md v1**: Write trigger-rich frontmatter and routing workflow only (classify -> map -> dispatch).
- [x] **Next - add references**: Create `references/routing-taxonomy.md`, `references/capability-matrix.md`, `references/delegation-templates.md`, `references/source-priority.md`.
- [ ] **Last - decide scripting boundary**: Only add `scripts/validate_route.py` if repeated route-linting is needed; otherwise keep v1 scriptless.
- [ ] **Last - dry-run tests**: Run 6 scenario prompts (2 clear, 2 ambiguous, 2 edge cases) and verify route correctness against Goal.


# Reading & Provocation
***

## Reading

### Source-grounded notes
- Reviewed agents: `.opencode/agents/primary/daily-agent.md`, `.opencode/agents/primary/daily-planner.md`, `.opencode/agents/primary/daily-thinker.md`, `.opencode/agents/subagent/context-engineer.md`, `.opencode/agents/subagent/daily-subagent.md`, `.opencode/agents/subagent/KG-updater.md`.
- Reviewed skills: `.opencode/skills/*/SKILL.md` including `skill-creator`, `thinking-models`, `research`, `reference-find`, `notion-use`, `playwriter`, `pptx`, `translation-en-ko`, `visual-explainer`.
- Pattern found: strongest skills use explicit trigger text in `description`, stepwise workflow, and clear handoff templates.
- Risk found: naming/path drift (`thinking-model` vs `thinking-models`, `.opencode/skill` vs `.opencode/skills`) and inconsistent frontmatter conventions.

### Why script (and when not)
- Script is optional, not default. Use a script only when deterministic validation is repeatedly needed (same checks every run).
- For this skill, `validate_route.py` would prevent malformed delegation payloads (missing done checks, missing fallback, unsupported agent-skill pairs).
- If you prefer lean v1, ship without scripts first and enforce validation via SKILL.md checklist; add script in v2 after failure patterns appear.

### How we will make it (build order)
1. Freeze taxonomy and trigger boundaries.
2. Define one routing decision flow and one delegation payload format.
3. Draft SKILL.md with hard output sections.
4. Add reference files for progressive disclosure.
5. Run scenario tests and tighten edge-case rules.

### SKILL.md draft (v1, workflow-only)
```markdown
---
name: workflow-routing
description: Route user requests into the minimum-sufficient execution workflow by selecting the right subagent, skill set, MCP/tool stack, context sources, and parallelization strategy. Use when requests are ambiguous, multi-step, cross-domain, or need delegation/orchestration instead of direct single-tool execution. Trigger especially for Notion-related work, visualization requests, deep-research requests, and reasoning-heavy tasks that need explicit routing before execution.
---

# Workflow Routing

## Required Behavior
- Classify the user request into one primary route and optional secondary route.
- Prefer minimum-sufficient routing; avoid over-delegation.
- Always output a delegation payload with required fields.
- Resolve unknowns explicitly; do not guess unavailable capabilities.

## Routing Workflow
1. Classify intent
   - Notion-related
   - Visualization
   - Deep Research
   - Thinking/Deliberation
   - Fallback/General Execution
2. Select route resources
   - Subagent(s)
   - Skills
   - MCP/tools
3. Decide execution shape
   - Sequential when outputs depend on prior steps
   - Parallel only for independent workstreams
4. Build delegation payload

## Route Map (v1)
- Notion-related
  - Triggers: Notion, meeting-prep, scrum, legal workflow in Notion context
  - Subagents: context-engineer, daily-subagent
  - Skills: notion-use, playwriter (if browser automation is required)
  - MCP/tools: playwriter (only when site/app interaction is needed)
- Visualization
  - Triggers: any request to explain with diagram/visual artifact
  - Subagents: daily-subagent
  - Skills: visual-explainer
  - MCP/tools: use local templates/references first
- Deep Research
  - Triggers: explicit deep research, evidence synthesis, source-backed recommendations
  - Subagents: context-engineer, daily-subagent
  - Skills: research, reference-find, thinking-models
  - MCP/tools: web search/fetch tools as needed
- Thinking/Deliberation
  - Triggers: strategy framing, ambiguity reduction, decision design
  - Subagents: daily-subagent
  - Skills: thinking-models
  - MCP/tools: local context first

## Delegation Contract
```markdown
### Delegation
- Target Agent: <agent-name>
- Assigned Skills: <skill-1, skill-2>
- Task: <specific user intent in one sentence>
- Context Sources: <paths/urls/ids>
- Done Checks: <1-3 observable checks>
- Fallback: <what to do if blocked>
```

### Build status
- Implemented skill files at `.opencode/skills/workflow-routing/`.
- Packaged successfully to `workflow-routing.skill` using `python3 .opencode/skills/skill-creator/scripts/package_skill.py .opencode/skills/workflow-routing`.
- Remaining work: decide whether to keep v1 scriptless or add route validator in v2.

## References (loaded only when needed)
- `references/routing-taxonomy.md`
  - Trigger vocabulary and route family definitions.
- `references/capability-matrix.md`
  - Valid route combinations: subagent x skill x MCP/tool.
- `references/delegation-templates.md`
  - Ready-to-use delegation payload variants by route.
- `references/source-priority.md`
  - Context source order (local notes/docs first, then external).

## How SKILL.md uses references
- Keep SKILL.md short: only routing flow + route map + delegation contract.
- Put volatile/long lists in `references/*` and point to them by filename in each route step.
- During execution, load only the reference file needed by the selected route.
```


# Annotate & Note-Taking
***


# Closing
***
> `daily-agent` prompt: 


# Footnotes
***
