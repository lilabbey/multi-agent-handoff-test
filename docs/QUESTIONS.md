# Open Questions and Agent Opinions

## Purpose
This document tracks all unresolved questions, opinions, and discussions from agents to ensure nothing is lost between handoffs.

---

## How to Use This Document

1. Add questions when you encounter ambiguity
2. Propose options for each question
3. Mark status (Open / In Discussion / Resolved)
4. Record resolution when decided
5. Move resolved items to DECISIONS.md

---

## Resolved Questions (Moved to DECISIONS.md)

The following questions have been resolved and documented in DECISIONS.md:

### Naming Conventions
- Q1: Agent Naming Standard -> RESOLVED by D-008 (Use unique names without numeric prefixes)
- Q2: Agent ID in Directories -> RESOLVED by D-001 (agents/[Unique-Name]/profile.md)

### Workflow Rules
- Q4: Handoff Frequency -> RESOLVED by D-004 (One handoff log per session)
- Q5: README Update Requirement -> RESOLVED by D-003 (MANDATORY for all agents)
- Q6: Schedule Update Timing -> RESOLVED by D-006 (Update at start and end of each session)

### Documentation Standards
- Q7: Markdown Formatting -> RESOLVED by D-004 (Per-session logs, standardized format)
- Q8: ASCII Art in README -> RESOLVED by D-005 (Use code blocks for consistent rendering)

### Technical Decisions
- Q10: Commit Squashing -> RESOLVED by D-002 (Use Conventional Commits specification)

### Specialty Tags
- Q3: Specialty Tags -> RESOLVED by D-007 (Use 2-3 comma-separated keywords from predefined list)

### Branch Strategy
- Q9: Branch Strategy -> RESOLVED by repository rules (Changes must be made through pull requests)
  - Current practice: Create feature branches, use PRs to main

---

## Open Questions

### Bootstrap Phase

#### Q11: Niche Selection
- Q: Which of the 3 proposed niches should be selected as primary?
  - Context: Orion created PROJECT_BRIEF.md with 3 candidates, awaiting Abbey decision
  - Options:
    - A) Niche 1: AI Agent Development and Workflow Automation
    - B) Niche 2: Sustainable Open-Source Business Models
    - C) Niche 3: Developer Productivity and Workflow Optimization
  - Recommendation: Niche 1 (best alignment with team expertise)
  - Proposed By: D-008
  - Status: Open - Awaiting Abbey decision

#### Q12: STYLE_GUIDE.md Finalization
- Q: Should STYLE_GUIDE.md remain generic or be adapted for the selected niche?
  - Context: Aurora created generic style guide, needs niche-specific adaptations
  - Options:
    - A) Keep generic (adaptable to any niche)
    - B) Adapt for selected niche
    - C) Create niche-specific version
  - Proposed By: D-008
  - Status: Open - Depends on Q11 (niche selection)

### D-013 Compliance

#### Q13: Documentation File Validation
- Q: Should the retained documentation files from D-008 sessions be treated as validated?
  - Context: D-013 states files were created out-of-scope and need review/reassignment
  - Files: TESTING.md, PIPELINE_VALIDATION.md, AUDIT_CHECKLIST.md, QUICK_REFERENCE.md, BOOTSTRAP_SUMMARY.md
  - Options:
    - A) Treat as validated (ready for use)
    - B) Require review by intended owners
    - C) Require complete rewrite by intended owners
  - Proposed By: D-008
  - Status: Open

---

## Agent Opinions and Feedback

### Workflow Preferences
- D-008: Prefers systematic, documentation-first approach. Focused on unblocking critical path.
- Vibe: Prefers systematic, documentation-first approach. Likes comprehensive handoff logs.

### Pain Points
- D-008: D-013 regression created uncertainty about file validation status.
- Vibe: ASCII tree in README not readable in some viewers.

### Suggestions for Improvement
- D-008:
  - Ensure all decisions are clearly documented in DECISIONS.md
  - Maintain clear critical path visibility
  - Use conventional commits consistently
- Vibe:
  - Add conventional commit guidelines
  - Create decision log for tracking
  - Standardize agent profile format

---

## Decision Log Reference
For resolved questions, see: DECISIONS.md
For graduation criteria, see: GRADUATION.md

---

## Template for New Questions

#### Q[Number]: [Brief Question]
- Q: [Detailed question]
  - Context: [Why this matters]
  - Options:
    - A) [Option 1]
    - B) [Option 2]
  - Proposed By: [Agent Name]
  - Status: Open

---
*Last updated: 2026-09-12T09:35:00Z*