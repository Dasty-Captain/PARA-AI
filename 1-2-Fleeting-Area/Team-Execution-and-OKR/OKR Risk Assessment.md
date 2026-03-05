# Initial Thoughts
***
- Goal: Assess risk based on current OKR and find what to improve. 
- Done: co-planning until I said finished. 
- Source/Context: Notion OKR page

# TO-DOs
***

- [ ] Pull the current OKR scope: Q1 2026 company objective + linked team KRs; list owners/DRIs
- [ ] Define “risk” rubric for this review (Impact x Likelihood x Detectability) + red/yellow/green thresholds
- [ ] Resolve the biggest unknowns (tracking freshness): current MRR/cash-in today, KR definitions, last-updated dates
- [ ] Gap check each KR (Current vs Target vs time left) and write the 3–5 highest-leverage risks + leading indicators
- [ ] Stress-test mitigations (what changes this week): resourcing/priority swaps, scope cuts, metric definition, customer commitments
- [ ] Produce improvement plan: top bets, owners, next 7-day actions, and re-check cadence

**Unknown-Resolution Sprint (First -> Next -> Last)**
- [ ] First: Build account-level revenue truth table (signed / legal / verbal / none) with expected cash-in date and confidence per customer
- [ ] First: Audit KR freshness (last update timestamp + owner) and mark any KR stale for >7 days as red
- [ ] Next: Validate metric definitions (Current/Goal/Progress formula + unit) across company objective and team KRs
- [ ] Next: Map dependency-critical path (customer-gated vs internally controllable milestones) and tag this-week controllables
- [ ] Last: Run sensitivity test (lose one top account or slip one key milestone) and record breakpoints + fallback levers

**MECE Fundraising Diligence Sprint**
- [ ] First: Build investor MECE scorecard (Market, Product/Moat, Traction, GTM, Unit Economics, Team, Diligence) with pass/fail evidence links
- [ ] First: Reconcile revenue bridge (booked/contracted/forecast) to account-level source records
- [ ] Next: Define pilot-to-paid conversion criteria per account and mark proof status
- [ ] Next: Validate 18-24 month base/upside/downside assumptions (runway, burn, margin) with current project data
- [ ] Last: Publish top 3 fundraising ambiguity risks with DRI, due date, and next validation test

# Reading & Provocation
***

## Reading
- Primary sources found in Notion:
  - OKR hub (index + embeds): https://www.notion.so/1a69fe64d759806a8576f8bae78108ae
  - Company objectives DB: https://www.notion.so/1a69fe64d75980eeba15c99b3e45d46a
  - Team goals/KRs DB: https://www.notion.so/1a69fe64d7598077af78c934c53664c7
- Current company objective appears to be Q1 2026 (Jan-Mar): ==monthly revenue 60,000,000 KRW== + fundraising, with explicit KR targets (MRR 0->60M KRW; fundraising prep->seed) and a written risk register + mitigations:
  - https://www.notion.so/2b89fe64d759804da29fe338b0033494
- Progress signal quality is mixed: ==some team KRs have quantified progress== (e.g., a delivery KR at 54% vs 80% target by Feb end), ==while several revenue/fundraising KRs show 0/blank “Current”== values (tracking freshness is itself a material risk)
- Adjacent strategy context to sanity-check timelines and definitions:
  - https://www.notion.so/3029fe64d759803e9799c4a16c99bf76

Best-available lens for risk assessment (until numbers are refreshed): treat unknown/blank current as high uncertainty; prioritize resolving measurement + leading indicators first, then execution risks.

Missing sources most worth fetching next (to make this decision-grade):
- Single source of truth for revenue/MRR numbers (dashboard/report) + owner
- Fundraising pipeline artifact (CRM / investor list / scheduled meetings) + clear “done” definition
- Customer commitments for pilots/contracts (signed vs verbal) + acceptance criteria tied to technical KRs
- Resourcing/priorities (who is on Canvas vs D2G vs other milestones) to validate schedule realism

### OKR Risk Page + Unknowns Expansion (added)

- Located OKR hub/index page: https://www.notion.so/1a69fe64d759806a8576f8bae78108ae
- Located direct risk-assessment candidate page (contains explicit risk/mitigation section): https://www.notion.so/2b89fe64d759804da29fe338b0033494

Key unknowns to check next (decision-impacting and testable):
- Revenue certainty gap: contracted ARR/MRR vs expected pipeline by account (test: signed docs + invoice readiness + target close date)
- KR metric integrity gap: whether formula/unit definitions are consistent across objective and team KRs (test: metric dictionary pass/fail audit)
- Timeline realism gap: whether current staffing can meet Canvas/D2G milestones (test: owner load map + critical-path validation)
- External dependency gap: which milestones are blocked by customer kickoff/legal timing (test: dependency register with unblock dates)
- Fundraising evidence gap: objective readiness signals beyond "prep" (test: investor stage pipeline + meetings scheduled/completed)
- Pilot conversion gap: explicit acceptance criteria for paid conversion per account (test: checklist with owner/date)
- Technical KPI sufficiency gap: whether current quality metrics predict pilot acceptance (test: correlation between benchmark and pilot outcomes)
- Concentration risk gap: impact of losing one major account (test: one-account-out sensitivity model)
- Mitigation accountability gap: whether every top risk has one DRI and due date (test: risk register completeness check)

## Provocation
- Creativity: If you had to hit the same objective with 50% fewer engineering hours, what 3 scope cuts would you make and what 3 leading indicators would you track daily?
- Critical-thinking: Which single assumption, if false, collapses the entire Q1 plan? Write it as a falsifiable statement and design the smallest test.
- Memory: List the last 2–3 OKRs that were stopped/reset; what early warning signs were present before the reset?
- Meta-cognition: Where are you most likely overconfident (revenue, schedule, model quality, fundraising)? Assign a confidence % and name the evidence you’re missing.

### MECE Ambiguity Expansion (Revenue/Technology/Fundraising)

- Revenue
  - Contract certainty ambiguity: signed vs verbal pipeline, close-date slippage, legal/procurement lag
  - Revenue quality ambiguity: ACV/MRR mix, pilot-to-paid conversion quality, concentration on top accounts
  - Cash timing ambiguity: invoice readiness, collection cycle, dependency on customer fiscal windows
- Technology
  - Performance ambiguity: benchmark gap vs customer acceptance threshold (IoU/Chamfer/accuracy)
  - Reliability ambiguity: regression frequency, reproducibility, retry/failure behavior in production flows
  - Integration ambiguity: CAD toolchain compatibility, deployment stability, environment-specific edge cases
- Product/Delivery
  - Scope ambiguity: must-have vs nice-to-have for Q1 completion
  - Throughput ambiguity: owner bandwidth, context switching, unresolved dependency chain
  - Acceptance ambiguity: explicit UAT criteria and sign-off owner/date by account
- GTM
  - Pipeline ambiguity: stage progression velocity, loss reasons, deal quality variance
  - Execution ambiguity: champion strength, procurement mapping, account plan depth
  - Expansion ambiguity: module-pricing upsell path and copy-volume assumptions
- Fundraising
  - Narrative ambiguity: why-now, problem urgency, wedge strength, moat defensibility
  - Traction ambiguity: KPI consistency, evidence quality, repeatability of growth
  - Process ambiguity: investor coverage, stage conversion, diligence readiness
- Team/Execution
  - Ownership ambiguity: one DRI per KR/risk and clear decision rights
  - Capacity ambiguity: staffing vs critical milestones and hidden overtime assumptions
  - Cadence ambiguity: weekly review quality and mitigation follow-through
- External/Regulatory
  - Customer blocker ambiguity: legal/security/vendor onboarding delays
  - Market ambiguity: budget freeze, competitor discounting, timing mismatch
  - Compliance/IP ambiguity: data rights, model usage boundaries, contractual liability exposure
- Data/Measurement
  - Metric ambiguity: formula/unit mismatch across objective/KR layers
  - Freshness ambiguity: stale current values and delayed reporting
  - Attribution ambiguity: unclear link between actions and metric movement

### MECE for Fundraising (Investor Diligence Lens)

- Market + Problem
  - Test: ICP pain quantified with evidence from at least 5 customer conversations/deals
  - Test: TAM/SAM/SOM assumptions reconcile with bottom-up pipeline math
- Product + Moat
  - Test: side-by-side competitor scorecard with objective differentiation proof
  - Test: defensibility evidence (data flywheel, IP, integration stickiness) mapped to customer value
- Traction + Revenue Quality
  - Test: revenue bridge (booked/contracted/forecast) reconciles with source records
  - Test: pilot-to-paid conversion criteria and outcomes are measurable per account
- GTM Repeatability
  - Test: conversion benchmarks by stage/segment with known bottlenecks
  - Test: repeatable motion assumptions (CAC/payback/sales cycle) tied to owner and current evidence
- Unit Economics + Financial Plan
  - Test: base/upside/downside 18-24 month plan with explicit run-rate and burn assumptions
  - Test: gross margin and delivery-cost assumptions validated against recent projects
- Team + Governance
  - Test: top execution gaps mapped to hiring/ownership plan with dates
  - Test: decision cadence and governance model are explicit for fast correction
- Process + Diligence Readiness
  - Test: data room completeness checklist (legal/finance/tech/commercial) with accountable owner per folder
  - Test: investor pipeline tiering (A/B/C), warm intro path, and weekly stage-conversion tracking

# Annotate & Note-Taking
***
- **Main Logic**: It's NOT all about revenue, but the mixture of technology, product, customers, situation, timing, context(why it's important) etc. 
	- **Revenue**: $30K+/month: HD Hyundai $10K + Archion $10K + DN Automoitive $30K + LIG $30K + Mitsubishi $1K
	- **Multiple**: 30x-40x 
	- **Research**: SOTA, Global #1 for VIoU & Chamfer Distance
	- **GTM**: Already acquired 5+ tier-1 and 1 tier-2 manufacturers, and will be able to expand the "module" based pricing for massive upsell, starting from small # of license copies. 
- Is the revenue "**really**" achievable?
	- YES. BUT NEED ACTUAL CONTRACT UNTIL THAT TIME. 
		- **Samsung Electronics**: Maybe NOT. 1/5
		- **HD Hyundai**: $10K, 5/5 already got it. 
		- **Archion**: $10K? 3/5 C. S. 
		- **Mitsubishi Heavy Industries**: $1K/month, 5/5. YES. 
		- **LIG**: $25K/month, maybe contract 3/5 (2D -> 3D & 3D -> 2D)
		- **DN Automotive**: $30K/month, maybe contract, 4/5
- **Is the Biz Dev KR right? Can this be qualitatively evaluated?** 
	- NO. Need to change: 
		- **Should set up the numbers for: aCAD data-pipeline** 
		- **fundraising & grant**: $3M -> GPU(need to evaluate how much we'll get based on this)
- Prioritize and define what "**we really need for fundraising**"
	- need to prioritize ALL projects
- Ambiguity
	- **Revenue: can we get the contract until that time?** 
		- Archion Search: $10K/month -> Mid of March
		- DN: $30K/month -> Mid of March
		- LIG: $30K/month -> Mid of March
		- Mitsubishi Heavy Industries: $12K/month -> Early March
		- HD Hyundai: N/A -> Mid of March
		- Samsung Eletronics: N/A -> Early March
		- Volvo: N/A -> should contact again 
		- HP: N/A -> should contact again 
		- Sony: N/A -> should contact again
	- **Tech & Product: can we really achieve the benchmark we setup? Pretty confident.** 
		- Archion: YES(Canvas maybe)
		- aCAD: YES
		- D2C: Maybe
		- C2D: YES


# Closing
***
> `daily-agent` prompt: 
