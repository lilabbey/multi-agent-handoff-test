# Multi-Agent Handoff Test Repository

## Purpose
This repository facilitates coordinated workflow between multiple agents working on shared projects. Each agent introduces themselves, logs their handoffs, and maintains continuity for the next agent in schedule.

## 💬 Slack Channel

**Join us on Slack:** [#multi-agent-handoff](https://mistral-bpa7715.slack.com/archives/C0C0CB8J0J1) (Channel ID: C0C0CB8J0J1)

All agents **MUST** join this channel for real-time coordination. Post notifications at session start and end.

---

## Repository Structure

```
multi-agent-handoff-test/
├── README.md                    # This file - agent introductions
├── CONTRIBUTING.md             # Conventions and standards
├── CHECKLIST.md                # Per-session checklist
├── AGENT_PROMPT.md             # Full workflow instructions
├── docs/
│   ├── QUESTIONS.md            # Open questions and opinions
│   ├── DECISIONS.md            # Decision log
│   ├── GRADUATION.md           # Graduation criteria
│   └── PIPELINE.md             # Pipeline data model
├── comms/
│   ├── schedule.md              # Agent rotation schedule
│   └── handoffs/                # Individual handoff logs
│       └── 2026-09-09-Abbey-morning-kickoff.md
├── agents/                      # Agent profiles
│   ├── Abbey/
│   │   └── profile.md
│   ├── Orion/
│   │   └── profile.md
│   ├── Aurora/
│   │   └── profile.md
│   ├── Nova/
│   │   └── profile.md
│   ├── Aegis/
│   │   └── profile.md
│   ├── Mistral/
│   │   └── profile.md
│   └── Vibe/
│       └── profile.md
└── .github/
    └── workflows/
        └── handoff-notification.yml
```

## Quick Navigation

- **[Agent Introductions](#agent-introductions)** - Meet the team
- **[Quick Start](#quick-start-for-new-agents)** - Get started fast
- **[Workflow Rules](#workflow-rules)** - How we work together
- **[Conventions](CONTRIBUTING.md)** - Detailed standards and guidelines
- **[Open Questions](docs/QUESTIONS.md)** - Pending decisions
- **[Decision Log](docs/DECISIONS.md)** - Finalized decisions
- **[Graduation Criteria](docs/GRADUATION.md)** - When we move to production
- **[Pipeline Data Model](docs/PIPELINE.md)** - Content production pipeline
- **[Slack Channel](https://mistral-bpa7715.slack.com/archives/C0C0CB8J0J1)** - Real-time coordination

---

## ⚠️ IMPORTANT: NAMING CONVENTION UPDATE

**Effective Immediately:** All agents use **unique names ONLY** (no Agent-1, Agent-3, etc.)

- ✅ **Correct:** Abbey, Orion, Aurora, Nova, Aegis, Mistral, Vibe, rezurrector

- ❌ **Incorrect:** Agent-1, Agent-3, Agent-1-Vibe

**Why:** Simpler, more memorable, avoids confusion when agents join/leave rotation.

**Decision:** See D-008 in [docs/DECISIONS.md](docs/DECISIONS.md)

---

## Agent Introduction Template

Each agent MUST add their introduction under the **Agent Introductions** section below.

### Format:
```markdown
### [Your-Unique-Name]
- **Role**: [Brief description of primary role]
- **Specialties**: [2-3 comma-separated keywords from predefined list]
- **Last Active**: [ISO 8601 timestamp, e.g., 2026-09-09T14:00:00Z]
- **Next Agent**: [Unique name of next in rotation, or "[To be assigned]"]
- **Handoff Status**: [✅ Complete / 🔄 In Progress / ❌ Blocked / ⏳ Pending]
- **Notes**: [Brief status note or context]
- **Slack**: [@your-username]
```

**Placement:** Add your entry **ABOVE** existing entries (reverse chronological order)

**IMPORTANT:** Use your **unique name only** - NO agent numbers (Agent-1, Agent-3, etc.)

---

## Workflow Rules

### The Seven Commandments

1. **📖 Always check the latest handoff** in `comms/handoffs/` before starting work
2. **✍️ Update your handoff log** when completing your session
3. **📝 Add your introduction** to this README (mandatory for all agents)
4. **🔄 Update the schedule** in `comms/schedule.md` when starting/finishing
5. **🏷️ Use conventional commits** for all changes
6. **💬 Post Slack notifications** at session start and end
7. **📋 Follow your assigned task** for the current rotation

### Best Practices

- **Be concise** - Optimize for the next agent understanding
- **Use consistent formatting** - Follow templates in CONTRIBUTING.md
- **Reference previous work** - Link to specific commits, files, or handoff logs
- **Ask questions** - Add to `docs/QUESTIONS.md` when unsure
- **Document decisions** - Record final answers in `docs/DECISIONS.md`
- **Use Slack** - For urgent coordination and notifications

---

## Current Schedule

See **[comms/schedule.md](comms/schedule.md)** for the current agent rotation schedule.

---

## Agent Introductions

### Abbey
- **Role**: Coordinator / Human Facilitator
- **Specialties**: workflow-design, project-initialization, coordination
- **Last Active**: 2026-09-09T14:00:00Z
- **Next Agent**: Orion
- **Handoff Status**: ✅ Complete - Manual morning kickoff, set bootstrap day plan
- **Notes**: Day 1 coordinator. Human-facilitated planning session only.
- **Slack**: @Abbey

### Orion
- **Role**: Project Scout
- **Specialties**: workflow-design, research, project-initialization
- **Last Active**: 2026-09-10T15:30:00Z
- **Next Agent**: Aurora
- **Handoff Status**: ✅ Complete
- **Notes**: Created docs/PROJECT_BRIEF.md with 3 candidate niches
- **Slack**: @Orion

### Aurora
- **Role**: Style Guide Architect
- **Specialties**: technical-writing, workflow-design, documentation
- **Last Active**: 2026-09-10T17:52:59Z
- **Next Agent**: Nova
- **Handoff Status**: ✅ Complete
- **Notes**: Created docs/STYLE_GUIDE.md generic style guide
- **Slack**: @Aurora

### Nova
- **Role**: Pipeline Engineer
- **Specialties**: system-architecture, workflow-design, automation
- **Last Active**: 2026-09-11T21:39:00Z
- **Next Agent**: Aegis
- **Handoff Status**: ✅ Complete
- **Notes**: Verified docs/PIPELINE.md per D-013 review
- **Slack**: @Nova

### Aegis
- **Role**: Quality Auditor
- **Specialties**: code-review, quality-assurance, process-optimization
- **Last Active**: [To be assigned]
- **Next Agent**: Mistral
- **Handoff Status**: ⏳ Pending
- **Notes**: Task: Audit Orion/Aurora/Nova output, update DECISIONS.md
- **Slack**: @Aegis

### Mistral
- **Role**: Scout (Dry Run)
- **Specialties**: research, content-curation, workflow-design
- **Last Active**: [To be assigned]
- **Next Agent**: Vibe
- **Handoff Status**: ⏳ Pending
- **Notes**: Task: Dry-run Scout role using PIPELINE.md queue format
- **Slack**: @Mistral

### Vibe
- **Role**: Consolidator
- **Specialties**: project-initialization, workflow-design, coordination
- **Last Active**: [To be assigned]
- **Next Agent**: [To be assigned]
- **Handoff Status**: ⏳ Pending
- **Notes**: Task: Consolidate day, prepare brief for Abbey
- **Slack**: @Vibe

### rezurrector
- **Role**: [To be assigned]
- **Specialties**: [To be assigned]
- **Last Active**: [To be assigned]
- **Next Agent**: [To be assigned]
- **Handoff Status**: ⏳ Pending
- **Notes**: [To be assigned]
- **Slack**: @rezurrector

---

## Quick Start for New Agents

### Step 1: Choose Your Unique Name
**Your name is already chosen** - Use the name assigned to you from the list above.

### Step 2: Join Slack Channel
**MANDATORY:** Join [#multi-agent-handoff](https://mistral-bpa7715.slack.com/archives/C0C0CB8J0J1) on Slack
- Post introduction: `👋 [Your-Name] joining the workflow`
- Add your Slack @username to your README introduction

### Step 3: Clone and Review
```bash
git clone https://github.com/lilabbey/multi-agent-handoff-test.git
cd multi-agent-handoff-test
```

### Step 4: Set Up Your Profile
```bash
# Create directory with YOUR unique name (no Agent-N prefix!)
mkdir -p agents/[Your-Unique-Name]
touch agents/[Your-Unique-Name]/profile.md
```

### Step 5: Add Your Introduction
Edit `README.md` and add your introduction **above** existing entries using the template.

**IMPORTANT:** Use your unique name ONLY (e.g., "Orion", NOT "Agent-2" or "Agent-2-Orion")

### Step 6: Update Schedule
Edit `comms/schedule.md` and:
- Add your row to the rotation table
- Use your **unique name** in Agent Name column (no Agent-N prefix!)
- Set status to `⏳ Pending`
- Add your Slack @username in the Slack column

### Step 7: Do Your Work
Follow your assigned task for the current rotation

### Step 8: Create Handoff Log
Create `comms/handoffs/YYYY-MM-DD-[Your-Unique-Name]-[description].md` with all required sections.

**IMPORTANT:** Use your unique name in filename

### Step 9: Commit and Push
```bash
git add .
git commit -m "type(scope): your commit message"
git push origin main
```

---

## Handoff Checklist

Before finishing your session:

- [ ] Previous agents handoff log reviewed
- [ ] Current work status documented
- [ ] Next steps clearly defined for following agent
- [ ] All modified files listed with changes
- [ ] Questions for next agent noted in handoff log
- [ ] Time estimates for remaining tasks
- [ ] README introduction added/updated (**with unique name only!**)
- [ ] Schedule status updated (**with unique name only!**)
- [ ] Slack notifications posted (start and end)
- [ ] Commit message follows conventional commits

---

## Predefined Specialty Tags

Use these standardized tags for your **Specialties** in README introductions:

### Technical
- `project-initialization`
- `workflow-design`
- `github-integration`
- `code-review`
- `testing`
- `documentation`
- `system-architecture`
- `automation`
- `slack-integration`

### Domain
- `frontend-development`
- `backend-development`
- `fullstack-development`
- `devops`
- `data-analysis`
- `machine-learning`
- `api-design`
- `content-curation`

### Process
- `technical-writing`
- `process-optimization`
- `quality-assurance`
- `coordination`
- `research`
- `team-communication`

---

## Contact and Coordination

### For Urgent Issues
- **Post in** [#multi-agent-handoff Slack channel](https://mistral-bpa7715.slack.com/archives/C0C0CB8J0J1)
- **Create a GitHub Issue** in this repository
- **Tag relevant agents** in issue comments (use unique names!)
- **Reference specific handoff logs** or commits

### For Questions
- **Add to** `docs/QUESTIONS.md`
- **Discuss** in GitHub Discussions
- **Ask in** #multi-agent-handoff Slack channel

### For Decisions
- **Record in** `docs/DECISIONS.md`

---

## Repository Statistics

- **Created**: 2026-09-08
- **Purpose**: Multi-agent workflow testing
- **Status**: Bootstrap Day Continued (2026-09-11)
- **Agents**: 9 agents with unique names
- **Handoffs**: 7+ handoff logs
- **Slack**: #multi-agent-handoff channel active

---

## License

This repository is for internal testing and coordination purposes only.

---

*Last updated: 2026-09-11T07:00:00Z*
*Slack channel: #multi-agent-handoff*
*Timezone: America/Denver (MT, UTC-6)*
