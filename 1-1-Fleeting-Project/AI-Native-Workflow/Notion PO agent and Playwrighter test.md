# Initial Thoughts
***
- **Goal**: I made my new workflow-routing skill and notion-use skill and I want to test this. 
- **Done**: give me 3 scenarios of how can I stress-test these skills. 

# TO-DOs
***
- [ ] **First | Test contract**: define a pass/fail matrix for 3 scenarios (happy path, degraded input, blocked environment) with one observable artifact per scenario.
- [ ] **First | Preconditions**: run `playwriter skill`, confirm extension connection, confirm Notion login, and confirm `https://www.notion.so/ai` is reachable.
- [ ] **Next | Scenario 1 (happy path)**: submit one full `PO Task` handoff to Notion AI using real source links and verify concrete output appears in target page/database.
- [ ] **Next | Scenario 2 (input stress)**: rerun with typo (`Playwrighter`) and one missing handoff field, then capture whether routing/agent behavior recovers gracefully.
- [ ] **Next | Scenario 3 (environment stress)**: simulate one blocked condition (extension disconnected or Notion AI unavailable) and verify fail-fast output gives one clear recovery step.
- [ ] **Last | Resolve unknowns**: document what "Notion PO agent" resolves to in practice (chat mode vs agent behavior), plus any selector/UI fragility seen during runs.
- [ ] **Last | Wrap-up**: record a short evidence log (URL/page IDs, what changed, pass/fail per scenario) and list tomorrow's top fix.
# Reading & Provocation
***
## Reading
- `/.opencode/skills/notion-use/SKILL.md`: your local canonical flow is already explicit - route via workflow-routing, then use playwriter to open Notion AI and delegate with a fixed `PO Task` format.
- `/.opencode/skills/playwriter/SKILL.md`: preflight matters more than prompt quality early; test failures often come from extension/tab/auth state, not logic quality.
- `/4-Quick-Note/Read aCAD recent weekly meeting -> Make Notion PO agent to make list of backlogs.md`: best live testbed because it includes realistic meeting-to-backlog conversion targets.
- `/4-Quick-Note/need to make Notion AI skill(with playwrighter MCP) -> add daily planner & agent to call the skill for Notion-related user task.md`: prior notes flag the highest-risk unknowns (PO identity boundary, Notion AI gating, brittle UI automation paths).
- `https://www.notion.com/help/notion-ai-faqs` + `https://playwriter.dev`: useful external ground truth for feature availability and runtime behavior when local assumptions conflict with observed UI.

Draft lens for this test day: treat this as a reliability test, not just a demo. A good run proves (1) deterministic handoff format, (2) robust behavior under degraded inputs, and (3) useful failure messages when prerequisites are broken.

## Provocation
- **Creativity**: What is one "chaos monkey" variant per scenario that could break your flow but still teach you the most in under 10 minutes?
- **Creativity**: If you had to test this with zero UI clicks (keyboard-first), what would you redesign in the handoff and verification steps?
- **Critical-thinking**: What exact evidence would make you conclude "workflow-routing works" vs "Notion PO agent works" (separate these claims)?
- **Critical-thinking**: Which failure is most dangerous to ship: silent wrong output, no output, or misleading success message? Pick one and justify in 2 lines.
- **Memory**: List 3 concrete failures you have already seen in similar automation tests and map each to a prevention check before Scenario 1.
- **Meta-cognition**: Where are you over-assuming today (agent identity, Notion AI mode, selector stability)? Write one falsification test for each assumption.
# Annotate & Note-Taking
***


# Closing
***
> `daily-agent` prompt: 


# Footnotes
***
