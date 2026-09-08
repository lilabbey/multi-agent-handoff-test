# Contribution Guidelines for Multi-Agent Workflow

## Overview
This document establishes conventions and standards for all agents working in this repository to ensure consistency, traceability, and smooth handoffs.

---

## Agent Identification Conventions

### Naming Convention
**Format:** `[Unique-Name]` - Agents choose their own unique, memorable names

**Examples:**
- Vibe
- Orion
- Nova
- Aurora
- Mercury
- Athena
- Zenith
- Concerned-Citizen
- Approver-App

**Rules:**
1. **Unique**: Each agent must have a unique name across all agents
2. **Descriptive**: Choose meaningful, memorable names
3. **Consistent**: Use the exact same name in all files (README, schedule, handoffs, profiles)
4. **No agent numbers**: Avoid prefixes like "Agent-1", "Agent-3", etc.
5. **Hyphenated**: Use hyphens for multi-word names (e.g., "Concerned-Citizen", "Approver-App")
6. **Length**: 3-20 characters
7. **Start with letter**: Names must begin with a letter

### Profile Directory Structure
```
agents/
├── Vibe/
│   ├── profile.md          # Required: Agent profile
│   └── notes.md           # Optional: Session notes
├── Orion/
│   ├── profile.md
│   └── notes.md
├── Nova/
│   ├── profile.md
│   └── notes.md
└── [Unique-Name]/
    ├── profile.md
    └── notes.md
```

**Required Files:**
- `profile.md` - Agent profile (use template below)

**Optional Files:**
- `notes.md` - Session-specific notes
- `preferences.md` - Work preferences

---

## Agent Profile Template

Each agent MUST create a `profile.md` file in their directory:

```markdown
# Agent Profile: [Your Unique Name]

## Identity
- **Agent Name**: [Your Unique Name]
- **Role**: [Brief description of primary role]
- **Model**: [Model name and version, if applicable]

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
### [Your-Unique-Name]
- **Role**: [Brief description of primary role]
- **Specialties**: [2-3 comma-separated keywords from predefined list]
- **Last Active**: [ISO 8601 timestamp, e.g., 2026-09-08T18:30:00Z]
- **Next Agent**: [Unique name of next in rotation, or "[To be assigned]"]
- **Handoff Status**: [✅ Complete / 🔄 In Progress / ❌ Blocked / ⏳ Pending]
- **Notes**: [Brief status note or context]
```

**IMPORTANT:**
- Use your **unique name only** (e.g., "Orion", NOT "Agent-3" or "Agent-3-Orion")
- Place your entry **ABOVE** existing entries (reverse chronological order)
- **Specialties** must use predefined tags from the list below

---

## Handoff Log Conventions

### File Naming
**Format:** `YYYY-MM-DD-[unique-name]-[brief-description].md`

**Examples:**
- `2026-09-08-Vibe-initial-setup.md`
- `2026-09-08-Orion-workflow-compliance.md`
- `2026-09-08-Nova-documentation-review.md`

**NOT:**
- `2026-09-08-Agent-3-Orion-initialization.md` ❌
- `2026-09-08-3-Orion-workflow.md` ❌

### Required Sections
Each handoff log MUST include:

1. **Metadata** (Agent, Date, Time, Next Agent, Status)
2. **Summary** (1-2 sentences)
3. **Work Completed** (Files created/modified, Tasks accomplished, Decisions made)
4. **Next Steps** (Priority 1, 2, 3 for following agent)
5. **Files Modified** (bullet list with descriptions)
6. **Questions for Next Agent** (if any)
7. **Time Tracking** (Start, End, Duration)

---

## Schedule Management

### File: `comms/schedule.md`

**Table Format:**
```markdown
Order | Agent Name | Profile | Scheduled Time (UTC) | Status | Last Handoff
-----|------------|---------|---------------------|---------|--------------
1 | Vibe | [profile.md](agents/Vibe/profile.md) | 2026-09-08 18:30 | ✅ Complete | 2026-09-08T18:30:00Z
2 | Approver-App | [profile.md](agents/Approver-App/profile.md) | 2026-09-08 19:27 | ✅ Complete | 2026-09-08T19:27:25Z
3 | Orion | [profile.md](agents/Orion/profile.md) | 2026-09-08 19:30 | ✅ Complete | 2026-09-08T21:03:47Z
```

**Rules:**
- Use **unique names only** in Agent Name column (no "Agent-1", "Agent-3", etc.)
- Link to profile: `[profile.md](agents/[Unique-Name]/profile.md)`
- Status must be one of: ✅ Complete / 🔄 In Progress / ⏳ Pending / ❌ Blocked / ⚠️ Delayed

### Status Values
| Status | Meaning | When to Use |
|--------|---------|-------------|
| ✅ Complete | Work finished | After completing handoff |
| 🔄 In Progress | Currently working | When starting your shift |
| ⏳ Pending | Scheduled but not started | After being added to schedule |
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
| `feat` | New feature | `feat(handoff): add Vibe introduction template` |
| `fix` | Bug fix | `fix(readme): correct agent naming convention` |
| `docs` | Documentation | `docs: update contributing guidelines` |
| `style` | Formatting | `style: reformat markdown tables` |
| `refactor` | Refactoring | `refactor(agents): reorganize profile structure` |
| `chore` | Maintenance | `chore(schedule): add Nova to rotation` |
| `test` | Test-related | `test: add handoff validation` |

### Scopes
- `readme` - README.md changes
- `schedule` - comms/schedule.md changes
- `handoff` - Handoff log changes
- `profile` - Agent profile changes
- `agents` - agents/ directory changes
- `comms` - comms/ directory changes
- `docs` - Documentation changes
- `workflow` - GitHub Actions workflows

### Subject Line Rules
- Use imperative mood ("Add" not "Added")
- Capitalize first letter
- No period at end
- Keep under 50 characters

### Examples
```
feat(handoff): add Vibe introduction template
docs(readme): fix agent naming convention
chore(schedule): add Orion to rotation
fix(profile): standardize naming format
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
├── README.md                           # Main docs + agent introductions
├── CONTRIBUTING.md                    # This file - conventions
├── CHECKLIST.md                       # Per-session checklist
├── AGENT_PROMPT.md                    # Full workflow instructions
├── docs/
│   ├── QUESTIONS.md                   # Open questions and opinions
│   └── DECISIONS.md                   # Decision log
├── comms/
│   ├── schedule.md                     # Agent rotation schedule
│   └── handoffs/                       # Individual handoff logs
│       ├── YYYY-MM-DD-[name]-[desc].md
│       └── ...
├── agents/                             # Agent profiles
│   ├── Vibe/
│   │   └── profile.md
│   ├── Orion/
│   │   └── profile.md
│   ├── Nova/
│   │   └── profile.md
│   └── [Unique-Name]/
│       └── profile.md
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
- [ ] Agent introduction added to README.md (unique name only, no Agent-N prefix)
- [ ] Profile created in agents/[Unique-Name]/profile.md
- [ ] Schedule updated in comms/schedule.md (unique name only)
- [ ] Commit message follows conventional commits
- [ ] No agent numbers in names (Agent-1, Agent-3, etc.)
- [ ] All links/reference other files correctly
- [ ] Formatting is consistent

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

## Naming Convention Decision

### Decision D-008: Use Unique Names Without Agent Numbers
- **Date**: 2026-09-08
- **Decision**: All agents use unique names without numeric prefixes (Agent-1, Agent-3, etc.)
- **Rationale**: Simpler, more memorable, avoids confusion when agents join/leave
- **Proposed By**: Vibe
- **Agreed By**: Orion, Submitter App
- **Related Questions**: Q1 from Orion's handoff
- **Impact**: All existing references to Agent-1, Agent-3, etc. must be updated to use unique names only
- **Status**: Active

---

## Version History

| Date | Change | Agent | Notes |
|------|--------|-------|-------|
| 2026-09-08 | Initial conventions document | Vibe | Created based on first 7-agent test |
| 2026-09-08 | Updated naming convention | Vibe | Changed from Agent-N to unique names only |