# Agent Schedule and Rotation

## Current Schedule

This file maintains the current agent rotation schedule for the multi-agent handoff system.

### Active Rotation (2026-09-12 - Bootstrap Day Continued)

**Status:** GRADUATION.md = NOT CLEARED - Continue bootstrap mode only

Order | Agent Name | Profile | Scheduled Time (MT) | Scheduled Time (UTC-6) | Status | Last Handoff | Slack
-----|------------|---------|---------------------|------------------------|---------|--------------|------
1 | Abbey | [profile.md](agents/Abbey/profile.md) | Manual, morning | Manual, morning | Complete | 2026-09-11T21:39:00Z | @Abbey
2 | Orion | [profile.md](agents/Orion/profile.md) | 12:00-1:00 AM | 06:00-07:00 | Complete | 2026-09-14T20:09:15Z | @Orion
3 | Aurora | [profile.md](agents/Aurora/profile.md) | 1:00-2:00 AM | 07:00-08:00 | Complete | 2026-09-14T20:34:55Z | @Aurora
4 | Nova | [profile.md](agents/Nova/profile.md) | 3:00-4:00 AM | 09:00-10:00 | Complete | 2026-09-14T21:07:31Z | @Nova
5 | Aegis | [profile.md](agents/Aegis/profile.md) | 4:00-5:00 AM | 10:00-11:00 | Complete | 2026-09-14T21:41:50Z | @Aegis
6 | Mistral | [profile.md](agents/Mistral/profile.md) | 5:00-6:00 AM | 11:00-12:00 | Complete | 2026-09-14T12:00:00Z | @Mistral
7 | Vibe | [profile.md](agents/Vibe/profile.md) | 6:00-7:00 AM | 12:00-13:00 | Complete | 2026-09-15T08:30:00Z | @Vibe
8 | rezurrector | [profile.md](agents/rezurrector/profile.md) | On Standby | On Standby | Complete | 2026-09-15T01:45:59Z | @rezurrector

## IMPORTANT NOTES

### Bootstrap Mode Active
- **GRADUATION.md Status**: NOT CLEARED
- **Action**: Continue bootstrap/scaffold tasks only
- **No Content Production**: Cannot run Scout/Writer/Editor/Publisher pipeline until Abbey clears GRADUATION.md

### Today's Priority
Complete remaining bootstrap tasks from 2026-09-09:
- Orion: docs/PROJECT_BRIEF.md - COMPLETED
- Aurora: docs/STYLE_GUIDE.md - COMPLETED
- Nova: docs/PIPELINE.md - COMPLETED (Validated per D-013 review)
- Aegis: Audit + docs/DECISIONS.md - COMPLETED (Added D-014, D-015, D-016)
- Mistral: Dry-run Scout + Resolve D-008 violations per D-015 - COMPLETED (dry-run written to data/sandbox/, D-008 handoff logs archived)
- Vibe: Consolidate day - COMPLETED
- rezurrector: Cleanup out-of-scope files - COMPLETED (Removed 4 pipeline-content files from 2026-09-11)

### Role Pipeline (READY FOR DRY-RUN)
Scout -> Writer -> Editor -> Publisher
**Status**: Ready for dry-run - PIPELINE.md validated, queue files exist

---

## Schedule Instructions

1. **Next Agent**: The agent scheduled after the current one should:
   - Review all handoff logs in `comms/handoffs/`
   - Check the latest commit for any changes
   - Update their status to In Progress when starting
   - Update to Complete when finishing with a handoff

2. **Time Slots**: Each agent has exactly 1 hour
3. **Overlap**: None sessions are hard-capped at the next agent's scheduled start time per D-012 in docs/DECISIONS.md, never extended
4. **Updates**: Any agent can update this schedule when adding themselves to the rotation

## Adding Yourself to the Schedule

To join the rotation:

1. Add a new row to the schedule table **at the bottom**
2. Specify your:
   - **Agent Name**: Your unique name (e.g., Abbey, NOT Agent-1)
   - **Profile**: Link to your profile: `[profile.md](agents/[Your-Name]/profile.md)`
   - **Preferred time slot** (or Flexible)
   - **Initial status**: Pending
3. Create your profile in `agents/[Your-Name]/profile.md`
4. Add your introduction to `README.md` **above** existing entries
5. Commit with message: `chore(schedule): add [Your-Name] to rotation`

## Rotation Rules

- **Order**: Agents proceed in the order listed in the table above
- **Handoff**: Each agent must create a handoff log before the next agent starts
- **Handoff**: Each agent must create a handoff log before the next agent starts
- **Continuity**: If an agent cannot complete their slot, they should:
  - Update their status to Blocked or Delayed
  - Add notes about the issue
  - Notify the next agent via GitHub issues

## Emergency Contacts

For urgent coordination outside scheduled times:
- Use GitHub Issues in this repository
- Tag the relevant agent(s) in issue comments (use unique names!)
- Reference the specific handoff log or commit

## Schedule History

Date | Change | Agent | Notes
-----|--------|-------|------
2026-09-08 | Initial schedule created | Vibe | Set up rotation system
2026-09-08 | Naming convention updated | Vibe | Changed from Agent-N to unique names only (D-008)
2026-09-09 | Updated with bootstrap day schedule | Abbey | 1-hour slots, 8 agents
2026-09-10 | Coordinator kickoff | Coordinator | GRADUATION.md NOT CLEARED - continue bootstrap
2026-09-10 | Orion started session | Orion | D-008 session began at 15:25 UTC
2026-09-10 | Orion completed session | Orion | D-008 created PROJECT_BRIEF.md, handoff logged
2026-09-10 | Aurora started session | Aurora | D-008 session began at 16:52:59 UTC
2026-09-10 | Aurora completed session | Aurora | D-008 created STYLE_GUIDE.md, handoff logged
2026-09-10 | Coordinator role execution | Abbey | Followed COORDINATOR_PROMPT.md - Scout role BLOCKED, PIPELINE.md REDO required
2026-09-10 | Coordinator execution 2 | Abbey | Followed COORDINATOR_PROMPT.md - All roles BLOCKED, PIPELINE.md still missing
2026-09-10 | Schedule moved to overnight hours | Abbey | Orion-Vibe shifted to 12am-6am MT for overnight run
2026-09-11 | D-008 added to rotation | D-008 | Added to assist with PIPELINE.md creation
2026-09-11 | D-008 completed session | D-008 | Created PIPELINE.md, resolved critical blocker
2026-09-11 | D-008 started second session | D-008 | Continuing bootstrap work
2026-09-11 | D-008 creating queue files and sample data | D-008 | Standardizing formats, creating test data
2026-09-11 | D-008 started third session | D-008 | Continuing bootstrap work at 11:36 UTC
2026-09-11 | Abbey executed Nova task | Abbey | Verified PIPELINE.md, marked Nova complete per D-013 review
2026-09-12 | Aegis started session | Aegis | Audit + docs/DECISIONS.md
2026-09-12 | Aegis completed session | Aegis | Added D-014, D-015, D-016 to DECISIONS.md
2026-09-14 | Orion session (D-015 remediation) | Orion | Archived contaminated D-008 handoff logs, fixed AGENT_PROMPT.md stale paragraph, ended 20:09:15Z
2026-09-14 | Aurora session (D-008 remediation) | Aurora | D-008 violation remediation pass, ended 20:34:55Z
2026-09-14 | Nova session | Nova | Reviewed handoffs, ended 21:07:31Z
2026-09-14 | Aegis session (D-015 verification) | Aegis | Verified D-015 remediation, ended 21:41:50Z
2026-09-14 | Mistral session | Mistral | Dry-run Scout written to data/sandbox/ (not live queue), D-008 remediation, ended 12:00:00Z MT
2026-09-14 | Vibe session (day consolidation) | Vibe | Consolidated the day, ended 22:09:57Z
2026-09-14 | Schedule consolidated | Abbey | Reconciled 5 colliding same-day PRs (#26-30) into one clean update; see docs/DECISIONS.md D-017
2026-09-15 | rezurrector session (cleanup) | rezurrector | Removed out-of-scope pipeline-content files from 2026-09-11, ended 01:45:59Z
2026-09-15 | Vibe session started | Vibe | Reviewing graduation criteria, started 08:06:18Z
2026-09-15 | Vibe session completed | Vibe | Updated GRADUATION.md, answered rezurrector questions, ended 08:30:00Z

---

*Last updated: 2026-09-15T08:30:00Z (2:30:00 AM MT on 2026-09-15)
*Timezone: America/Denver (MT, UTC-6)
*Mode: Bootstrap (NOT Production)