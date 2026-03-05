# Initial Thoughts
***
- **Goal**: aCAD projects require massive amounts of "human designer's reasoning trace" for aData reverse-modeling data. We were able to achieve SOTA #1 on extrude-only CAD operation reverse-engineering fields, and we are trying to apply the recipe into all CAD operations(revolve, sweep etc) based on our data, pre-training, and post-training experiences. We prepared 1) data acquiring tool, web-CAD platform that logs designer's reasoning trace on our CAD code tree format 2) cheap, cost-efficient companies where can do reverse-engineering from India and Vietnam. 
- **Done**: Find great strategy with types, fields, strategies, many scenarios of data acquisition plan to apply our BEST recipes from extrude model. 
- **Source/Context**: UniversalContext.md

# TO-DOs
***
- [ ] **First | Dataset blueprint v0 (3,600 human traces)**: freeze bucket targets: `Extrude 1,000`, `Revolve 800`, `Sweep 500`, `Loft 400`, `Boolean/Pattern/Fillet 600`, `Constraint-repair sessions 300`.
- [ ] **First | Extrude transfer set (1,000)**: collect `simple prismatic parts 600` (brackets, plates, enclosures), plus `thin-wall/shell + draft 250`, plus `multi-body extrude + cut chains 150`.
- [ ] **First | Revolve industrial set (800)**: collect `gear/pulley/shaft/bushing classes 500` + `aerospace/auto fluid parts 200` + `medical/electronics precision parts 100`; require native + neutral exports (`STEP`, `Parasolid`, source CAD format).
- [ ] **Next | Sweep/Loft hard-geometry set (900)**: `sweep 500` (pipes, cable paths, impeller passages) + `loft/boundary 400` (aero surfaces, ergonomic handles); enforce guide-curve and continuity labels in trace.
- [ ] **Next | DSL augmentation pipeline**: for each accepted human trace, auto-generate `4-8` DSL perturbations (parameter jitter, operation reorder, failure-repair replay) while preserving manufacturability constraints.
- [ ] **Next | Gold benchmark pack (240 tasks)**: build locked eval with `extrude 60`, `revolve 60`, `sweep 40`, `loft 40`, `boolean/pattern 40`; include hidden anti-cheat tasks and cross-CAD replay checks.
- [ ] **Next | QA gate with hard thresholds**: accept only if `geometry equivalence >= 98%`, `trace replay success >= 95%`, `reasoning field completeness >= 92%`, `schema validity >= 99%`.
- [ ] **Last | Vendor pilot structure (3 lanes x 120 tasks)**: India pod vs Vietnam pod vs managed vendor, same task mix and QA gate; compare by `$ / accepted trace`, rejection causes, and turnaround days.
- [ ] **Last | Cost-risk guardrail**: stop scaling any lane where rework exceeds `25%` or reviewer load exceeds `1 reviewer : 35 traces/day`; pivot mix before contract expansion.
# Reading & Provocation
***
## Reading
- Proposed concrete plan is a **human-first core + DSL expansion** design: start with `3,600` accepted human reasoning traces, then expand each via `4-8x` controlled DSL augmentation.
- Keep extrude as transfer anchor, not majority sink: cap extrude near `28%` of core set so revolve/sweep/loft learning is not underfit.
- Revolve should be treated as first hard-transfer frontier: prioritize shaft/gear/pulley + pressure/fluid geometries because they stress profile quality, axis decisions, and tolerance reasoning.
- Sweep/loft data needs explicit trace fields that many vendors miss: guide-curve choice, section continuity intent (`G0/G1/G2`), and failure-repair rationale; without these, post-training lift is weak.
- Use cross-format outputs per sample (`native CAD`, `STEP`, `Parasolid`) to reduce CAD-tool lock-in and improve downstream parser robustness.
- Enforce benchmark discipline early: a fixed `240-task` gold pack should gate all vendors and all augmentation changes before scale-up.
- Unit economics must be tied to acceptance (`$ / accepted trace`) and reviewer bottleneck, not hourly rate; this aligns with current outsourcing transition context (`https://www.notion.so/3119fe64d759809ca24ffbecc42f1069`).
- Security/IP terms are already available and should be mandatory pilot criteria, not post-selection paperwork (`https://www.notion.so/3059fe64d759816dbdc8dcfb75f66e1b`, `.opencode/UniversalContext.md`).

## Provocation
- **Creativity**: If `3,600` is too small, where do you add the next `+800` first: revolve, loft, or constraint-repair? Decide one and justify by expected model lift.
- **Creativity**: Design one "impossible-to-fake" trace field for each op family (extrude/revolve/sweep/loft) that a real designer can provide but shortcut workers cannot.
- **Critical-thinking**: Which is more dangerous for aCAD: `under-coverage of loft/sweep` or `low-quality reasoning on revolve`? Pick one and define a measurable early warning.
- **Critical-thinking**: At what rejection rate does low-cost vendor pricing become net-loss versus a more expensive, higher-fidelity lane?
- **Memory**: Write the exact 5 transfer invariants from the extrude SOTA recipe that must be encoded in QA checklists for every non-extrude task.
- **Memory**: Which CAD failure patterns (self-intersection, thin-wall collapse, invalid constraints, continuity breaks) appeared most in prior runs, and which bucket addresses each?
- **Meta-cognition**: What assumption are we hiding inside "DSL augmentation will preserve realism," and what falsification test can break it in one week?
- **Meta-cognition**: If research and ops disagree on one metric next month, what governance rule resolves it without slowing dataset throughput?
# Annotate & Note-Taking
***


# Closing
***
> `daily-agent` prompt: 


# Footnotes
***
