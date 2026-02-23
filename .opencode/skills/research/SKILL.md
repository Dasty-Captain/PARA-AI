---
name: research
description: Deliver consulting-grade research from a user question through hypothesis, evidence collection, synthesis, and recommendation.
---

# Research

Use this skill for structured, high-confidence research that supports decisions with transparent evidence and tradeoffs.

## Required Behavior

- Start by clarifying the exact research question and decision use case.
- This skill is a parallel analysis worker under `@context-engineer`; it does not orchestrate other skills.
- Build evidence from multiple source types, not a single article or source.
- Distinguish facts, interpretations, and recommendations explicitly.

## Required Inputs

- Research question and intended decision.
- Scope boundaries (timeframe, geography, industry, audience).
- Depth target (quick brief, standard, deep-dive).
- Constraints (deadline, acceptable uncertainty, excluded sources).

If inputs are missing, ask only for the minimum needed values.

## Workflow

1. Receive scope and context packet from `@context-engineer`; produce hypothesis, synthesis, and recommendation stream in parallel with `reference-find` output.
2. Frame the question into sub-questions and testable hypotheses.
3. Build search strategy with keywords, synonyms, and exclusion terms.
4. Collect sources across at least three categories where possible:
   - Primary or official sources
   - High-quality secondary analysis
   - Industry or domain commentary
5. Evaluate source quality (authority, recency, methodology, bias risk).
6. Extract claim-level evidence and reconcile contradictions.
7. Synthesize findings into implications, options, and tradeoffs.
8. Deliver recommendations with confidence levels and caveats.

## Output Format

Return in this exact section order:

1. Research Question and Scope
2. Method and Source Strategy
3. Key Findings (evidence-backed)
4. Contradictions and Uncertainty
5. Recommendations and Tradeoffs
6. Confidence Assessment
7. Sources

## Guardrails

- Do not present unverified claims as facts.
- Cite sources for every material claim.
- Prefer recent and primary sources when stakes are high.
- State uncertainty honestly; avoid false precision.

## Confidence Scale

- High: multiple strong, converging sources with low contradiction.
- Medium: useful evidence with some assumptions or mixed findings.
- Low: limited sources, high disagreement, or weak data quality.
