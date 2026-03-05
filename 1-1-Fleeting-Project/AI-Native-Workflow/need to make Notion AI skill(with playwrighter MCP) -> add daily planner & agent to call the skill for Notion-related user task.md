# Initial Thoughts
***
- **Goal**: This is to make a "notion-use" agent skill that follows these steps: Call the "skill-creator" skill to do this job. Query below with "skill-creator" skill. 
	1. **trigger**: user request about something has to be done in Notion or Notion-related tasks including meeting-prep, scrum management(backlogs, tasks etc), or some document jobs that has to be shared to the teams. 
	2. **MUST ITEM**: Call both "playwriter" MCP AND it has its own agent skill "playwriter". 
	3. **MUST ITEM**: Open Notion -> click "Notion AI" on the sidebar -> (automatically) PO agent pops up -> delegate the task to PO agent with clear and correct format
	4. Let user knows and inform to check opened Notion AI page.
- **Done**: 1-3 observable acceptance checks
	- Should use skill-creator skill
	- should make great skill with above workflow
	- should include above items, so I can test it out. 
- **Source/Context**: only required links/paths/IDs
	- Browse the internet about OpenCode skill format(YAML etc)

# TO-DOs
***
- [ ] **First — lock skill contract**: set `name`/`description` trigger language for Notion tasks (meeting prep, scrum/backlog, shared docs) and define 2-3 non-trigger cases.
- [ ] **First — harden must-items**: encode mandatory dual call (`playwriter` skill + playwriter MCP) as non-optional preflight.
- [ ] **First — fix PO handoff schema**: finalize PO agent target, payload format, and success acknowledgment format.
- [ ] **Next — build SKILL.md workflow**: Preflight -> Open Notion -> Enter Notion AI -> Delegate to PO agent -> Notify user to verify opened page.
- [ ] **Next — add fallback logic**: use sidebar click first, then keyboard shortcut path when Notion AI label/position changes.
- [ ] **Next — add verification gates**: require observe -> act -> observe after every browser action and fail fast on auth/extension errors.
- [ ] **Last — package-ready checklist**: run quick validation and define manual tests for happy path, login wall, and Notion AI unavailable.
- [ ] **Last — ship draft artifact**: keep one ready-to-copy SKILL.md draft in the lowest section for immediate iteration.
# Reading & Provocation
***
## Reading
- **Loaded source of truth:** `.opencode/skills/skill-creator/SKILL.md` says keep SKILL body lean, put trigger conditions in frontmatter `description`, and use deterministic workflow when fragility is high.
- **Workflow pattern source:** `.opencode/skills/skill-creator/references/workflows.md` supports strict sequence + conditional fallback design for UI automation tasks.
- **Execution constraint source:** `.opencode/skills/playwriter/SKILL.md` and `playwriter skill` require operational discipline (own page/session checks, observe->act->observe, popup/tab caveats).
- **Delegation pattern source:** `.opencode/agents/primary/daily-agent.md` gives the right style for structured handoff prompts to downstream agents.
- **External cross-checks:** https://docs.anthropic.com/en/docs/claude-code/skills (skill frontmatter and trigger behavior), https://www.notion.com/help/notion-ai-faqs (Notion AI entry and availability assumptions), https://playwright.dev/docs/chrome-extensions (automation constraints for browser extension contexts).
- **Drafted approach:** design `notion-use` as a low-freedom procedure skill: explicit trigger scope, mandatory dual-call preflight, deterministic UI path, fixed PO delegation template, explicit final user notification.
- **Best available missing context:** PO agent identifier + payload schema is still the highest-risk unknown; solve this before final packaging.

## Provocation
- **Creativity:** Produce 2 alternate delegation templates (compact vs explicit) and choose one based on error-prevention, not style preference.
- **Critical-thinking:** Write the single highest-impact failure mode and the exact first recovery action in one sentence each.
- **Memory:** List the 5 playwriter rules you must never violate while opening Notion AI.
- **Meta-cognition:** State your strongest assumption about PO agent availability, and define a 2-minute test to disprove it.
- **Decision test:** Decide now: `manual-only` or `auto` invocation; give one measurable trigger for revisiting that decision.
# Annotate & Note-Taking
***


# Closing
***
> `daily-agent` prompt: 


# Footnotes
***

```markdown
---
name: notion-use
description: Automate Notion-related execution requests including meeting prep, scrum backlog/task management, and shared team document work. Use when user asks to do work in Notion or delegate Notion operations to an internal PO agent. Mandatory workflow: load playwriter skill, use playwriter MCP to open Notion, enter Notion AI, delegate with fixed PO handoff format, then notify user to verify the opened Notion AI page.
---

# Notion Use Skill

Follow this deterministic workflow exactly.

## 0) Mandatory preflight
1. Load the `playwriter` skill.
2. Load the `playwriter` MCP, and verify playwriter extension connectivity and page control readiness.
3. If extension/session is not ready, stop and return one actionable recovery step.

## 1) Open Notion and enter Notion AI
1. Open `https://www.notion.so`.
2. Confirm user is authenticated; if not authenticated, stop and ask user to complete login.
3. Primary path: click `Notion AI` in sidebar.
4. Fallback path: use Notion AI shortcut if sidebar path is unavailable.
5. After each action, verify page state before continuing.

## 2) Delegate to PO agent
Use this exact handoff format:

`PO Task`
- Goal: <one-sentence objective>
- Scope: <what to include/exclude>
- Context/Sources: <links/IDs/context>
- Done Checks: <1-3 observable outputs>

If required fields are missing, request only the minimum missing values.

## Fail-fast rules
- Do not continue when extension is disconnected.
- Do not continue when Notion authentication blocks access.
- Do not invent PO agent identifiers or payload fields.
```
