# Decision Log

## Purpose
This document records all final decisions made by the agent team to maintain a single source of truth for workflow conventions and standards.

---

## 📋 Decision Format

```markdown
## [D-00X] - [Brief Decision Title]
- **Date**: YYYY-MM-DD
- **Decision**: [What was decided]
- **Rationale**: [Why this decision was made]
- **Proposed By**: [Agent Name]
- **Agreed By**: [Agent Names]
- **Related Questions**: [Links to QUESTIONS.md items]
- **Impact**: [What changes as a result]
- **Status**: Active / Superseded / Deprecated
```

---

## 📜 Active Decisions

### Repository Structure

#### D-001 - Standardize Agent Profile Directory Structure
- **Date**: 2026-09-08
- **Decision**: All agent profiles will use the format `agents/[Unique-Name]/profile.md`
- **Rationale**: Consistent structure makes it easy to find and manage agent profiles. The Unique-Name should follow the naming convention defined in CONTRIBUTING.md (no Agent-N prefixes).
- **Proposed By**: Vibe
- **Agreed By**: Orion, Submitter App
- **Related Questions**: Q1, Q2
- **Impact**: All agent profiles must be moved to match this structure with unique names only
- **Status**: Active

#### D-002 - Use Conventional Commits
- **Date**: 2026-09-08
- **Decision**: All commits must follow the Conventional Commits specification as outlined in CONTRIBUTING.md
- **Rationale**: Standardized commit messages enable better history tracking, automated changelog generation, and easier understanding of changes.
- **Proposed By**: Vibe
- **Agreed By**: Orion, Submitter App
- **Related Questions**: Q9, Q10
- **Impact**: All future commits must use the format: `type(scope): subject`
- **Status**: Active

#### D-003 - Mandatory README Introductions
- **Date**: 2026-09-08
- **Decision**: All agents MUST add their introduction to README.md when joining the rotation or completing their first handoff
- **Rationale**: Centralized agent directory helps with discoverability and understanding team composition. The README serves as the primary entry point.
- **Proposed By**: Vibe
- **Agreed By**: Orion, Submitter App
- **Related Questions**: Q5
- **Impact**: Agents who have not added introductions should do so immediately using their unique name only
- **Status**: Active

#### D-004 - Handoff Log Per Session
- **Date**: 2026-09-08
- **Decision**: Agents must create one handoff log per session (not per task)
- **Rationale**: Per-session logs provide better continuity and reduce overhead. Task-level detail can be included within the session log.
- **Proposed By**: Vibe
- **Agreed By**: Orion, Submitter App
- **Related Questions**: Q4
- **Impact**: Agents should consolidate multiple task updates into a single session handoff log
- **Status**: Active

#### D-005 - Fix README ASCII Tree
- **Date**: 2026-09-08
- **Decision**: Repository structure in README uses code blocks for consistent rendering
- **Rationale**: Code blocks render consistently across all GitHub viewers and markdown parsers.
- **Proposed By**: Vibe
- **Agreed By**: Orion, Submitter App
- **Related Questions**: Q8
- **Impact**: README.md structure visualization now uses code blocks
- **Status**: Active

#### D-006 - Schedule Update Timing
- **Date**: 2026-09-08
- **Decision**: Agents must update their status in schedule.md when starting (In Progress) and when finishing (Complete)
- **Rationale**: Real-time status tracking enables better coordination and reduces confusion about who is currently active.
- **Proposed By**: Vibe
- **Agreed By**: Orion, Submitter App
- **Related Questions**: Q6
- **Impact**: Agents should update schedule at start and end of each session
- **Status**: Active

#### D-007 - Standardize Specialty Format
- **Date**: 2026-09-08
- **Decision**: Specialties in README use 2-3 comma-separated keywords from the predefined list in CONTRIBUTING.md
- **Rationale**: Consistent specialty tags enable better agent matching and skill discovery across the team.
- **Proposed By**: Vibe
- **Agreed By**: Orion, Submitter App
- **Related Questions**: Q3
- **Impact**: Predefined specialty list is maintained in README.md and CONTRIBUTING.md
- **Status**: Active

### Naming Conventions

#### D-008 - Use Unique Names Without Numeric Prefixes
- **Date**: 2026-09-08
- **Decision**: **ALL AGENTS MUST USE UNIQUE NAMES WITHOUT "Agent-N" PREFIXES**
- **Rationale**: Simpler, more memorable, avoids confusion when agents join/leave rotation. Numeric prefixes (Agent-1, Agent-3, etc.) cause inconsistency and make it harder to reference agents.
- **Proposed By**: Vibe
- **Agreed By**: Orion, Submitter App
- **Related Questions**: Q1 from Orion's handoff
- **Impact**: 
  - All agent directories use format: `agents/[Unique-Name]/` (e.g., `agents/Orion/`, NOT `agents/Agent-3/`)
  - All README introductions use format: `### [Unique-Name]` (e.g., `### Orion`, NOT `### Agent-3 - Orion`)
  - All schedule entries use format: `[Unique-Name]` in Agent Name column (e.g., `Orion`, NOT `Agent-3`)
  - All handoff log filenames use format: `YYYY-MM-DD-[Unique-Name]-[description].md` (e.g., `2026-09-08-Orion-initialization.md`, NOT `2026-09-08-Agent-3-Orion-...`)
  - All existing references to Agent-1, Agent-3, etc. have been updated to use unique names only
- **Status**: **ACTIVE - EFFECTIVE IMMEDIATELY**

### Communication

#### D-009 - Slack Integration for Real-Time Coordination
- **Date**: 2026-09-09
- **Decision**: All agents MUST use Slack channel #multi-agent-handoff for real-time coordination and notifications
- **Rationale**: Faster communication, better team awareness, immediate notifications for session start/end
- **Proposed By**: Abbey
- **Agreed By**: All agents
- **Related Questions**: None
- **Impact**: 
  - Session start notification mandatory: `🔄 [Name] starting [time]`
  - Session end notification mandatory: `✅ [Name] complete [time] - [summary]`
  - All agents must join channel: #multi-agent-handoff (C0C0CB8J0J1)
  - Channel link: https://mistral-bpa7715.slack.com/archives/C0C0CB8J0J1
- **Status**: **ACTIVE - EFFECTIVE IMMEDIATELY**

#### D-010 - Graduation Criteria
- **Date**: 2026-09-09
- **Decision**: Only Abbey (human coordinator) can clear graduation criteria to move from bootstrap to production mode
- **Rationale**: Human oversight required for production readiness and niche selection
- **Proposed By**: Abbey
- **Agreed By**: All agents
- **Related Questions**: None
- **Impact**: 
  - No agent can declare graduation
  - Only Abbey can update docs/GRADUATION.md to "CLEARED"
  - Bootstrap mode continues until Abbey's morning review
- **Status**: **ACTIVE - EFFECTIVE IMMEDIATELY**

### Workflow

#### D-011 - Bootstrap Day Protocol
- **Date**: 2026-09-09
- **Decision**: Day 1 (2026-09-09) is Bootstrap Day - scaffold only, no content production
- **Rationale**: Infrastructure must be established before content creation
- **Proposed By**: Abbey
- **Agreed By**: All agents
- **Related Questions**: None
- **Impact**: 
  - Today's tasks: PROJECT_BRIEF.md, STYLE_GUIDE.md, PIPELINE.md, audit, dry-run
  - No drafting or publishing of actual content
  - No niche decision by agents (Abbey decides)
  - All work is infrastructure/scaffold only
- **Status**: **ACTIVE - TODAY ONLY**

---

## ⏭️ Superseded Decisions

*None yet*

---

## 🗑️ Deprecated Decisions

*None yet*

---

## 🔍 Decision Index

| ID | Title | Date | Status | Category |
|----|-------|------|--------|----------|
| D-001 | Standardize Agent Profile Directory Structure | 2026-09-08 | Active | Repository |
| D-002 | Use Conventional Commits | 2026-09-08 | Active | Git |
| D-003 | Mandatory README Introductions | 2026-09-08 | Active | Documentation |
| D-004 | Handoff Log Per Session | 2026-09-08 | Active | Workflow |
| D-005 | Fix README ASCII Tree | 2026-09-08 | Active | Documentation |
| D-006 | Schedule Update Timing | 2026-09-08 | Active | Workflow |
| D-007 | Standardize Specialty Format | 2026-09-08 | Active | Documentation |
| D-008 | **Use Unique Names Without Numeric Prefixes** | 2026-09-08 | **Active** | **Naming** |
| D-009 | **Slack Integration for Real-Time Coordination** | 2026-09-09 | **Active** | **Communication** |
| D-010 | **Graduation Criteria** | 2026-09-09 | **Active** | **Workflow** |
| D-011 | **Bootstrap Day Protocol** | 2026-09-09 | **Active** | **Workflow** |

---

## 📝 Template for New Decisions

```markdown
## [D-XXX] - [Brief Decision Title]
- **Date**: YYYY-MM-DD
- **Decision**: [What was decided]
- **Rationale**: [Why this decision was made]
- **Proposed By**: [Agent Name]
- **Agreed By**: [Agent Names]
- **Related Questions**: [Q1, Q2, etc.]
- **Impact**: [What changes as a result]
- **Status**: Active
```

---

## 🔗 Related Documents

- [CONTRIBUTING.md](../CONTRIBUTING.md) - Workflow conventions and standards
- [QUESTIONS.md](./QUESTIONS.md) - Open questions and opinions
- [GRADUATION.md](../GRADUATION.md) - Production readiness criteria

---

## 📌 IMPORTANT NOTICE FOR ALL AGENTS

**D-008 IS NOW IN EFFECT:**

Starting immediately, **ALL agents must use unique names WITHOUT numeric prefixes**.

**DO NOT USE:**
- Agent-1, Agent-2, Agent-3, etc.
- Agent-1-Vibe, Agent-3-Orion, etc.

**USE INSTEAD:**
- Abbey, Orion, Aurora, Nova, Aegis, Mistral, Vibe, rezurrector

This applies to:
- Directory names: `agents/Abbey/` NOT `agents/Agent-1/`
- README introductions: `### Abbey` NOT `### Agent-1 - Abbey`
- Schedule entries: `Abbey` NOT `Agent-1`
- Handoff filenames: `2026-09-09-Abbey-kickoff.md` NOT `2026-09-09-Agent-1-kickoff.md`

**All existing files have been updated to reflect this change.**

---

*Last updated: 2026-09-09T20:25:00Z*

## D-013: Overnight D-008 Regression — Scope Correction

- **Date**: 2026-09-11
- **Decision**: The account operating overnight under 2026-09-11 (mistakenly
  self-identifying as "D-008," a decision ID, not a valid agent per D-008)
  created five queue data files with real sample pipeline content
  (topics/drafts/reviews/research/final) despite docs/GRADUATION.md being
  NOT CLEARED. That sample data has been stripped — queue files reset to
  empty structure only. Five documentation files it also created
  (AUDIT_CHECKLIST.md, PIPELINE_VALIDATION.md, TESTING.md, QUICK_REFERENCE.md,
  BOOTSTRAP_SUMMARY.md) are retained as scaffolding but were created
  out-of-scope (not the creating account's assigned task) and should be
  reviewed/reassigned to their intended owners, not treated as validated.
- **Rationale**: GRADUATION.md's block on content production only has
  teeth if violations are actually reverted, not just documented.
- **Status**: Active
