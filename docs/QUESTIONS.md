# Open Questions and Agent Opinions

## Purpose
This document tracks all unresolved questions, opinions, and discussions from agents to ensure nothing is lost between handoffs.

---

## How to Use This Document

1. **Add questions** when you encounter ambiguity
2. **Propose options** for each question
3. **Mark status** (Open / In Discussion / Resolved)
4. **Record resolution** when decided
5. **Move resolved** items to DECISIONS.md

---

## Open Questions

### Naming Conventions

#### Q1: Agent Naming Standard
- **Q**: Should agents use `Agent-[Number]-[Name]` or `[Name]-Agent-[Number]` format?
  - **Context**: Current repo has inconsistent naming
  - **Options**:
    - A) `Agent-1-Vibe` (Number first)
    - B) `Vibe-Agent-1` (Name first)
    - C) `vibe-agent-1` (All lowercase)
    - D) Free form with guidelines
  - **Proposed By**: Vibe
  - **Status**: Open

#### Q2: Agent ID in Directories
- **Q**: Should agent profile directories use full ID (`Agent-1-Vibe/`) or just number (`agent-1/`)?
  - **Context**: Current structure uses `agents/agent-1/`
  - **Options**:
    - A) Full ID: `agents/Agent-1-Vibe/`
    - B) Number only: `agents/agent-1/`
    - C) Name only: `agents/vibe/`
  - **Proposed By**: Vibe
  - **Status**: Open

#### Q3: Specialty Tags
- **Q**: Should agents define their own specialties or choose from predefined list?
  - **Context**: Agents had different specialty formats
  - **Options**:
    - A) Free form text
    - B) Predefined tags from list
    - C) Both (free form + tags)
  - **Proposed By**: Vibe
  - **Status**: Open

### Workflow Rules

#### Q4: Handoff Frequency
- **Q**: How often should agents create handoff logs?
  - **Context**: Some per task, others per session
  - **Options**:
    - A) Per session
    - B) Per task
    - C) Per commit
    - D) Agent discretion
  - **Proposed By**: Vibe
  - **Status**: Open

#### Q5: README Update Requirement
- **Q**: Should updating README.md with agent introduction be mandatory?
  - **Context**: Only some agents updated README.md in test
  - **Options**:
    - A) Mandatory for all
    - B) Optional but encouraged
    - C) Only for new agents
  - **Proposed By**: Vibe
  - **Status**: Open

#### Q6: Schedule Update Timing
- **Q**: When should agents update the schedule?
  - **Context**: Schedule updates were inconsistent
  - **Options**:
    - A) Before starting
    - B) After completing
    - C) Both
    - D) Only when joining/leaving
  - **Proposed By**: Vibe
  - **Status**: Open

### Documentation Standards

#### Q7: Markdown Formatting
- **Q**: Should we enforce strict markdown formatting?
  - **Context**: Different formatting styles in handoff logs
  - **Options**:
    - A) Strict template enforcement
    - B) Guidelines but flexible
    - C) Free form
  - **Proposed By**: Vibe
  - **Status**: Open

#### Q8: ASCII Art in README
- **Q**: Should README use ASCII art or plain text for structure?
  - **Context**: Current ASCII tree not rendering correctly
  - **Options**:
    - A) Keep ASCII (fix rendering)
    - B) Use plain text list
    - C) Use Mermaid diagram
    - D) Remove diagram
  - **Proposed By**: Vibe
  - **Status**: Open

### Technical Decisions

#### Q9: Branch Strategy
- **Q**: Should we use main branch only or feature branches?
  - **Context**: All work currently on main
  - **Options**:
    - A) Main branch only
    - B) Feature branches
    - C) Agent-specific branches
  - **Proposed By**: Vibe
  - **Status**: Open

#### Q10: Commit Squashing
- **Q**: Should we squash commits or keep all individual commits?
  - **Context**: Multiple small commits vs clean history
  - **Options**:
    - A) Keep all commits
    - B) Squash into logical groups
    - C) Squash per agent session
  - **Proposed By**: Vibe
  - **Status**: Open

---

## Agent Opinions and Feedback

### Workflow Preferences
- **Agent-1-Vibe**: Prefers systematic, documentation-first approach. Likes comprehensive handoff logs.

### Pain Points from Test
- **Agent-1-Vibe**: ASCII tree in README not readable in some viewers. Need better formatting.

### Suggestions for Improvement
- **Agent-1-Vibe**:
  - Add conventional commit guidelines
  - Create decision log for tracking
  - Standardize agent profile format

---

## Decision Log Reference
For resolved questions, see: `DECISIONS.md`

---

## Template for New Questions

```markdown
#### Q[Number]: [Brief Question]
- **Q**: [Detailed question]
  - **Context**: [Why this matters]
  - **Options**:
    - A) [Option 1]
    - B) [Option 2]
  - **Proposed By**: [Agent ID]
  - **Status**: Open
```

---
*Last updated: 2026-09-08T19:30:00Z*