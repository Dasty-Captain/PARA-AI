# Initial Thoughts
***
- 
- Goal: To make great alpha CAD backlogs for tracking each research items
- Done: Will iterate until it makes great high-level research backlog items. 
- Source/Context: Notion -> aCAD workspace -> meeting / backlog page 
	- aCAD meeting: https://www.notion.so/2e79fe64d7598072a003e2e14d74b814?v=2ef9fe64d759805a8c25000cc2999848&source=copy_link
	- aCAD backlog: https://www.notion.so/2e79fe64d75980ef8b02e80eebe94d89?v=2ef9fe64d759805a8c25000cc2999848&source=copy_link

# TO-DOs
***
- [x] Read the most recent Weekly Meeting page and list: decisions, action items, and open questions (source: 2026-02-20 Weekly Meeting)
- [ ] Finalize 6 backlog epics (post-training split into 2 approaches; CAD data acquisition merged into 1 epic)
- [ ] Draft 10-20 high-level research backlog items (1-2 lines each) with a concrete "Done when" acceptance check
- [ ] Decide a Notion naming convention and apply consistently (recommended: epics as `[Epic] ...`, items prefixed by epic short-tag)
- [ ] Normalize each backlog item into Notion fields: Priority(P0-3), Status(Not started), Assignee(if known), Due Date(window)
- [ ] Populate the Notion Backlog DB with 6 epics + items (keep the 2 existing in-progress items as-is)
- [ ] Specify the "Notion PO agent" MVP (inputs, extraction rules, output schema, human-review loop, success metric)

# Reading & Provocation
***

## Reading

Sources pulled:
- Notion Meeting DB: `https://www.notion.so/2e79fe64d7598072a003e2e14d74b814?v=2ef9fe64d759805a8c25000cc2999848&source=copy_link`
- Notion Backlog DB: `https://www.notion.so/2e79fe64d75980ef8b02e80eebe94d89?v=2ef9fe64d759805a8c25000cc2999848&source=copy_link`
- Most recent weekly meeting page (2026-02-20): `https://www.notion.so/30d9fe64d7598092a7c1c96955482488`

What the “recent weekly meeting” actually says (signals for high-level backlog):
- Process: after each meeting, everyone writes next-week TODOs into the backlog; keep experiment logs elsewhere and keep backlog simple; group backlog items at a high level together.
- Workstreams called out: mutation data quality + rejection filters; cut-plane/cross-section tooling; post-training experimentation (curriculum, GTPO, verifier/BoN, GFlowNet); eval/reward issues (alignment, projection IoU); CAD op expansion (revolve/sweep/spline) + data sourcing; reasoning-trace collection; GPU/time planning.

Current Notion backlog state (queried board): only 2 “In progress” items exist:
- “curriculum 적용후 테스팅”
- “vision encoder lora 적용 / 비적용 테스팅”
So the immediate need is scaffolding: stable epics + high-level research items so weekly TODOs land consistently.

Final 6 backlog epics (per your note comment):
- Data pipeline & mutation quality
- Cross-section / cut-plane tool + tool-calling setup
- CAD data acquisition (revolve/sweep/spline) + data sourcing + reasoning-trace collection
- Post-Training 1: Evaluation & reward design (IoU/projection IoU, alignment, benchmarks)
- Post-Training 2: GFlowNet based approach
- Experiment loop & project hygiene (curriculum, vision-encoder LoRA tests, verifier/BoN, GTPO, recipes, backlog discipline, timeline/GPU)

Missing sources worth fetching next (to reduce rework):
- Prior 1-2 weekly meeting pages (e.g. 2026-02-13, 2026-02-06) for continuity of decisions and owner mapping.
- Action Items DB linked from the 2026-02-20 meeting note.

## Provocation

Creativity (generate options, then pick):
- For each of the 6 epics, define 1 north-star metric in 1 line.
- For each epic, draft 3 backlog items in the format: "Verb + object" + "Done when...".

Critical-thinking (force priorities):
- What is the single bottleneck this week: data quality, tool extraction, post-training, eval/reward, or CAD data acquisition? Pick 1 and defend with 2 pieces of evidence from the meeting.
- Define 3 falsifiable hypotheses for the bottleneck you picked; each must have a 1-day test.

Memory (reconstruct the implicit plan):
- From your memory: which 3 decisions from the last 2 weeks are non-negotiable constraints for research direction?

Meta-cognition (design the backlog so it stays useful):
- What would make a backlog item too detailed for this board? Write a 1-sentence rule, then rewrite 2 items to comply.

# Annotate & Note-Taking
***
Finalize these items. It should be 6 backlog epics, and make sure post-training have 2 different approaches and CAD data acquisition is merged to one item.
- Data pipeline & mutation quality
- Cross-section / cut-plane tool + tool-calling setup
- Post-training loop (curriculum / GTPO / verifier / BoN): divide them into two items
	- Post-Training 1: Evaluation & reward design (IoU/projection IoU, alignment, benchmarks)
	- Post-Training 2: GFlowNet based approach
- CAD data acquisition (revolve/sweep/spline) + data sourcing
	- Reasoning-trace data collection (what “trace” means; how we store + train)

# Closing
***
> `daily-agent` prompt:
```text
You are daily-agent. Objective: finalize aCAD high-level backlogs by creating exactly 6 epic scaffolds and 10-20 backlog items in Notion, grounded in the most recent Weekly Meeting.

DELEGATE PLAYWRIGHTER TO MANIPULATE THE BROWSER, AND CALL NOTION PO AGENT(NOTION AI THROUGH WEB) TO DO THE TASK.

Primary sources:
- Meeting DB: https://www.notion.so/2e79fe64d7598072a003e2e14d74b814?v=2ef9fe64d759805a8c25000cc2999848&source=copy_link
- Backlog DB: https://www.notion.so/2e79fe64d75980ef8b02e80eebe94d89?v=2ef9fe64d759805a8c25000cc2999848&source=copy_link
- Weekly Meeting page (2026-02-20): https://www.notion.so/30d9fe64d7598092a7c1c96955482488

Constraints (must follow):
- Exactly 6 backlog epics.
- Post-training split into 2 distinct approaches.
- CAD data acquisition + data sourcing merged into 1 epic.

Step 1) Re-read the 2026-02-20 weekly meeting page and extract:
- Decisions/constraints (process + timeline)
- Action items / TODO themes
- Workstreams and techniques explicitly mentioned (GTPO, verifier/BoN, curriculum, GFlowNet, cut-plane tool, mutation rejection filters, projection IoU, revolve/sweep/spline, reasoning traces)

Step 2) Create 6 epic rows in the Notion Backlog DB.
Default convention: prefix epic rows with `[Epic]`.
Use these epic titles (verbatim):
1. [Epic] Data pipeline & mutation quality
2. [Epic] Cross-section / cut-plane tool + tool-calling setup
3. [Epic] CAD data acquisition (revolve/sweep/spline) + data sourcing + reasoning-trace collection
4. [Epic] Post-Training 1: Evaluation & reward design (IoU/projection IoU, alignment, benchmarks)
5. [Epic] Post-Training 2: GFlowNet based approach

For each epic row:
- Status = Not started (unless clearly already in progress)
- Priority = P1 (adjust to P0/P2 only if clearly urgent/non-urgent)
- Assignee blank unless the meeting explicitly indicates an owner
- In the page body, add: (a) 1-2 sentence scope definition (b) Source link to the meeting page

Step 3) Create 10-20 backlog item rows distributed across the 6 epics.
- Each item title is 1-2 lines and starts with an epic short-tag like: `[Data]`, `[Tool]`, `[CAD]`, `[Eval]`, `[GFlowNet]`, `[Ops]`
- Each item body includes:
  - Done when ... (crisp acceptance check)
  - Source: meeting page link
- Status = Not started
- Priority set by dependency (P0 blockers, P1 core, P2 nice-to-have)

Step 4) Do not disrupt existing in-progress backlog items; keep them as-is and optionally add an epic short-tag + Source in their page body (DB has no Epic relation property).

Step 5) Create one backlog item: `[Ops] Notion PO agent MVP spec` and write the MVP spec in its page body: DELEGATE PLAYWRIGHTER TO MANIPULATE THE BROWSER, AND CALL NOTION PO AGENT(NOTION AI THROUGH WEB) TO DO THE TASK.
- Inputs: which Meeting DB views/pages it reads (start with the Weekly Meeting pages)
- Extraction rules: how it detects decisions, action items, open questions, workstreams
- Output schema: how it writes to Backlog (naming, priority/status defaults, how it embeds Source)
- Human review loop: what a person must approve/edit each week
- Success metric: what “great backlog” means and how to measure it weekly

Deliverable: Backlog DB contains 6 epic rows + 10-20 high-level items, all with "Done when" + Source links.
```
