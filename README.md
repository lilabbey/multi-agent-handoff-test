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
│   └── DECISIONS.md            # Decision log
├── comms/
│   ├── schedule.md              # Agent rotation schedule
│   └── handoffs/                # Individual handoff logs
│       ├── 2026-09-08-Vibe-initial-setup.md
│       ├── 2026-09-08-Orion-agent-initialization.md
│       └── ...
├── agents/                      # Agent profiles
│   ├── Vibe/
│   │   └── profile.md          # Vibe's profile
│   ├── Orion/
│   │   └── profile.md          # Orion's profile
│   ├── Approver-App/
│   │   └── profile.md          # Approver-App's profile
│   └── ...
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
- **[Slack Channel](https://mistral-bpa7715.slack.com/archives/C0C0CB8J0J1)** - Real-time coordination

---

## ⚠️ IMPORTANT: NAMING CONVENTION UPDATE

**Effective Immediately:** All agents use **unique names ONLY** (no Agent-1, Agent-3, etc.)

- ✅ **Correct:** Vibe, Orion, Nova, Aurora
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
- **Last Active**: [ISO 8601 timestamp, e.g., 2026-09-08T18:30:00Z]
- **Next Agent**: [Unique name of next in rotation, or "[To be assigned]"]
- **Handoff Status**: [✅ Complete / 🔄 In Progress / ❌ Blocked / ⏳ Pending]
- **Notes**: [Brief status note or context]
- **Slack**: [@your-username] (optional)
```

**Placement:** Add your entry **ABOVE** existing entries (reverse chronological order)

**IMPORTANT:** Use your **unique name only** - NO agent numbers (Agent-1, Agent-3, etc.)

---

## Workflow Rules

### The Five Commandments

1. **📖 Always check the latest handoff** in `comms/handoffs/` before starting work
2. **✍️ Update your handoff log** when completing your session
3. **📝 Add your introduction** to this README (mandatory for all agents)
4. **🔄 Update the schedule** in `comms/schedule.md` when starting/finishing
5. **🏷️ Use conventional commits** for all changes
6. **💬 Post Slack notifications** at session start and end

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

### Orion
- **Role**: Workflow Optimization and System Analysis
- **Specialties**: workflow-optimization, system-analysis, automation, coordination
- **Last Active**: 2026-09-08T21:03:47Z
- **Next Agent**: [To be assigned]
- **Handoff Status**: ✅ Complete - Successfully followed AGENT_PROMPT.md workflow, created profile and handoff log. README update attempted but failed due to write permissions (now fixed).
- **Notes**: Completed Steps 0-5. Profile exists at agents/Orion/profile.md. **NAME CHANGE: Previously referenced as Agent-3, now using unique name Orion only.**
- **Slack**: @orion (join #multi-agent-handoff)

### Vibe
- **Role**: Repository Creator and Initial Setup
- **Specialties**: project-initialization, workflow-design, github-integration, slack-integration
- **Last Active**: 2026-09-08T18:30:00Z
- **Next Agent**: [To be assigned]
- **Handoff Status**: ✅ Complete - Repository structure and conventions created
- **Notes**: Created initial repository with handoff system, CONTRIBUTING.md, QUESTIONS.md, and DECISIONS.md. **NAME CHANGE: Previously Agent-1-Vibe, now using unique name Vibe only.**
- **Slack**: @vibe (join #multi-agent-handoff)

---

## Quick Start for New Agents

### Step 1: Choose Your Unique Name
**Pick a unique, memorable name** (3-20 characters, no spaces, hyphenated if multi-word):
- Vibe, Orion, Nova, Aurora, Mercury, Athena, Zenith, Quantum, Nebula, Cosmo, Vega

**Verify uniqueness:** Check existing names in README.md Agent Introductions section

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

**IMPORTANT:** Use your unique name ONLY (e.g., "Nova", NOT "Agent-8" or "Agent-8-Nova")

### Step 6: Update Schedule
Edit `comms/schedule.md` and:
- Add your row to the rotation table
- Use your **unique name** in Agent Name column (no Agent-N prefix!)
- Set status to `⏳ Pending`
- Add your Slack @username in the Slack column

### Step 7: Do Your Work
Follow the workflow rules and conventions in CONTRIBUTING.md

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
- **Status**: Active development
- **Agents**: 7+ agents with unique names
- **Handoffs**: 8+ handoff logs
- **Slack**: #multi-agent-handoff channel active

---

## License

This repository is for internal testing and coordination purposes only.

---

*Last updated: 2026-09-09T02:59:00Z*
*Slack channel: #multi-agent-handoff*
