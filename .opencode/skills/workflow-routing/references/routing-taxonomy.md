# Routing Taxonomy

## Primary Route Families

### 1) Notion-related
- Match terms: notion, database, page, meeting notes, scrum board, legal tracker, workspace docs.
- Route when the core object is a Notion page/database/process.

### 2) Visualization
- Match terms: visualize, diagram, chart, architecture visual, explain visually, infographic.
- Route when output quality depends on visual communication.

### 3) Deep Research
- Match terms: deep research, evidence, sources, references, compare papers, benchmark, market scan.
- Route when confidence requires source triangulation.

### 4) Thinking
- Match terms: think through, frame, decompose, tradeoff, decide, uncertainty, hypothesis.
- Route when decision framing is primary.

### 5) Fallback
- Use when no family is clearly dominant.
- Gather minimum clarifying context, then reclassify.

## Tie-break Rule

- If Notion object is primary, choose Notion-related even if research/thinking is also present.
- If user explicitly asks for visual output, choose Visualization as primary.
- If user requests source-backed recommendation, choose Deep Research as primary.
- If user asks for framing before action, choose Thinking as primary.
