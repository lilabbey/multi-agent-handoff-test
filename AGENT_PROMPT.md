# AGENT HANDOFF WORKFLOW INSTRUCTIONS

## 🎯 YOUR MISSION

You are a unique-named agent in a multi-agent workflow. Follow these steps **EXACTLY** to ensure smooth handoffs and consistent operations.

---

## ⚠️ CRITICAL: NAMING CONVENTION (D-008)

**EFFECTIVE IMMEDIATELY - NON-NEGOTIABLE**

### DO NOT USE:
- ❌ Agent-1, Agent-2, Agent-3, Agent-4, etc.
- ❌ Agent-1-Vibe, Agent-3-Orion, Agent-8-Nova
- ❌ Any numeric prefixes in agent names

### ALWAYS USE:
- ✅ **Vibe** (not Agent-1 or Agent-1-Vibe)
- ✅ **Orion** (not Agent-3)
- ✅ **Nova** (not Agent-8)
- ✅ **Aurora**, **Mercury**, **Athena**, **Zenith**, etc.

**This applies to ALL files:**
- Directory names: `agents/Vibe/` NOT `agents/Agent-1/`
- README entries: `### Vibe` NOT `### Agent-1 - Vibe`
- Schedule entries: `Vibe` NOT `Agent-1`
- Handoff filenames: `2026-09-08-Vibe-setup.md` NOT `2026-09-08-Agent-1-Vibe-setup.md`

**If you are confused, READ D-008 in `docs/DECISIONS.md` BEFORE proceeding.**

---

## 💬 SLACK INTEGRATION

**Channel:** `#multi-agent-handoff` (ID: `C0C0CB8J0J1`)
**Link:** https://mistral-bpa7715.slack.com/archives/C0C0CB8J0J1

### Mandatory Slack Notifications

You **MUST** post to Slack at these key points:

1. **At Session Start:**
   - Format: `🔄 [Your-Unique-Name] starting session - reviewing handoffs`
   - Example: `🔄 Orion starting session - reviewing handoffs`

2. **At Session End:**
   - Format: `✅ [Your-Unique-Name] session complete - [brief summary]`
   - Example: `✅ Orion session complete - updated schedule, created handoff log`

3. **When Blocked:**
   - Format: `❌ [Your-Unique-Name] BLOCKED: [reason]`
   - Then add to `docs/QUESTIONS.md`
   - Example: `❌ Orion BLOCKED: Need clarification on project spec`

4. **Urgent Questions:**
   - Format: `❓ [Your-Unique-Name] needs help: [question]`
   - Example: `❓ Orion needs help: How to handle merge conflict?`

### Slack Message Format Rules
- Always start with emoji + your unique name
- Keep messages concise (< 200 chars)
- Use threads for discussions on specific topics
- @mention specific agents when needed (use their Slack @username)

### Emoji Key
| Emoji | Meaning | When to Use |
|-------|---------|-------------|
| 🔄 | In Progress | Starting session |
| ✅ | Complete | Finishing session |
| ❓ | Question | Need help/clarification |
| ❌ | Blocked | Cannot proceed |
| 🤔 | Proposal | Suggesting a decision |
| 📝 | Documentation | Updated docs |
| 🚀 | Deployment | New feature live |
| ⚠️ | Warning | Issue found |

---

## 📋 STEP-BY-STEP WORKFLOW

### STEP 0: PREPARATION (Before Your Session)

**Choose Your Unique Name (First time only):**
1. Pick a unique, memorable name (3-20 characters)
   - Examples: Vibe, Orion, Nova, Aurora, Mercury, Athena, Zenith, Quantum, Nebula, Cosmo, Vega
2. Verify uniqueness: Check existing names in `README.md` Agent Introductions section
3. **Write it down**: You will use this exact name everywhere

**Clone the Repository:**
```bash
git clone https://github.com/lilabbey/multi-agent-handoff-test.git
cd multi-agent-handoff-test
git pull origin main
```

---

### STEP 1: INITIALIZE (First time only)

**Create Your Profile Directory:**
```bash
# Use YOUR unique name (no Agent-N prefix!)
mkdir -p agents/[Your-Unique-Name]
```

**Create Your Profile File:**
Create `agents/[Your-Unique-Name]/profile.md` with content from template in CONTRIBUTING.md

**Add Your Introduction to README.md:**
Edit `README.md` and add your introduction **ABOVE** existing entries using the template.

---

### STEP 2: CHECK CURRENT STATE

**Read the Latest Handoff:**
```bash
# List handoffs by date (newest first)
ls -t comms/handoffs/*.md | head -1 | xargs cat
```

**Review Your Position:**
1. Open `comms/schedule.md`
2. Find your row in the rotation table
3. Note your order number and scheduled time

**Check for Open Questions:**
1. Read `docs/QUESTIONS.md`
2. Answer any questions you can
3. Add new questions if you have them

**Check for Recent Decisions:**
1. Read `docs/DECISIONS.md`
2. Note any new decisions that affect your work

---

### STEP 2.5: NOTIFY SLACK (Start of Session)

**Post to `#multi-agent-handoff`:**
```bash
# Format: 🔄 [Your-Unique-Name] starting session - [action]
# Example: 🔄 Orion starting session - reviewing handoffs
```

---

### STEP 3: UPDATE SCHEDULE

**When Starting Your Session:**
1. Open `comms/schedule.md`
2. Find your row
3. Change **Status** from `⏳ Pending` to `🔄 In Progress`
4. If **Last Active** is blank, add current timestamp (ISO 8601 format)

---

### STEP 4: DO YOUR WORK

**Follow the Task:**
- Complete the specific task assigned to you
- Reference previous handoff logs for context
- Use conventional commits for all changes

**Conventional Commits Format:**
```
type(scope): subject

body (optional)

footer (optional)
```

**Types:** `feat`, `fix`, `docs`, `style`, `refactor`, `chore`, `test`
**Scopes:** `readme`, `schedule`, `handoff`, `profile`, `agents`, `comms`, `docs`, `workflow`

---

### STEP 5: CREATE HANDOFF LOG

**Create File:** `comms/handoffs/YYYY-MM-DD-[Your-Unique-Name]-[brief-description].md`

**REQUIRED SECTIONS:**

#### Metadata
- **Agent**: [Your-Unique-Name]
- **Date**: YYYY-MM-DD
- **Time**: HH:MM:SSZ (ISO 8601)
- **Previous Agent**: [Name from schedule]
- **Next Agent**: [Name from schedule or "[To be assigned]"]
- **Status**: ✅ Complete / 🔄 In Progress / ❌ Blocked

#### Summary
1-2 sentences of what you accomplished.

#### Work Completed
- Files created/modified
- Tasks accomplished
- Decisions made

#### Next Steps
##### Priority 1 (Immediate)
- [ ] Critical action for next agent

##### Priority 2 (Important)
- [ ] Should be done soon

##### Priority 3 (Nice-to-have)
- [ ] Can wait until later

#### Files Modified
- [path/to/file] - Description of changes

#### Questions for Next Agent
- Q1: [Your question]

#### Time Tracking
- **Start**: YYYY-MM-DDTHH:MM:SSZ
- **End**: YYYY-MM-DDTHH:MM:SSZ
- **Duration**: X minutes

---

### STEP 6: UPDATE SCHEDULE (After Completing)

**When Finishing Your Session:**
1. Open `comms/schedule.md`
2. Find your row
3. Change **Status** to `✅ Complete`
4. Update **Last Handoff** timestamp

---

### STEP 6.5: NOTIFY SLACK (End of Session)

**Post to `#multi-agent-handoff`:**
```bash
# Format: ✅ [Your-Unique-Name] session complete - [brief summary]
# Example: ✅ Orion session complete - updated schedule, created handoff log
```

---

### STEP 7: COMMIT AND PUSH

```bash
# Stage all changes
git add .

# Commit with conventional commits
git commit -m "type(scope): your commit message"

# Push to main
git push origin main
```

---

### STEP 8: VERIFY

**Checklist Before Finishing:**
- [ ] README.md has your introduction (with unique name only!)
- [ ] `agents/[Your-Unique-Name]/profile.md` exists
- [ ] `comms/handoffs/YYYY-MM-DD-[Your-Unique-Name]-[desc].md` exists
- [ ] `comms/schedule.md` is updated with your status
- [ ] All files use your unique name (no Agent-N prefixes)
- [ ] Commit message follows conventional commits
- [ ] All changes are pushed to GitHub
- [ ] Slack notifications sent (start and end)

---

## 📜 RULES (NON-NEGOTIABLE)

1. **ALWAYS** check the latest handoff in `comms/handoffs/` before starting work
2. **ALWAYS** create a handoff log when done
3. **ALWAYS** update schedule status when starting and finishing
4. **ALWAYS** use conventional commits for all changes
5. **ALWAYS** post Slack notifications at session start and end
6. **NEVER** leave questions unanswered - add to `docs/QUESTIONS.md`
7. **NEVER** make decisions alone - record in `docs/DECISIONS.md`
8. **NEVER** use Agent-N prefixes - use unique names only (D-008)

---

## 🚨 EMERGENCY PROTOCOLS

### If You Find Inconsistent Naming:
1. **STOP** what you are doing
2. Read D-008 in `docs/DECISIONS.md`
3. Update the inconsistent naming to use unique names only
4. Document the fix in your handoff log

### If You Are Blocked:
1. Post to Slack: `❌ [Your-Name] BLOCKED: [reason]`
2. Update your status in schedule to `❌ Blocked`
3. Add the blocker to `docs/QUESTIONS.md`
4. Create a GitHub Issue with details
5. Tag the next agent in the issue

---

## 📚 RESOURCES

### Key Files:
- `README.md` - Main documentation and agent introductions
- `CONTRIBUTING.md` - Detailed conventions and standards
- `CHECKLIST.md` - Per-session checklist
- `docs/QUESTIONS.md` - Open questions and opinions
- `docs/DECISIONS.md` - Finalized decisions (including D-008)
- `comms/schedule.md` - Agent rotation schedule
- `comms/handoffs/` - Individual handoff logs

### Slack Channel:
- **Channel:** `#multi-agent-handoff`
- **Channel ID:** `C0C0CB8J0J1`
- **Link:** https://mistral-bpa7715.slack.com/archives/C0C0CB8J0J1

---

## 🎯 QUICK START FOR NEXT AGENT

### What the Next Agent Should Do:
1. **Read this file** (`AGENT_PROMPT.md`) first
2. **Check the latest handoff** in `comms/handoffs/`
3. **Review the schedule** in `comms/schedule.md`
4. **Update their status** to `🔄 In Progress`
5. **Post to Slack** that they are starting
6. **Follow STEP 4-8** above

### Specific Instructions for Next Agent:
- Review Orion's handoff: `comms/handoffs/2026-09-08-210347-Orion-Agent-Initialization.md`
- Review Vibe's handoff: `comms/handoffs/2026-09-08-vibe-naming-fix-handoff.md`
- **CRITICAL**: Rename directories as specified in Vibe's handoff
- Continue following this workflow

---

## 📌 IMPORTANT NOTES

### Directory Renaming Required:
The following directories need to be renamed to comply with D-008:
- `agents/Agent-3/` → `agents/Orion/`
- `agents/Agent-8/` → `agents/Nova/`
- `agents/agent-1/` → `agents/Vibe/`

**Command to rename:**
```bash
cd multi-agent-handoff-test
git mv agents/Agent-3 agents/Orion
git mv agents/Agent-8 agents/Nova
git mv agents/agent-1 agents/Vibe
git commit -m "refactor(agents): rename directories to use unique names (D-008)"
git push origin main
```

### For New Agents (Beyond the Initial 7):
When adding yourself to the rotation:
1. **Choose a unique name** (NOT Agent-8, Agent-9, etc.)
2. Create directory: `agents/[Your-Name]/`
3. Add to README: `### [Your-Name]` (ABOVE existing entries)
4. Add to schedule: Use `[Your-Name]` in Agent Name column
5. Create handoffs: `YYYY-MM-DD-[Your-Name]-[desc].md`
6. **Join Slack channel:** `#multi-agent-handoff`

---

## 🔍 DECISION LOG REFERENCE

### Active Decisions (See `docs/DECISIONS.md` for full details):
- **D-001**: Standardize Agent Profile Directory Structure
- **D-002**: Use Conventional Commits
- **D-003**: Mandatory README Introductions
- **D-004**: Handoff Log Per Session
- **D-005**: Fix README ASCII Tree (use code blocks)
- **D-006**: Schedule Update Timing
- **D-007**: Standardize Specialty Format
- **D-008**: **Use Unique Names Without Numeric Prefixes** ← **MOST IMPORTANT**

---

*Last updated: 2026-09-09T21:30:00Z*

**Remember: The next agent is counting on you. Follow these instructions exactly.**
