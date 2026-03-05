# Initial Thoughts
***
- **Goal**: alpha CAD project is our CAD-native foundation model project that requires massive "human designer's reasoning trace," and we developed web-CAD platform for this. We'll need to conduct a large scale research on which company/university can do this for us with cost-efficiency? We need some AI DATA specialized company that can outsource/crowd-source for large-scale, high quality data(i. e. ScaleAI or selectstar.ai)
- **Done**: Find the best candidates that are cost-efficient including US, Korea, Vietnam, Africa etc. 
- **Source/Context**: Find those by browsing the internet. 

# TO-DOs
***
- [ ] Define the data unit + target volume (e.g., $/accepted trace-minute; 1k/10k/100k sessions) and minimum acceptance metrics (geometry correctness + trace completeness)
- [ ] Freeze the reasoning-trace schema for pilots (required event logs vs event+NL rationale; language; controlled vocabulary)
- [ ] Decide alpha scope boundaries (single part vs assemblies; must-have CAD ops; whether GD&T/tolerances are in-scope)
- [ ] Build a 2-week pilot pack: 30-50 tasks across 3 difficulty tiers + gold tasks + cheating/audit checks + reviewer rubric
- [ ] Shortlist 2 CAD outsourcing firms + 1 data-ops vendor; draft outreach email + vendor questionnaire (tooling, pricing model, QA, security/IP)
- [ ] Run pilots inside the web-CAD platform (mandatory); measure acceptance rate, rework rate, trace fidelity score, throughput, and $/accepted unit
- [ ] Decide scaling model (hybrid default): production vendor + expert reviewers + (optional) university cohort for hard cases


# Reading & Provocation
***
## Reading

What "cost-efficient partner" should mean for aCAD
- Minimize total $/usable reasoning-trace minute (or $/accepted task) while still meeting manufacturing-grade correctness, trace fidelity, IP/security constraints, and predictable throughput.
- Treat cost as labor + QA + management + rework + security overhead (not just headline hourly rate).

Partner archetypes (pick 1 primary + 1 secondary)
1) CAD engineering outsourcing firms (best for real CAD skill)
- Good when: you need parametric discipline and higher first-pass correctness.
- Watch-outs: many optimize for "final CAD output," not rich traces; requires a strict trace schema + instrumented logging in your web-CAD.

2) Data labeling / managed-workforce vendors (best for ops + QA systems)
- Good when: you need dashboards, workforce scaling, compliance posture.
- Watch-outs: often not CAD-native; you may need to supply CAD SMEs + tight gold tasks.

3) Universities / student programs (best for hard-case traces + credibility)
- Good when: you need careful, high-signal traces on difficult tasks and can tolerate semester cadence.
- Watch-outs: contracting overhead + variable quality; best as a supplement, not your only supply.

Shortlist: CAD outsourcing (Vietnam / India / Eastern Europe / Africa)
- Vietnam
  - ETEAMS (product design + mechanical engineering): https://eteams.com.vn
  - Arion Automation (automation machine mechanical design): https://arion-automation.vn
  - Brigen Consulting (2D/3D mechanical drafting/modeling): https://brigenconsulting.com
- India
  - Microdra (public rate card; drafting): https://microdra.com/pricing-of-cad-drafting-services/
  - Tesla Outsourcing Services (multi-discipline outsourcing): https://teslaoutsourcingservices.com
  - Indovance (engineering outsourcing; dedicated resource model): https://indovance.com
  - Tata Technologies (enterprise engineering services): https://www.tatatechnologies.com
- Eastern Europe
  - Astek Poland (engineering outsourcing): https://astek.pl
  - Centerline Romania (3D CAD + engineering services): https://centerline.ro
  - Immertec (mechanical design + drawings): https://immertec.ro
- Africa (South Africa)
  - SA Draughting / SADC Draughting Consultants (offshore CAD services): https://sadraughting.co.za
  - Draftline (mechanical design & draughting + personnel outsourcing): https://draftlinesa.co.za

Shortlist: data vendors (useful if you need compliance + managed QA)
- Scale AI (security posture; 3D sensor-fusion task types, not CAD-native): https://scale.com/security
- iMerit (compliance posture; 3D point cloud + domain experts positioning): https://imerit.net/compliance-and-certifications/
- Sama (in-house workforce + security positioning): https://www.sama.com/data-security-and-trust
- Labelbox (platform + managed services; security posture reference): https://labelbox.com/blog/celebrating-labelboxs-latest-security-advancement-iso-27001-2022-certification/
- Select Star (not an annotation vendor; relevant for dataset governance/lineage): https://www.selectstar.com/security-compliance

Evaluation rubric (use this to compare vendors in 1 spreadsheet)
- Data quality + acceptance rate (30%): spec compliance, constraint correctness, low rework; measurable error taxonomy
- Trace fidelity + instrumentation depth (20%): event-level logs + intermediate states + repairs; not just screen recordings
- Security/IP posture (15%): IP assignment, subcontractor controls, audit rights, deletion SLAs
- CAD domain expertise (15%): can explain constraint failures, parametric modeling conventions, manufacturing checks
- Throughput + scaling (10%): ramp plan (first 100 accepted traces; first 10k), reviewer capacity scales
- Cost transparency (5%): charge per accepted unit, not per attempt; QA/rework included
- Program management (5%): weekly calibration, dashboards, rapid iteration on schema

High-signal unknowns to resolve (these change the "best partner")
- What is the "unit": per-feature trace, per-task trace, or full design session?
- Do you require natural-language rationale, or only interaction logs? In which language(s)?
- Is alpha scope single-part only, or assemblies + mates? Any GD&T/tolerance requirements?
- Are tasks synthetic only, or do they include sensitive customer specs/geometry (on-prem + strict access control)?
- Target weekly throughput + budget ceiling per accepted unit?

Reference excerpts (verbatim)
- Microdra hourly rate card: "2D: USD 10/Hour | 3D: USD 13/Hour" (Microdra Pricing - CAD Drafting Services) https://microdra.com/pricing-of-cad-drafting-services/
- Scale certifications list: "SOC 2 Type II" and "ISO 27001" (Scale - Security at Scale; Certifications and Compliance) https://scale.com/security
- iMerit: "Our SOC 2 Type 2 attestation is a testament to our commitment to enterprise-grade security" (iMerit Compliance and Certifications; SOC 2) https://imerit.net/compliance-and-certifications/
- Sama: "Your Data is Yours - Sama does not share or keep any datasets for training or other purposes, unlike crowdsourced alternatives." (Sama Data Security & Trust) https://www.sama.com/data-security-and-trust
- Select Star: "Select Star will never access your data values or run queries against your data unless explicitly authorized" (Select Star Security & Compliance) https://www.selectstar.com/security-compliance
- Labelbox: "in addition to maintaining our SOC 2 Type 2, Labelbox has successfully attained our ISO 27001:2022 certification." (Labelbox blog, 2023-08-02) https://labelbox.com/blog/celebrating-labelboxs-latest-security-advancement-iso-27001-2022-certification/

Recommended pilot design (default)
- Run 2 parallel pilots: (A) CAD outsourcing shop (Vietnam/India) for production realism, (B) managed-workforce vendor for ops+QA, both inside your web-CAD.
- Gate with gold tasks + trace rubric; pay per accepted unit; require session replay + tamper-resistant logs.

## Provocation

Creativity
- Design 3 "trace products" you could buy: (1) cheap/high-volume, (2) balanced, (3) premium/hard-cases. For each: deliverable + unit price + acceptance test.

Critical-thinking
- Write the top 5 ways your dataset could become unusable (trace too thin, cheating, wrong constraints, IP contamination, reviewer bottleneck). For each: 1 prevention control + 1 detection test.

Memory
- From your aCAD experience: list 10 CAD actions where the reason matters more than the action (constraints choice, feature ordering, tolerance choices, repair strategy, etc.).

Meta-cognition
- Pick 1 metric that should be the single source of truth for "cost-efficiency" (e.g., $/accepted trace-minute) and write exactly how you'd compute it from logs + review outcomes.


## Reading (Round 2: Better sources for cheap GOT-trace production)

Reframed scope (what we are actually buying)
- We are not buying "CAD files"; we are buying *parametric modeling sessions inside our web-CAD* so we can log operations into GOT (GFL Object Tree) as a human reasoning trace.
- Therefore partners must accept: (1) working in a browser CAD tool, (2) trace/operation discipline, (3) pay-per-accepted-unit QA.

Cheap, cost-effective vendor pool with public pricing (India)
- Microdra (India) rate card (lowest friction to pilot)
  - Pricing page explicitly lists: "2D: USD 10/Hour | 3D: USD 13/Hour" https://microdra.com/pricing-of-cad-drafting-services/
  - Strength: already sells drafting/modeling as a service; easy to contract as paid pilot; you can enforce "must use our web-CAD" in SOW.

- IndiaCADworks (India) published hourly rates across CAD domains (good for parametric + mechanical)
  - Pricing page lists mechanical service rates, including: "3D Modeling - starts at $14/hour" and "Drafting (Fabrication/Shop Drawing/Manufacturing Drawing) - starts at $14/hour" https://www.indiacadworks.com/pricing.php
  - Also lists "CAD conversion services are priced, starting at $12 per hour" and explicitly offers "Parametric 3D Modeling" as a service category https://www.indiacadworks.com/pricing.php
  - Strength: clearer rate menu for budgeting; mechanical-oriented options are closer to your GOT objectives than pure AEC drafting.

- URCADServices (India) published low-cost CAD pricing (useful as a "cost floor")
  - Pricing page states: "Our CAD Conversion services start at $7/hour" https://www.urcadservices.com/pricing
  - Same page lists per-hour examples including "3D Modeling .................................  $13" (and additional $15/$16 tiers) https://www.urcadservices.com/pricing
  - Strength: very explicit "low price" positioning; good for high-volume, simpler tasks if your QA is strong.

- A R Digitech (India) pricing model transparency (rates not posted)
  - Pricing page describes billing models (fixed cost vs agreed hourly) and rework policy (no-charge for their mistakes; hourly for scope changes) https://ardigitech.com/pricing.php
  - Strength: if you need predictable rework rules; weakness: no public hourly rate.

Vietnam options that fit "dedicated team" + CAD skills (better than generic crowdsourcing for IP)
- THIENTU BPO (Vietnam) - dedicated offshore CAD designers (AutoCAD/SolidWorks/CATIA)
  - "Vietnam offers a growing pool of CAD professionals skilled in 2D drafting, 3D modeling, and engineering design software like AutoCAD, SolidWorks, and CATIA." https://thientu.vn/blog/hire-cad-designers-in-vietnam
  - Same page includes salary bands (USD/month) for "Junior CAD Designer" and more (their estimates) https://thientu.vn/blog/hire-cad-designers-in-vietnam
  - Company site states ISO certifications and onboarding speed: "ISO 9001:2015 and ISO/IEC 27001:2022" and "typically onboarded within 7-14 days" https://thientu.vn/
  - Strength: easiest way to stand up a controlled "crowd" (dedicated team) while keeping IP/security tighter than open marketplaces.

- Arion Automation Vietnam (Hanoi) - mechanical design outsourcing
  - Positions itself as providing "mechanical design outsourcing services" and explicitly targets cost reduction by outsourcing simple tasks https://arion-automation.vn/
  - Strength: mechanical design orientation (closer to parametric CAD) vs pure drafting.

- ETEAMS (Ho Chi Minh City) - mechanical engineering / product development
  - Services include "Mechanical Engineering" for product development https://eteams.com.vn/
  - Strength: can handle harder tasks (but likely higher cost than pure drafting vendors).

- Brigen Consulting (Da Nang) - mechanical drafting + mechanical 3D modeling listed as services
  - Navigation lists "Mechanical 3D Modeling" under Mechanical Drafting services https://brigenconsulting.com/
  - Strength: may be useful for steady drafting throughput; validate depth in parametric feature-based modeling.

Crowd marketplaces (useful, but usually not "cheap")
- Cad Crowd (marketplace + managed QC)
  - Claims global expert pool: "community of 123,457 world-class experts" and lists software coverage incl. SolidWorks, AutoCAD, Inventor, CATIA https://www.cadcrowd.com/how-it-works
  - Pricing guidance on same page: "Hourly design ranges between $50-120/hr" https://www.cadcrowd.com/how-it-works
  - Strength: fast access to breadth + NDA/IP language; weakness: not cost-efficient for volume trace collection.

Practical recommendation (given the new GOT/web-CAD constraint)
- Cheapest stable path is usually not an open crowd platform; it is a dedicated offshore team (Vietnam) or a low-cost India CAD shop with a strict trace+QA contract.
- If you still want "crowd" scaling, the best move is to treat vendors above as your staffing supply and run the crowd inside your own web-CAD task system (gold tasks + audit + pay-per-accepted-unit).

## Provocation (Round 2)

Creativity
- Draft 3 task types you can mass-produce in web-CAD that maximize GOT learning signal: (1) 2D drawing to parametric part, (2) spec sheet to part family with configs, (3) repair session (start from broken GOT and fix).

Critical-thinking
- Define the minimum trace spec that prevents "CAD output without reasoning". Write it as 10 required fields (e.g., fully constrained sketch %, feature naming rules, regen-from-scratch check, and 1-line intent tag per feature group).

Memory
- List the 20 CAD ops you most want in the GOT distribution (extrude/revolve/sweep/loft, fillet, pattern, mirror, boolean, constraints, mates, etc.) and rank them by training value.

Meta-cognition
- If you could only instrument 3 anti-cheating checks in web-CAD, what are they (e.g., replay detection, unusually low interaction entropy, gold-task divergence), and what would each one trigger?


# Annotate & Note-Taking
***
- ==minimum acceptable bar for data==: we have open-source 3D mesh data and evaluate them based on chamfer distance. If 85%+ is identical, we'd like to accept them. 
- 


# Closing
***
> `daily-agent` prompt: 
