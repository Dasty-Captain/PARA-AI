<context_company>
**Identity**: The Dimension Company (based in Seoul & Silicon Valley).
**Mission**: Build the "Agentic Palantir for CAD"—a domain-specific CAD agent that automates complex CAD and engineering workflows for Tier-1 manufacturers (Samsung, HD Hyundai).
**Core Value Proposition**:
- Structure unstructured legacy data (2D drawings, 3D CAD files, BOMs) into an AI-native ontology and AI trainable synthetic data.
- Reduce design cycle time by 30x-400x; save 95% of labor costs.
- "Faster, Easier, Cheaper, yet Scalable Mass Production."
</context_company>

<current_projects>
1. **Archion (Strategic Cash Cow)**: AI Interior Designer automating 2D-to-3D modeling, furniture recommendation, and rendering. Target: Series A driver.
2. **HD Hyundai Project ("선실")**: Automated Drawing-to-CAD for shipbuilding equipment (2D → 3D).
3. **2D Drawing -> 3D Parametric CAD**: convert unstructured 2D drawings into parametric 3D CAD model for small parts to large assembly CAD models.
4. **⍺Data/⍺CAD**: Convert an enterprise's legacy, unstructured CAD models into AI-trainable reconstructed code (⍺Data). Use these synthetic datasets for post-training to build a highly accurate, enterprise-specific foundation model, then integrate and deploy the model into the company's services and workflows.
</current_projects>

<key_kpis_2026>
**1. Company OKR 2026**
- **North Star**: $6.5M ARR ($540K MRR) by Year-End; $200M Valuation.
- **Theme**: Preparing rapid expansions (Product & Technology readiness).
- **Adoption**: Secure 15-20 Enterprise Customers (Tier-1 OEMs).
- **Performance**: 98% Geometrical Accuracy, ≥60% Design Cycle Time Reduction.
**2. Quarterly Key Results**
- **Q1 (Foundation)**: $60K MRR. Launch 2D→3D Agent & Archion Global. Secure 3 2D -> 3D Pilots (HD, MHI, Volvo).
- **Q2 (Expansion)**: $170K MRR. Launch Simple Parts Module(implementing ⍺Data/⍺CAD). Scale with P&P Advisory(reduce GTM cost with domain-specific consulting firm).
- **Q3 (Dominance)**: $390K MRR. Launch Assembly & PLM Agent. Formalize Autodesk Partnership.
- **Q4 (Scale/Exit)**: $540K MRR ($6.5M ARR). Target $500K+ ACV Deals. Decision: M&A vs Series A.
</key_kpis_2026>

<capabilities_sources>
| Source | Priority | Purpose | Matches |
| :--- | :--- | :--- | :--- |
| **UniversalContext** | **CRITICAL (1)** | Current Status, OKRs, Active Projects, Team Context | `.opencode/UniversalContext.md` |
| **Obsidian** | Secondary (2)| Daily Notes, Research Notes, Zettelkasten | `PARA_Zettel/PARA/` |
| **Notion** | Fallback (3) | Specific task details not in UniversalContext | `notion_retrieve_db` |
| **Knowledge Graph** | Deep (4) | Relationship exploration, complex queries | `membase_search` |
</capabilities_sources>


<notion_sources>
When `UniversalContext.md` lacks the needed detail, use this registry to fetch from Notion (`notion-fetch` by page ID):

| Key | Page ID | Use When |
| :--- | :--- | :--- |
| `okr` | `1a69fe64d759806a8576f8bae78108ae` | Project OKR progress, bottlenecks, risks (PO-managed) |
| `ray-actions` | `2ef9fe64d75980c19c1ce0163eeb7741` | Ray's personal to-dos (filter: assigned to Ray Lee) |
| `bd-backlogs` | `2ca9fe64d75980c6b388c1156cec7afc` | Sprint backlogs from weekly milestones (Ray & Daniel) |
| `bd-tasks` | `1b29fe64d759808fb3b7cf2cea4cf26b` | Individual tasks broken from backlogs |
| `bd-docs` | `1b29fe64d759809999c5ded327025c0d` | Biz dev documents & references; agent writes here |
</notion_sources>

<technical_context updated="2026-02">
<product>
Products: Archion (interior design), Drawing-to-CAD (manufacturing), ⍺Data/⍺CAD (research for CAD data pipeline + foundation model).
</product>

<project id="archion-search">
  <name>Archion Search</name>
  <summary>Interior designer uploads a consultation brief → system returns a curated, coordinated furniture collection matching style/budget/space constraints.</summary>
  <how_it_works>
    1. CPLG (Consultation Parser) extracts structured requirements from raw consultation input.
    2. FCLG (Furniture Combination) queries pgvector furniture embeddings and composes room-level combinations optimizing style coherence, budget, and spatial fit.
    3. ASG (Asset Search Graph) handles individual semantic search: query rewrite → Gemini embedding → pgvector similarity → LLM re-ranking on metadata.
    4. Designer reviews via Room/Category UI; edits processed by FCELG (Combination Edit) which regenerates affected items while maintaining collection coherence.
    5. All pipelines run as LangGraph services called from NestJS backend via LlmService.callLangGraph(). Gemini LLM backbone. Mixpanel tracks selection time KPI (target: 90%+ reduction).
  </how_it_works>
</project>

<project id="archion-canvas">
  <name>Archion Canvas</name>
  <summary>2D DWG floor plan → full 3D interior scene with extruded walls, doors/windows, and auto-populated FF&E from Archion Search.</summary>
  <how_it_works>
    1. DWG parsed → wall polylines, door/window symbols, room boundaries extracted.
    2. Walls extruded to 3D; openings cut for doors/windows. Rooms classified by type.
    3. FCLG generates furniture sets per room; items placed via spatial rules + LLM aesthetic reasoning.
    4. 3D scene renders in-browser (Three.js/WebGL). Gemini for photorealistic previews. Export: Revit/SketchUp.
  </how_it_works>
</project>

<project id="drawing-to-cad">
  <name>Drawing-to-CAD</name>
  <summary>Converts 2D engineering drawings (PDF/DWG/DXF) into precise, editable 3D parametric CAD models (STEP/IGES) using a LangGraph + MCP agentic pipeline with verification and self-correction loops.</summary>
  <how_it_works>
    Built as an agentic architecture where specialized agents collaborate, loop, and self-correct:

    1. **Drawing Analyzer**: VLM (OpenAI o3) visually reasons over the 2D drawing — identifies views (front/side/top/section), recognizes geometric primitives, reads dimensions/tolerances/materials, and infers the 3D shape that would produce these 2D projections.
    2. **Structure Document**: Converts analysis into a structured spec — dimensions with tolerances, material properties, geometric relationships, feature hierarchy, manufacturing constraints.
    3. **GFL Code Agent**: Generates GFL (Geometric Figure Library) code from the spec. GFL is Dimension's CAD-native DSL (600+ tokens for B-spline, extrude, revolve, fillet, boolean, constraints, GD&T). Code constructs a GFL Object Tree (GOT) — executed by OCC kernel to produce B-rep solid → STEP/IGES export. All dimensions are parametric variables.
    4. **Visual Verifier**: Renders the generated 3D from multiple viewpoints, computes tri-view IoU and Chamfer Distance against expected geometry. If below threshold, feeds specific error context back to the Code Agent — not just "wrong" but "what is geometrically wrong and where."
    5. **Code Editor (Repair Loop)**: On verification failure or GFL runtime errors, receives the failed code + error location in the GOT (node path, parent context) + visual diff. Generates targeted fixes to specific GOT nodes rather than regenerating from scratch. Loop repeats until passing or retry limit.

    Current state (agent v0): 70% of successful generations achieve IoU ≤ 0.05. 30% exceed retry limits — agent identifies errors but struggles with fixes. Coder improvement is active focus.
    Enterprise: HD Hyundai cabin conversion (1 week → 10 min). MHI 3-5 licenses confirmed.
  </how_it_works>
  <variant name="DN Automotive 3D→2D">Reverse pipeline: 3D models → compliant 2D drawings via NX/DWG/PLM MCP tools.</variant>
</project>

<project id="adata-acad">
  <name>⍺Data / ⍺CAD</name>
  <summary>⍺Data transforms legacy/proprietary/unstructured 3D CAD into normalized, augmentable training data. ⍺CAD is the foundation model post-trained on this data for CAD generation with manufacturing-grade precision.</summary>
  <how_it_works>
    **⍺Data Pipeline:**
    1. Legacy CAD files (STEP/IGES/proprietary) parsed via OCC → B-rep geometry, feature trees, metadata extracted.
    2. Reconstructed into GOT (GFL Object Tree) — the canonical code-based representation. This is the key transformation: opaque binary CAD → structured, trainable code sequences.
    3. Because GOT is code, it's inherently augmentable — vary parameters, add/remove features, re-execute for valid geometric variants. Cost: ~$0.03/generation vs. manual collection.
    4. Ontology built from enterprise sources (Excel, PDFs, design patterns, CAD codes) via Graph RAG. Accuracy jumped 80-85% → 90-95% after knowledge graph integration.

    **⍺CAD Foundation Model:**
    1. Pre-train on large-scale public 3D/multimodal data.
    2. Post-train on ⍺Data output: SFT on GOT sequences for enterprise part families + GRPO/ORPO RL for manufacturing constraint alignment + GFlowNet for solution diversity.
    3. Result: CAD-native model (3B params, target 10B) understanding geometry, constraints, tolerances, manufacturability. Current: IoU 78% (target 92%), CAD Coder Benchmark 52% (target 67% SOTA). GFL rendering unified across all training pipelines.

    Data flywheel: enterprise customers + university MoUs (KAIST, MIT, Stanford, Texas A&M) expand training coverage.
  </how_it_works>
</project>

<shared_patterns>
  GFL as universal CAD representation. pgvector for embeddings. LangGraph for orchestration. Next.js/TypeScript frontends. Python AI backends (FastAPI / LangGraph CLI). Deploys as SaaS + On-Premise + Plugin (SolidWorks, Siemens NX, AVEVA, Autodesk, PTC Creo, Dassault CATIA).
</shared_patterns>
</technical_context>

<business_context updated="2026-02">
**Funding**: ~$4M raised to date, accumulated across equity rounds and government grants. Preparing for Series A with a target $200M valuation by year-end 2026, contingent on hitting $6.5M ARR ($540K MRR).
**Team**: Founded by alumni of KAIST and Seoul National University. Core engineering team comprises 3D AI researchers who have shipped production systems across 3D game engines (real-time rendering, geometry processing) and enterprise CAD/PLM platforms. Multiple team members are International Olympiad of Informatics (IOI) Gold medalists and South Korean national team representatives, bringing world-class algorithmic and systems engineering depth. The combination of competitive programming rigor and domain-specific 3D/CAD expertise is rare globally and central to Dimension's ability to solve manufacturing-grade geometry problems that general-purpose AI labs cannot.
**Customers & Pipeline**: Three Tier-1 enterprise customers are signed and in production or deployment: Samsung Electronics, HD Hyundai Shipbuilding (automated cabin drawing-to-CAD conversion — reduced turnaround from 1 week to 10 minutes), and Mitsubishi Heavy Industries (3-5 licenses confirmed). Active sales conversations are underway with Volvo and HP. Customer profile skews toward large manufacturers with massive legacy 2D drawing libraries who need scalable, automated 3D conversion — shipbuilding, automotive, heavy industry, and electronics. Total addressable market sits within the ~$15B+ global CAD/PLM software market.
**Go-to-Market & Expansion**: Dimension's GTM follows a "prove in Asia, scale globally" playbook. The company first landed Tier-1 enterprises in South Korea and Japan — markets where relationships, on-prem requirements, and domain credibility matter — then is expanding into the United States and Europe with structured ABM and 14-day cold outreach sequences targeting Tier-1 accounts. GTM cost is further reduced through the P&P Advisory partnership (domain-specific consulting channel with existing manufacturer relationships) and a planned Autodesk partnership (App Store distribution + joint research, formalization targeted Q3 2026). Unlike CAD AI startups in Silicon Valley that remain in pilot or demo stages with SMBs and developer audiences, Dimension already has production-grade deployments generating revenue at Tier-1 global manufacturers.
**Moats & Competitive Positioning**: Four reinforcing moats differentiate Dimension from SV-based CAD AI competitors (Zoo/KittyCAD, Onshape AI, etc.) who focus on developer copilots or parametric assistance. First, the proprietary GFL (Geometric Figure Library) DSL with 600+ tokens serves as a universal intermediate representation across all products — it is both the execution format and the training target. Second, the ⍺Data pipeline is the only scalable path from legacy/proprietary CAD files to normalized, augmentable synthetic training data at ~$0.03 per generation versus prohibitive manual collection costs. Third, production deployments at three Tier-1 manufacturers provide real-world validation and continuous feedback that no competitor can replicate without years of enterprise relationship building. Fourth, a growing data flywheel fueled by enterprise customer data and university MoU partnerships (KAIST, MIT, Stanford, Texas A&M) continuously expands training coverage across part families, industries, and CAD conventions.
</business_context>