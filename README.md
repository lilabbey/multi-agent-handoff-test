# Multi-Agent Handoff Test Repository

## Purpose
This repository facilitates coordinated workflow between multiple Google profile agents working on shared projects. Each agent introduces themselves, logs their handoffs, and maintains continuity for the next agent in schedule.

## Repository Structure

```
multi-agent-handoff-test/
├── README.md                    # This file - agent introductions
├── CONTRIBUTING.md             # Conventions and standards
├── docs/
│   ├── QUESTIONS.md            # Open questions and opinions
│   └── DECISIONS.md            # Decision log
├── comms/
│   ├── schedule.md              # Agent rotation schedule
│   └── handoffs/                # Individual handoff logs
│       ├── 2026-09-08-Agent-1-Vibe-initial-setup.md
│       └── ...
├── agents/                      # Agent profiles
│   ├── Agent-1-Vibe/
│   │   └── profile.md          # Agent profile
│   ├── Agent-2/
│   │   └── profile.md
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

---

## Agent Introduction Template

Each agent MUST add their introduction under the **Agent Introductions** section below.

### Format:
```markdown
### [Agent-ID] - [Agent Name]
- **Role**: [Brief description of primary role]
- **Specialties**: [2-3 comma-separated keywords from predefined list]
- **Last Active**: [ISO 8601 timestamp, e.g., 2026-09-08T18:30:00Z]
- **Next Agent**: [Agent-ID of next in rotation, or "[To be assigned]"]
- **Handoff Status**: [✅ Complete / 🔄 In Progress / ❌ Blocked / ⏳ Pending]
- **Notes**: [Brief status note or context]
```

**Placement:** Add your entry **ABOVE** existing entries (reverse chronological order)

---

## Workflow Rules

### The Five Commandments

1. **📖 Always check the latest handoff** in `comms/handoffs/` before starting work
2. **✍️ Update your handoff log** when completing your session
3. **📝 Add your introduction** to this README (mandatory for all agents)
4. **🔄 Update the schedule** in `comms/schedule.md` when starting/finishing
5. **🏷️ Use conventional commits** for all changes (see CONTRIBUTING.md)

### Best Practices

- **Be concise** - Optimize for the next agent understanding
- **Use consistent formatting** - Follow templates in CONTRIBUTING.md
- **Reference previous work** - Link to specific commits, files, or handoff logs
- **Ask questions** - Add to `docs/QUESTIONS.md` when unsure
- **Document decisions** - Record final answers in `docs/DECISIONS.md`

---

## Current Schedule

See **[comms/schedule.md](comms/schedule.md)** for the current agent rotation schedule.

---

## Agent Introductions

### Agent-1 - Vibe
- **Role**: Repository Creator and Initial Setup
- **Specialties**: project-initialization, workflow-design, github-integration
- **Last Active**: 2026-09-08T18:30:00Z
- **Next Agent**: [To be assigned]
- **Handoff Status**: ✅ Complete - Repository structure and conventions created
- **Notes**: Created initial repository with handoff system, CONTRIBUTING.md, QUESTIONS.md, and DECISIONS.md. Next agent should review all docs and add introduction above.

---

## Quick Start for New Agents

### Step 1: Clone and Review
```bash
git clone https://github.com/lilabbey/multi-agent-handoff-test.git
cd multi-agent-handoff-test
```

### Step 2: Read Current State
- Review latest handoff in `comms/handoffs/`
- Read `comms/schedule.md` for rotation
- Check `docs/QUESTIONS.md` for open items
- Review `docs/DECISIONS.md` for standards

### Step 3: Set Up Your Profile
```bash
mkdir -p agents/[Your-Agent-ID]
touch agents/[Your-Agent-ID]/profile.md
```

### Step 4: Add Your Introduction
Edit `README.md` and add your introduction **above** existing entries using the template.

### Step 5: Update Schedule
Edit `comms/schedule.md` and:
- Add your row to the rotation table
- Set status to `🔄 In Progress` when starting
- Update to `✅ Complete` when finishing

### Step 6: Do Your Work
Follow the workflow rules and conventions in CONTRIBUTING.md

### Step 7: Create Handoff Log
Create `comms/handoffs/YYYY-MM-DD-[Agent-ID]-[description].md` with all required sections.

### Step 8: Commit and Push
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
- [ ] README introduction added/updated
- [ ] Schedule status updated
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

---

## Contact and Coordination

### For Urgent Issues
- **Create a GitHub Issue** in this repository
- **Tag relevant agents** in issue comments
- **Reference specific handoff logs** or commits

### For Questions
- **Add to** `docs/QUESTIONS.md`
- **Discuss** in GitHub Discussions

### For Decisions
- **Record in** `docs/DECISIONS.md`

---

## Repository Statistics

- **Created**: 2026-09-08
- **Purpose**: Multi-agent workflow testing
- **Status**: Active development

---

## License

This repository is for internal testing and coordination purposes only.

---

*Last updated: 2026-09-08T19:30:00Z*