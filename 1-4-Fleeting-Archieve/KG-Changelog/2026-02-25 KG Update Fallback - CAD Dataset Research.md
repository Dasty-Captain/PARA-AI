# KG Update Fallback - CAD Dataset Research (2026-02-25)

## Decisions
- Routed request as deep research (open-source CAD datasets + aCAD strategy).
- Delegated a research-grade PO Task to Notion AI with strict done checks.
- Adopted provisional 3-tier data strategy: permissive open pretraining, non-commercial benchmark quarantine, proprietary trace moat.

## New Facts
- ABC: large B-Rep-centric corpus; rights context nuanced.
- SketchGraphs: 15M sketch constraints; limited for full enterprise manufacturing reasoning.
- Fusion 360 Gallery datasets: high quality but explicitly non-commercial research use.
- PartNet/ShapeNet and Onshape-derived sources require careful legal interpretation for commercial training.
- Biggest market gap: enterprise-safe CAD reasoning traces and manufacturability intent are scarce in open data.

## Open Questions
- Commercial legal posture for Onshape-derived public-document datasets.
- First wedge segment for aCAD with best KPI lift.
- Best partner model to optimize $/accepted trace-minute.

## Status
- Context-engineered market map produced.
- Notion AI prompt submitted; generation in progress.
- Memory write API (`membase_add_memory`) returned HTTP 422, so this note is the durable fallback log.
