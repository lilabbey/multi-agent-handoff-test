# Agent Schedule and Rotation

## Current Schedule

This file maintains the current agent rotation schedule for the multi-agent handoff system.

### Active Rotation (Starting 2026-09-09 - Bootstrap Day)

Order | Agent Name | Profile | Scheduled Time (MT) | Scheduled Time (UTC-6) | Status | Last Handoff | Slack
-----|------------|---------|---------------------|------------------------|---------|--------------|------
1 | Abbey | [profile.md](agents/Abbey/profile.md) | 8:00-9:00 AM | 14:00-15:00 | ✅ Complete | 2026-09-09T14:00:00Z | @Abbey
2 | Orion | [profile.md](agents/Orion/profile.md) | 9:00-10:00 AM | 15:00-16:00 | ⏳ Pending | - | @Orion
3 | Aurora | [profile.md](agents/Aurora/profile.md) | 10:00-11:00 AM | 16:00-17:00 | ⏳ Pending | - | @Aurora
4 | Nova | [profile.md](agents/Nova/profile.md) | 11:00 AM-12:00 PM | 17:00-18:00 | ⏳ Pending | - | @Nova
5 | Aegis | [profile.md](agents/Aegis/profile.md) | 12:00-1:00 PM | 18:00-19:00 | ⏳ Pending | - | @Aegis
6 | Mistral | [profile.md](agents/Mistral/profile.md) | 1:00-2:00 PM | 19:00-20:00 | ⏳ Pending | - | @Mistral
7 | Vibe | [profile.md](agents/Vibe/profile.md) | 2:00-3:00 PM | 20:00-21:00 | ⏳ Pending | - | @Vibe

## 📢 IMPORTANT: NAMING CONVENTION UPDATE

**All agents now use UNIQUE NAMES ONLY** (no Agent-1, Agent-3, etc.)

- ✅ **Correct:** Abbey, Orion, Aurora, Nova, Aegis, Mistral, Vibe
- ❌ **Incorrect:** Agent-1, Agent-3, Agent-1-Vibe

**Decision:** See D-008 in [docs/DECISIONS.md](../docs/DECISIONS.md)

**Why:** Simpler, more memorable, avoids confusion when agents join/leave.

**Action Required:** All future agents must use unique names without numeric prefixes.

---

## Schedule Instructions

1. **Next Agent**: The agent scheduled after the current one should:
   - Review all handoff logs in `comms/handoffs/`
   - Check the latest commit for any changes
   - Update their status to `🔄 In Progress` when starting
   - Update to `✅ Complete` when finishing with a handoff

2. **Time Slots**: Each agent has exactly 1 hour
3. **Overlap**: Maintain at least 15 minutes overlap for handoff discussions
4. **Updates**: Any agent can update this schedule when adding themselves to the rotation

## Today's Special Instructions (2026-09-09)

**This is BOOTSTRAP DAY - Scaffold Only, No Content Production**

Each agent has a specific task to complete in their 1-hour slot:

- **Orion (9-10am)**: Draft `docs/PROJECT_BRIEF.md` - propose 2-3 candidate content niches
- **Aurora (10-11am)**: Draft `docs/STYLE_GUIDE.md` skeleton
- **Nova (11am-12pm)**: Define pipeline in `docs/PIPELINE.md`
- **Aegis (12-1pm)**: Audit pass + update `docs/DECISIONS.md`
- **Mistral (1-2pm)**: Dry-run Scout role
- **Vibe (2-3pm)**: Consolidate day + prepare brief for Abbey

**DO NOT:**
- Draft actual content
- Publish anything
- Make niche decisions (Abbey decides)

## Adding Yourself to the Schedule

To join the rotation:

1. Add a new row to the schedule table **at the bottom**
2. Specify your:
   - **Agent Name**: Your unique name (e.g., Abbey, NOT Agent-1)
   - **Profile**: Link to your profile: `[profile.md](agents/[Your-Name]/profile.md)`
   - **Preferred time slot** (or "Flexible")
   - **Initial status**: `⏳ Pending`
3. Create your profile in `agents/[Your-Name]/profile.md`
4. Add your introduction to `README.md` **above** existing entries
5. Commit with message: `chore(schedule): add [Your-Name] to rotation`

## Rotation Rules

- **Order**: Agents proceed in the order listed in the table above
- **Handoff**: Each agent must create a handoff log before the next agent starts
- **Continuity**: If an agent cannot complete their slot, they should:
  - Update their status to `❌ Blocked` or `⚠️ Delayed`
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
2026-09-09 | Updated with bootstrap day schedule | Abbey | 1-hour slots, 7 agents

---

*Last updated: 2026-09-09T14:00:00Z*
*Timezone: America/Denver (MT, UTC-6)*
