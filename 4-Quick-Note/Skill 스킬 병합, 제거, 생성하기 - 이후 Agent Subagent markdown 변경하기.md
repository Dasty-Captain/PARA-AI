Modify Skills: 
I'm modifying my agent skills right now in `.opencode/skills/`. Based on below points for improvements, suggest me a plan how you'll modify with an example drafts. The skill should be concise overall, but the workflow and deliverables should be clearly defined.
- [x] (skill)**`reference-find skill`**: what can be improved here? need to find the reference in paragraph and line level precision. It should mention the exact sentence of paragraph supporting the claim. If there's anything more to improve, suggest me. 
- [x] (skill)**`research`**: this should be run through `@context-engineer` subagent, and call `reference-find` skill at the same time. 
***
I just changed the skills `research` and `reference-find`. To make this applied in my workflow, I'll need to modify my `@context-engineer` subagent and primary-agent both `daily-planner` and `daily-agent`. They are all in .opencode/agents/. Suggest me a plan of how you'll modify those. 
- [x] (subagent) When user's task is about do some deep-research, call `@context-engineer` and it should always use the `research` and `reference` skills.
- [x] (primary agent) for both `daily-planner` and `daily-agent` should delegate `@contexth-engineer` subagent with research & reference skill.

Add skills: 
- [ ] Workflow Rounting skill: orchestrating the subagents and skills with the right format to provide. 
- [ ] Notion AI skills: how to use what types of Notion commands are, and how to use those. 
- [ ] Translate skill: English -> Korean skill with anti-LLM pattern. 