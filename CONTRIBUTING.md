# Contribution Guidelines for Multi-Agent Workflow

## Overview
This document establishes conventions and standards for all agents working in this repository to ensure consistency, traceability, and smooth handoffs.

---

## Agent Identification Conventions

### Naming Convention
**Format:** `Agent-[Number]-[Name]`

**Examples:**
- `Agent-1-Vibe`
- `Agent-2-Claude`
- `Agent-3-Mistral`

**Rules:**
1. **Unique**: Each agent must have a unique identifier
2. **Consistent**: Use the same naming pattern throughout
3. **Descriptive**: Include agent type/model if helpful
4. **No spaces**: Use hyphens only

### Profile Directory Structure
```
agents/
├── Agent-1-Vibe/
│   ├── profile.md          # Required: Agent profile
│   └── notes.md           # Optional: Session notes
├── Agent-2-Claude/
│   ├── profile.md
│   └── notes.md
└── Agent-3-Mistral/
    ├── profile.md
    └── notes.md
```

**Required Files:**
- `profile.md` - Agent profile (see template below)

**Optional Files:**
- `notes.md` - Session-specific notes
- `preferences.md` - Work preferences

---

## Agent Profile Template

Each agent MUST create a `profile.md` file in their directory:

```markdown
# Agent Profile: [Your Name]

## Identity
- **Agent Name**: [Full Name]
- **Agent ID**: [Unique Identifier, e.g., Agent-1-Vibe]
- **Model**: [Model name and version]
- **Role**: [Primary role]

## Capabilities

### Core Competencies
- [List 3-5 primary capabilities]

### Specializations
- [List 2-3 specialized skills]

### Tools Access
- [List available tools/integrations]

## Preferences

### Work Style
- **Approach**: [Systematic, Creative, Analytical, etc.]
- **Communication**: [Concise, Detailed, Visual, etc.]
- **Focus Areas**: [What you prefer to work on]

### Collaboration
- **Handoff Style**: [Brief/Comprehensive/Detailed]
- **Documentation**: [Minimal/Standard/Thorough]
- **Feedback Style**: [Direct/Constructive/Diplomatic]

### Availability
- **Time Zone**: [UTC offset]
- **Active Hours**: [e.g., 08:00-17:00 UTC]
- **Response Time**: [Urgent/Standard/Planning]

## Workflow

### Quality Standards
- [Your standards for code/documentation]

### Daily Process
1. [Step 1]
2. [Step 2]
3. [Step 3]
```

---

## README.md Introduction Template

Each agent MUST add their introduction to `README.md` under the **Agent Introductions** section.

**Format:**
```markdown
### [Agent-ID] - [Agent Name]
- **Role**: [Brief role description]
- **Specialties**: [2-3 comma-separated keywords from predefined list]
- **Last Active**: [ISO 8601 timestamp]
- **Next Agent**: [Agent-ID or "[To be assigned]"]
- **Handoff Status**: [✅ Complete / 🔄 In Progress / ❌ Blocked / ⏳ Pending]
- **Notes**: [Brief status note]
```

**Placement:** Above existing entries (reverse chronological order)

---

## Handoff Log Conventions

### File Naming
**Format:** `YYYY-MM-DD-[agent-id]-[brief-description].md`

**Examples:**
- `2026-09-08-Agent-1-Vibe-initial-setup.md`
- `2026-09-08-Agent-2-Claude-code-review.md`

### Required Sections
Each handoff log MUST include:

1. **Metadata** (Agent, Date, Time, Next Agent, Status)
2. **Summary** (1-2 sentences)
3. **Work Completed** (Files created/modified, Tasks accomplished)
4. **Next Steps** (Priority 1, 2, 3 for following agent)
5. **Files Modified** (bullet list)
6. **Questions for Next Agent** (if any)
7. **Time Tracking** (Start, End, Duration)

---

## Schedule Management

### Status Values
| Status | Meaning | When to Use |
|--------|---------|-------------|
| ✅ Complete | Work finished | After completing handoff |
| 🔄 In Progress | Currently working | When starting shift |
| ⏳ Pending | Scheduled but not started | After being added |
| ❌ Blocked | Cannot proceed | When encountering blockers |
| ⚠️ Delayed | Will start later | When rescheduling |

---

## Git Commit Conventions (Conventional Commits)

### Format
```
type(scope): subject

body

footer
```

### Types
| Type | Usage | Example |
|------|-------|---------|
| `feat` | New feature | `feat(handoff): add agent introduction template` |
| `fix` | Bug fix | `fix(readme): correct ASCII tree formatting` |
| `docs` | Documentation | `docs: add contributing guidelines` |
| `style` | Formatting | `style: format markdown tables` |
| `refactor` | Refactoring | `refactor(agents): reorganize profile structure` |
| `chore` | Maintenance | `chore(schedule): add Agent-2 to rotation` |
| `test` | Test-related | `test: add handoff validation` |

### Scopes
- `readme` - README.md changes
- `schedule` - comms/schedule.md changes
- `handoff` - Handoff log changes
- `profile` - Agent profile changes
- `workflow` - GitHub Actions workflows
- `agents` - agents/ directory changes
- `comms` - comms/ directory changes
- `docs` - Documentation changes

### Subject Line Rules
- Use imperative mood ("Add" not "Added")
- Capitalize first letter
- No period at end
- Keep under 50 characters

### Examples
```
feat(handoff): add agent introduction template
docs(readme): fix ASCII tree rendering
docs: add contributing guidelines
chore(schedule): add Agent-2 to rotation
fix(profile): standardize agent naming convention
```

---

## Communication Protocols

### Questions and Opinions
**File:** `docs/QUESTIONS.md`

All unresolved questions, opinions, and discussions should be tracked here.

### Decision Log
**File:** `docs/DECISIONS.md`

All final decisions should be recorded here for reference.

---

## File Structure Conventions

### Directory Structure
```
multi-agent-handoff-test/
├── README.md
├── CONTRIBUTING.md
├── docs/
│   ├── QUESTIONS.md
│   └── DECISIONS.md
├── comms/
│   ├── schedule.md
│   └── handoffs/
│       └── YYYY-MM-DD-[agent-id]-[description].md
├── agents/
│   └── [Agent-ID]/
│       ├── profile.md
│       └── notes.md
└── .github/
    └── workflows/
        └── handoff-notification.yml
```

### File Naming
- **Lowercase** with hyphens
- **No spaces**
- **Descriptive** names
- **Consistent** patterns

---

## Quality Checklist

Before committing, verify:

- [ ] All required sections in handoff log
- [ ] Agent introduction added to README.md
- [ ] Profile created in agents/[id]/profile.md
- [ ] Schedule updated in comms/schedule.md
- [ ] Commit message follows conventional commits
- [ ] No sensitive data in files
- [ ] Links/reference other files correctly
- [ ] Formatting is consistent

---

## Version History

| Date | Change | Agent | Notes |
|------|--------|-------|-------|
| 2026-09-08 | Initial conventions document | Vibe | Created based on first 7-agent test |