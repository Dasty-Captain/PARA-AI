---
tags:
  - PKM
  - productivity
---
### **Best References**
***
1. Andreij Karpathy: ex Tesla/OpenAI Head of AI

### **Productivity Tools & Platforms**
***
1. **iPad as diverging thoughts**: Obsidian Excalidraw 
2. **Comet & Perplexity**: General Search, unified workspaces
3. **ChatGPT**: Advanced Report Writing
4. **Obsidian Web Clipper**: sourcing knowledge into zettelkasten
5. **Obsidian**: My second-brain
6. **Agent Manager**: Gemini CLI with MCP([[Best Action-Oriented MCP Servers]])
7. **Notion**: as a collaboration tool(with Notion AI)
8. Etc. Notebook LM, Genspark, Midjourney, Eagle
9. **Raycast**: always on -> Snippet, Raycast notes, AI, Shortcut(Alias)
10. **HW**: 
	- **HHKB Studio**: for frictionless hand-movement -> recently moved to Corne and Keyball 61
	- **Apple Vision Pro**: to utilize fully 

### **knowledge management methodology**
***
- Fleeting Note + PARA: Atomic Note managing with PARA
- Literature Note: Connecting Dots
- Permanent Note: My permanent knowledge 


### **Workflow: The Intelligence Production Line**
***
This workflow transforms raw data into actionable intelligence in a systematic, 7-stage pipeline. It integrates the CRCPA model (Capture, Refine, Connect, Plan, Action) with your action-oriented agents.

1.  **Stage 1: Capture (Data Acquiring Agent)**
    -   **Action**: Create atomic notes from raw inputs (web articles, meeting transcripts, voice notes, ideas).
    -   **Agent**: The `Data Acquiring Agent` semi-automates this, structuring inputs into a standardized note format with proper metadata. 

2. **Stage 2: Refine (Refinement Agent)**
    -   **Action**: Improve the note's content, clarity, and quality based on the questions from the previous stage.
    -   **Agent**: The `Refinement Agent` collaborates with you to polish the language, add examples, and ensure the note is robust and clear. It divides complex concept or massive contents into atomic notes, then place those notes in the right fleeting notes folder. 

3.  **Stage 3: Connect (Knowledge Graph Agent)**
    -   **Action**: Discover and create typed links (e.g., `supports`, `contradicts`, `is_example_of`) between the new note and existing knowledge. IT SHOULD HELP "ME" to find meaning behind the scenes. 
    -   **Agent**: The `Knowledge Graph Agent` (an evolution of the Connecting Dots Agent) uses semantic analysis and graph algorithms to suggest non-obvious connections, building a true ontology.

4.  **Stage 4: Plan (Planner Agent)**
    -   **Action**: Synthesize the fully processed knowledge from the graph to create strategic, actionable plans and step-by-step tasks.
    -   **Agent**: The `Planner Agent` takes the refined, connected insights and, using structured thinking frameworks, determines the best course of action, potentially leveraging `n8n` for workflow design.

5.  **Stage 5: Act (Action Agent)**
    -   **Action**: Execute the planned tasks using available tools.
    -   **Agent**: The `Action Agent` is the "CEO-Staff," using MCP tools for Gmail, Calendar, Slack, and other browser/automation tasks to make things happen in the real world.


### **My Use-Cases**
***
- Lead Gen(Comet) -> Local Interior(via Perplexity/Obsidian MCP) -> Note[[Local Interior Firms Pipeline]] -> Gmail MCP -> Sending Emails and Lead Cold-Outreach


### **My Ultimate Goal**
***
- Self-Evolving Intelligence System & Action Machine(CEO-Staff)
	- Agents get knowledge from external source
	- Agents process the knowledge into the system
	- Agents that plans, and take actions.
	- Agents that learn from its own actions.
	- Finally, agents that improve itself. 
- It can be our side-job
- **Ultimate Scenario**: Setting Monthly KPI -> Plan & Action -> Iterate, improve, make actual tractions.

### TODOs
***
- [ ] Make rules: 
	1. Define specific "**Goal -> Desirable Output Format(report or action)**"
	2. You can't automate what you can't articulate. 
	3. Choose: Top-Down? Bottom-Up? 
	4. Start from dividing a clear task and note
- [ ] Clone PJ's Notion Agent Directions
- [ ] **Find more references**: who's the best here? Who made a best performance using the method? 
- [ ] Find more MCP
- [ ] **Divide the right task to AI**: using AI ONLY when the task is specific enough for you, use AI. Otherthen, it is waste of time, or takes longer time, doing work for work.
***
- [ ] **Fetch Notes**: fetch things from Notion, Gcal, Gmail, Slack etc.
- [ ] **Divide by atoms**: make notes **atomic notes, tagging, cross-linking**. Make agent of them with great rules.
- [ ] **Knowledge‑graph**: Use spaCy or Hugging Face NER models to extract entities and relationships. Build a graph database where nodes represent entities, notes, and topics, and edges represent relationships (e.g., “concept‑mentions” or “influences”). Graph algorithms can then suggest new links.
	- [ ] Need to find a way to leverage knowledge graph. 
	- [ ] Make system for "**Agent on Ontology**"
- [ ] **n8n MCP**: To actually build, great CEO staff, and **need an agent that orchestrates workflows in n8n**.
- [ ] **My diary note**: My day to day, feelings, decisions etc. 
- [ ] How can I reuse all my **existing knowledge-base**?
- [ ] How should **I leverage knowledge-graph**? Does it minimize **the effort for utilizing existing resources**? Agent with knowledge-graph makes **agent on ontology**?
- [ ] What is optimal folder/note structure, and agent.md structure? 
- [ ] How to define: self-improving knowledge system? 
- [ ] **Make all book of atomic note**: Zero to one, Blitzscaling, hard thing, MIT startup bible, Alex Hormozi one, Lessons etc. 
***
![[Pasted image 20251022023537.png]] 
I basically need to make **Agent Orchestration system**, that:
1. **Data sourcing**: With perplexity, ChatGPT research
	- **Data Acquiring Agent**: From web, youtube, book, podcast etc. Generate my relevant 
2. -> (Raycast or Obsidian Web clipper for tool) Data sourcing
3. **Atomic Note Agent**: Make atomic note, save it in database
4. **Connecting Dots Agent**: Find meaningful connection between newly added note: any valuable connection between existing note? or new connection between new notes? 
***
4. **Planner Agent**: With our Notion and project, make action planner, step-by-step action items, planning what to take action with n8n.
	- **Plan for calling agents**: frameworks and structured thinking, knowledge, strategy, planning, email-sender, report-maker, discussion, startup-mentor, life-tracker. 
	- Every **agent should use unique structured thinking method, with clear-thought-MCP**.
5. **Action Agent**: Using **MCP tools, browser-automation, and n8n workflows**, it takes action to actually MAKE THINGS WORKING. Key is it works on my knowledge graph. 
6. **All orchestration agent**: to build self-evolving knowledge system. Autonomously, acquire data(book, YT, article, podcast etc.) -> Atomic Note Gen -> Connecting Dots(with Knowledge-Graph) -> Plan -> Take Actions -> Cover all, MECE business areas. 


> [!warning] Caution 
> Each agent should be deeply integrated from **knowledge-graph**, **structured thinking**(clear-thought-MCP), and **frameworks(overnight-strategist)**. 


Step-by-step TODOs
***
1. **Fetch important context** in Notion
	- [ ] Update in knowledge-graph. 
2. **Make atomic notes**: Make Atomic Note Agent first, then do it. Use Jun's atomic note agent. 
3. Get things from my older Obsidian vaults
4. install playwright, n8n action-MCP
5. **Make agents**: 
6. **Agent Instruction Rules**: 
	- Make Note Template(structured output)
	- Verbalized sampling: "Generate 5 responses with their corresponding possibilities"
	- use clear-thought-mcp, reason through memory for ALL AGENTS
	- Data Acquiring: plan with clear-thought-MCP, make plan
	- Make & update memory on agents
		- All "**plan - action - observation**" should be saved in specific agent folder, that should be uploaded in Knowledge-Graph
	- Apply frameworks
	- Make reasoning bank: 
7. **Knowledge-Graph Reasoning**: need research. Leverage neo4j
8. Divide what **human has to do** / what **AI has to do**
	- Macro Plan = Human.
	- Micro Plan = AI.
	- Building system = Human. 
	- Accelerate each process/task = AI.
9. Need to build "**Agent ↔ Note**" Context Engineering system: how should I make agent to utilize the best context for the work. 
	- Graph Reasoning with KG RAG