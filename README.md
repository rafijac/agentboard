# AgentBoard — Kanban for Coding Agents (demo)

An original, single-file portfolio demo by Rafi Jacobson. A Linear/Cursor-style board for orchestrating AI coding agents.
**All agents, repos, logs, token counts and costs are simulated in the browser.**

## Run
Open `index.html` in any modern browser. No build step and no dependencies (the Inter/JetBrains Mono fonts come from Google Fonts and are optional).

## Features
- Columns: Done | Needs you | Running (left to right). New tasks go straight to Running (queued ones sit at the top with a "queued" tag until started); drag-and-drop between columns
- Approve moves a card to Done (merged); reject archives a rejected copy in Done and re-runs the agent
- "Close session" on a Done card moves it to the collapsible Closed sessions area below the board, where it can be reopened
- Open the dashboard directly with `index.html#dashboard`
- Task cards: agent + model, repo/branch, progress, tokens, est. cost, elapsed time
- New-task modal (press `n`), optional auto-start
- Side panel: live streaming agent log, diff summary, Approve & merge / Reject & re-run
- Simulated agents advance on timers (1×/3×/8× speed)
- Dashboard tab: KPIs (tasks done, success rate, avg time, cost, tokens), canvas throughput chart, SVG cost-by-agent chart, agent utilization, activity feed
- State persisted in localStorage; "Reset demo" restores seed data
