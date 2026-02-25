---
name: notion-use
description: Automate Notion-related execution requests including meeting prep, scrum backlog/task management, legal-related task, and shared team document work. Use when user asks to do work in Notion or delegate Notion operations to Notion PO agent. Mandatory workflow: load playwriter skill, use playwriter MCP to open Notion, enter Notion AI, delegate with fixed PO handoff format, then notify user to verify the opened Notion AI page.
---

# Notion Use Skill

Follow this deterministic workflow exactly.

## 0) Mandatory preflight
1. Load the `playwriter` skill.
2. Load the `playwriter` MCP, and verify playwriter extension connectivity and page control readiness.
3. If extension/session is not ready, stop and return one actionable recovery step.

## 1) Open Notion and enter Notion AI
1. Open `https://www.notion.so/ai`. If not worked, `https://notion.so/`
1-1. Confirm user is authenticated; if not authenticated, stop and ask user to complete login.
1-2. Primary path: click `Notion AI` in sidebar.
2. Fallback path: use Notion AI shortcut if sidebar path is unavailable.
3. After each action, verify page state before continuing.

## 2) Delegate to PO agent
Use this exact handoff format:

`PO Task`
- Goal: <one-sentence objective>
- Scope: <what to include/exclude>
- Context/Sources: <links/IDs/context>
- Done Checks: <1-3 observable outputs>

If required fields are missing, request only the minimum missing values.

## Fail-fast rules
- Do not continue when extension is disconnected.
- Do not continue when Notion authentication blocks access.
- Do not invent PO agent identifiers or payload fields.