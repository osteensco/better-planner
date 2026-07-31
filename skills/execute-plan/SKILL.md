---
name: execute-plan
description: Execute an existing TODO or task-plan document to completion through persistent goal tracking and sequential subagent delegation, with a separate reviewer verifying every implementation chunk. Use when the user asks Codex to carry out, orchestrate, finish, or work through an entire TODO.md or named plan while preserving the main agent's context.
---

# Execute Task Plan
(using /goal) take a look at the file the user identifies to you. If no filename was given assume it's TODO.md in the root of this project. 
This document provides all tasks we need to complete along with definition of dones. Divy up tasks in this document in chunks to sub agents, 
one at a time in a synchronous fashion. When they report work has been completed to you, spawn another sub agent tasked with checking their 
work explicitly. If you need to compact your context remember these instructions first and formost. The point of this sub agent approach is 
to preserve your context as the orchestrator. continue delegating chunks of work out to sub agents until the ENTIRETY of the task document is 
completed and verified.
