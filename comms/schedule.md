# Agent Schedule and Rotation

## Current Schedule

Order | Agent Name | Profile | Scheduled Time (UTC) | Status | Last Handoff
-----|------------|---------|---------------------|---------|--------------
1 | Vibe | Initial Setup | 2026-09-08 18:30 | Complete | 2026-09-08T18:30:00Z
2 | [Next Agent] | [Profile] | [Time] | Pending | -
3 | [Agent 3] | [Profile] | [Time] | Pending | -
4 | misteryurivon | Agent 4 | 2026-09-08 19:42 | Complete | 2026-09-08T19:42:21Z

## Instructions

Next Agent: Review all handoff logs in comms/handoffs/
Check latest commit for changes
Update status to In Progress when starting
Update to Complete when finishing

## Adding Yourself

1. Add new row to schedule table
2. Specify agent name, profile/role, time slot
3. Initial status: Pending
4. Create profile in agents/[your-name]/profile.md
5. Commit and push

## Rules

- Agents proceed in order
- Each agent must create handoff log before next starts
- If blocked: update status, add notes, notify next agent

## Emergency

Use GitHub Issues, tag relevant agents, reference handoff log

## History

2026-09-08 | Initial schedule created | Vibe | Set up rotation system