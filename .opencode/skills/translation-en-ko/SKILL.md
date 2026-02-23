---
name: translation-en-ko
description: Translate English to Korean, then apply anti-LLM naturalization while preserving meaning and formatting.
---

# English to Korean Translation

Use this skill when the user wants English text translated into Korean with natural wording.

## Required Behavior

- Follow this fixed workflow order:
  1. Just translate it.
  2. Apply anti-LLM patterns to make it more natural and human-like.
- Keep meaning, intent, certainty level, numbers, and constraints unchanged.
- Preserve formatting unless the user asks for a different format.

## Required Inputs

- Source text in English.
- Target audience or tone if the user specifies one.

If tone is missing, default to clear, natural Korean suitable for technical readers.

## Workflow

1. Translate the source text to Korean directly.
2. Run an anti-LLM pass on the Korean draft:
   - Reduce translationese and rigid AI cadence.
   - Prefer direct Korean over corporate or over-formal phrasing when appropriate.
   - Remove unnecessary transition filler and repetitive structure.
   - Keep the original message intact.
3. Validate output fidelity and formatting:
   - Do not change facts, emphasis, or scope.
   - Keep markdown structure, links, code blocks, inline code, placeholders, file paths, and commands unchanged.

## Output Format

Return in this exact section order:

1. Korean Translation
2. Notes (only if needed for ambiguous terms)

## Guardrails

- Do not add new claims, examples, or opinions not present in the source.
- Do not translate content inside code fences or inline code unless explicitly requested.
- Do not alter URLs, placeholders, IDs, or command syntax.
- Ask a single clarification question only when ambiguity materially changes meaning.
