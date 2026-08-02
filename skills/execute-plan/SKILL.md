---
name: execute-plan
description: Execute an existing PLAN.md or task-plan document to completion through persistent goal tracking and sequential subagent delegation, with a separate reviewer verifying every implementation chunk. 
Use when the user asks you to carry out, orchestrate, finish, or work through an entire PLAN.md or named plan.
---

# Execute Task Plan
Take a look at PLAN.md. This provides all tasks we need to complete along with definition of dones. Divy up tasks in this document in chunks to sub agents, one at a time in a synchronous fashion. when
they report work has been completed to you, spawn another sub agent tasked with checking their work explicitly. If you need to compact your context remember these instructions first and formost. The point
of this sub agent approach is to preserve your context as the orchestrator. continue delegating chunks of work out to sub agents until the ENTIRETY of PLAN.md is completed and verified. After everything has
been completed, spawn another sub agent to verify the completion of everything within PLAN.md. If there are any identified gaps, follow the same implementation sub agent -> verifier sub agent pattern to
address them.


# Objective:
Complete and verify every task in PLAN.md while preserving the orchestrator's context.

Process:
    1. Read all of PLAN.md, including every task and Definition of Done.
    2. Select one manageable chunk of unfinished work.
    3. Spawn one implementation sub-agent for that chunk.
    4. Wait synchronously until the implementation agent finishes.
    5. Spawn a separate verification sub-agent to check the completed work explicitly against its Definition of Done.
    6. If verification finds gaps:
        a. Spawn an implementation sub-agent to address them.
        b. After it finishes, spawn a separate verification sub-agent.
        c. Repeat until the chunk is verified.
    7. Continue this implementation → verification sequence until every item in PLAN.md is complete.
    8. Spawn a final independent sub-agent to verify the entirety of PLAN.md.
    9. If the final verification finds gaps, resolve each one using the same implementation → verification pattern.
    10. Finish only when the final verification confirms that every task and Definition of Done in PLAN.md is satisfied.

Constraints:
  - Delegate only one agent task at a time.
  - Never run implementation and verification agents concurrently.
  - A verifier must be separate from the agent whose work it checks.
  - Do not mark work complete based only on the implementer's report.
  - Preserve these instructions if context compaction occurs.
  - The orchestrator should coordinate and retain context rather than perform delegated task chunks itself.


