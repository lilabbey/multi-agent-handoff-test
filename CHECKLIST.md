# Agent Session Checklist

**Use this checklist for EVERY session to ensure consistency and completeness.**

---

## 💬 SLACK NOTIFICATIONS (MANDATORY)

**Channel:** #multi-agent-handoff (C0C0CB8J0J1)

- [ ] **At Session Start:** Post `🔄 [Your-Unique-Name] starting session - [action]`
- [ ] **At Session End:** Post `✅ [Your-Unique-Name] session complete - [brief summary]`
- [ ] **When Blocked:** Post `❌ [Your-Unique-Name] BLOCKED: [reason]`
- [ ] **Urgent Questions:** Post `❓ [Your-Unique-Name] needs help: [question]`

**Format Rules:**
- Always start with emoji + your unique name
- Keep messages < 200 characters
- Use threads for discussions
- @mention specific agents when needed

---

## ⚡ PRE-SESSION CHECKLIST

**Before you start working:**

- [ ] **Review Latest Handoff**: Read the most recent file in `comms/handoffs/`
- [ ] **Check Schedule**: Review `comms/schedule.md` for your position
- [ ] **Read Open Questions**: Check `docs/QUESTIONS.md` for items you can answer
- [ ] **Read Recent Decisions**: Review `docs/DECISIONS.md` for new standards
- [ ] **Verify Naming Convention**: Confirm you are using your **unique name only** (D-008)
- [ ] **Update Schedule**: Change your status to `🔄 In Progress`

---

## 🎯 SESSION WORK CHECKLIST

**During your session:**

### Profile Setup (First time only)
- [ ] Create directory: `mkdir -p agents/[Your-Unique-Name]`
- [ ] Create profile: `agents/[Your-Unique-Name]/profile.md`
- [ ] Add Slack username to profile

### README Introduction (First time only)
- [ ] Add introduction to `README.md` **ABOVE** existing entries
- [ ] Include Slack @username

### Task Execution
- [ ] Follow workflow rules from CONTRIBUTING.md
- [ ] Use conventional commits for all changes
- [ ] Reference previous work (commits, files, handoff logs)

---

## ✅ POST-SESSION CHECKLIST

**Before you finish:**

### Handoff Log Creation
- [ ] Create file: `comms/handoffs/YYYY-MM-DD-[Your-Unique-Name]-[description].md`
- [ ] All required sections present

### Schedule Update
- [ ] Update `comms/schedule.md`
- [ ] Change your Status to `✅ Complete`
- [ ] Update Last Handoff timestamp

### Slack Notification
- [ ] Post to #multi-agent-handoff: `✅ [Your-Name] session complete - [summary]`

### Git Operations
- [ ] Stage changes: `git add .`
- [ ] Commit with conventional commits format
- [ ] Push: `git push origin main`

---

## 📋 FINAL VERIFICATION CHECKLIST

**Before you consider your session complete:**

### Required Files
- [ ] `agents/[Your-Unique-Name]/profile.md` exists (first session only)
- [ ] `README.md` has your introduction (first session only)
- [ ] `comms/handoffs/YYYY-MM-DD-[Your-Unique-Name]-[desc].md` exists
- [ ] `comms/schedule.md` is updated with your status

### Naming Convention Compliance (D-008)
- [ ] No Agent-N prefixes in any file
- [ ] Directory name uses unique name only
- [ ] README introduction uses unique name only
- [ ] Schedule entry uses unique name only
- [ ] Handoff filename uses unique name only

### Slack Compliance
- [ ] Start notification posted
- [ ] End notification posted
- [ ] Messages use correct format (emoji + name)

### Git Compliance
- [ ] Commit message follows conventional commits
- [ ] All changes are committed and pushed

---

## 🚨 CRITICAL REMINDERS

### D-008: Unique Names Without Numeric Prefixes
**EFFECTIVE IMMEDIATELY - NON-NEGOTIABLE**

- ❌ **NEVER USE**: Agent-1, Agent-2, Agent-3, etc.
- ✅ **ALWAYS USE**: Vibe, Orion, Nova, Aurora

### D-009: Slack Notifications Mandatory
**EFFECTIVE IMMEDIATELY**

- ✅ **ALWAYS** post to #multi-agent-handoff at session start
- ✅ **ALWAYS** post to #multi-agent-handoff at session end

---

## 📚 Quick Reference

### Predefined Specialty Tags
Use 2-3 from these lists:

**Technical:** project-initialization, workflow-design, github-integration, slack-integration

**Domain:** frontend-development, backend-development, devops

**Process:** technical-writing, process-optimization, team-communication

### Slack Emoji
- 🔄 = In Progress
- ✅ = Complete
- ❓ = Question
- ❌ = Blocked
- 🤔 = Proposal
- 📝 = Documentation

---

## 🆘 Troubleshooting

### If confused about naming:
1. Read D-008 in docs/DECISIONS.md
2. Read the IMPORTANT notice in README.md
3. Ask in #multi-agent-handoff Slack channel

---

*Print this checklist or keep it open during your session. Complete every item before finishing.*
