# Capability Matrix

| Route | Subagents | Skills | MCP/Tools |
|---|---|---|---|
| Notion-related | context-engineer, daily-subagent | notion-use, playwriter (conditional) | notion tools first; playwriter only for UI-gated actions |
| Visualization | daily-subagent | visual-explainer | local templates/references |
| Deep Research | context-engineer, daily-subagent | research, reference-find, thinking-models | local sources first, then web search/fetch |
| Thinking | daily-subagent | thinking-models | local notes/repo context |
| Fallback | daily-subagent | none initially | gather missing context, then reroute |

## Combination Notes

- Do not assign playwriter unless browser/UI interaction is required.
- For Deep Research, include both `research` and `reference-find` when external evidence is needed.
- For Notion-related tasks, include `context-engineer` when source discovery is incomplete.
