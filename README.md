# AgentBoard — Kanban for Coding Agents (demo)

An original, single-file portfolio demo by Rafi Jacobson. A Linear/Cursor-style board for orchestrating AI coding agents.
**All agents, repos, logs, token counts and costs are simulated in the browser.**

## Run
Open `index.html` in any modern browser. No build step and no dependencies (the Inter/JetBrains Mono fonts come from Google Fonts and are optional).

## Views
- **Board** — every session collated: Done | Needs you | Running. Orchestrator sessions and their worker subagents, drag-and-drop between columns
- **Inbox** — only the main orchestrator sessions, only when they truly need you. Each item is rewritten by the interceptor (below) into a concise visual card: summary, fact chips, suggested action, Approve / Reject, plus "show original" for the full agent log
- **Dashboard** — KPIs (tasks done, success rate, avg time, cost, tokens, intercepted, needs-you), canvas throughput chart, SVG cost-by-agent chart, agent utilization, activity feed
- Open the dashboard directly with `index.html#dashboard`, the inbox with `index.html#inbox`

## The interceptor (cheap model)
A simulated cheap-model layer sits between the agents and you. When a session needs attention it first tries to handle it itself (~45% of the time it just merges and moves on — those never reach you, marked ✦). Otherwise it rewrites the agent's long-winded log into the concise visual inbox card. Worker sessions never surface directly; their needs escalate through their orchestrator.

## Features
- Columns: Done | Needs you | Running (left to right). New tasks go straight to Running (queued ones sit at the top with a "queued" tag until started); drag-and-drop between columns
- Approve moves a card to Done (merged); reject archives a rejected copy in Done and re-runs the agent
- "Close session" on a Done card moves it to the collapsible Closed sessions area below the board, where it can be reopened
- Task cards: agent + model, worker/orchestrator tag, parent session, repo/branch, progress, tokens, est. cost, elapsed time, ✦ marker when the interceptor touched it
- New-task modal (press `n`), optional auto-start
- Side panel: live streaming agent log, diff summary, Approve & merge / Reject & re-run
- Simulated agents advance on timers (1×/3×/8× speed)
- State persisted in localStorage; "Reset demo" restores seed data
