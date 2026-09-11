# Quick Reference Guide for All Agents

## Current Status

Mode: Bootstrap (NOT Production)
Graduation: NOT CLEARED - Awaiting Abbey's review
Priority: Complete bootstrap deliverables and clear graduation criteria

---

## Key Documents

### Core Documentation (READ FIRST)
1. AGENT_PROMPT.md - Main workflow instructions for all agents
2. GRADUATION.md - Graduation criteria and current status
3. PROJECT_BRIEF.md - 3 candidate niches (awaiting Abbey's selection)
4. STYLE_GUIDE.md - Writing and formatting standards
5. PIPELINE.md - Pipeline data model and workflow

### Supporting Documentation
- CHECKLIST.md - Per-session checklist
- CONTRIBUTING.md - Contribution guidelines
- COORDINATOR_PROMPT.md - Coordinator-specific instructions
- DECISIONS.md - Decision log
- TESTING.md - Pipeline testing guide
- PIPELINE_VALIDATION.md - Validation checklist for Nova
- AUDIT_CHECKLIST.md - Audit checklist for Aegis
- BOOTSTRAP_SUMMARY.md - Complete bootstrap phase summary

### Directory Documentation
- data/README.md - Data directory structure
- content/README.md - Content directory structure

---

## Agent Rotation

Order | Agent | Slot (MT) | Slot (UTC) | Status | Next Task
-----|-------|-----------|------------|--------|-----------
1 | Abbey | Manual | Manual | Complete | Select niche
2 | Orion | 12-1 AM | 06-07 | Complete | Done
3 | Aurora | 1-2 AM | 07-08 | Complete | Done
4 | D-008 | 2-3 AM | 08-09 | In Progress | Creating infrastructure
5 | Nova | 3-4 AM | 09-10 | REDO REQUIRED | Validate PIPELINE.md
6 | Aegis | 4-5 AM | 10-11 | Pending | Audit deliverables
7 | Mistral | 5-6 AM | 11-12 | Pending | Dry-run Scout
8 | Vibe | 6-7 AM | 12-13 | Pending | Consolidate day
9 | rezurrector | Standby | Standby | Pending | -

---

## Critical Path (P0)

### Blocking Production Mode
1. Nova: Validate PIPELINE.md
   - Use: PIPELINE_VALIDATION.md
   - Output: Validated PIPELINE.md
   
2. Aegis: Audit all bootstrap deliverables
   - Use: AUDIT_CHECKLIST.md
   - Output: Audit report
   
3. Abbey: Select niche and clear GRADUATION.md
   - Use: PROJECT_BRIEF.md
   - Output: Selected niche, cleared graduation

### Enabling Production Mode
Once GRADUATION.md is cleared:
- Scout role can begin
- Writer role can begin
- Editor role can begin
- Publisher role can begin

---

## File Locations

### Documentation
- All docs: docs/
- Agent profiles: agents/Name/profile.md
- Schedule: comms/schedule.md
- Handoff logs: comms/handoffs/

### Pipeline Files
- Queue files: data/queue-name-queue.md
- Content: content/niche/files.md

### Sample Data
- Sample topic: content/AI-Agent-Dev/2026-09-11-multi-agent-workflows.md
- Sample draft: content/AI-Agent-Dev/drafts/2026-09-11-multi-agent-workflows-draft.md
- Sample review: content/AI-Agent-Dev/reviews/2026-09-11-multi-agent-workflows-review.md
- Sample published: content/AI-Agent-Dev/published/2026-09-11-multi-agent-workflows-published.md

---

## What Each Agent Should Do Now

### Abbey
- Review PROJECT_BRIEF.md and select a niche
- Review all bootstrap deliverables
- Clear GRADUATION.md when ready

### Orion
- Standby - All work complete

### Aurora
- Standby - All work complete (awaiting niche selection for finalization)

### D-008 (Current)
- Continue creating infrastructure and documentation
- Standardize queue formats
- Create sample data for testing
- Prepare for production mode

### Nova
- Review PIPELINE.md using PIPELINE_VALIDATION.md
- Validate all aspects of the pipeline
- Update PIPELINE.md status to Validated
- Update schedule status to Complete

### Aegis
- Wait for PIPELINE.md validation
- Audit all bootstrap deliverables using AUDIT_CHECKLIST.md
- Document findings in handoff log

### Mistral
- Wait for PIPELINE.md validation
- Dry-run Scout role using TESTING.md
- Test topic creation and queue updates

### Vibe
- Wait for audit and dry-run completion
- Consolidate bootstrap day
- Prepare brief for Abbey

### rezurrector
- Standby

---

## Slack Notifications

Channel: #multi-agent-handoff (ID: C0C0CB8J0J1)

When to Post:
- Session start: 🔄 [Name] starting session - [action]
- Session end: ✅ [Name] session complete - [summary]
- Blocked: ❌ [Name] BLOCKED: [reason]
- Question: ❓ [Name] needs help: [question]

---

## Conventional Commits

Format: type(scope): subject

Types: feat, fix, docs, style, refactor, chore, test

Scopes: readme, schedule, handoff, profile, agents, comms, docs, workflow, queue, content

Examples:
- feat(pipeline): add complete PIPELINE.md data model
- docs(readme): add D-008 introduction
- chore(schedule): add D-008 to rotation

---

## Key Decisions

- D-008: Use unique names without numeric prefixes
- D-009: Slack integration mandatory
- D-010: Only Abbey can clear GRADUATION.md

---

## Bootstrap Progress

### Infrastructure
- [x] Niche proposed (3 candidates)
- [x] Style guide created (generic)
- [x] Pipeline data model defined
- [x] Queue file formats standardized
- [x] All agent profiles created
- [x] All agent introductions added

### Process
- [x] Role pipeline defined
- [x] Role responsibilities clear
- [x] Handoff log template standardized
- [x] Schedule rotation working
- [x] Slack notifications integrated

### Quality
- [x] Content standards defined
- [ ] Review rubric established
- [x] Blocked/failure protocols documented
- [x] Decision logging process working

---

## Quick Links

- Repository: https://github.com/lilabbey/multi-agent-handoff-test
- Slack: https://mistral-bpa7715.slack.com/archives/C0C0CB8J0J1
- AGENT_PROMPT.md: Main workflow instructions
- GRADUATION.md: Graduation criteria

---

Last Updated: 2026-09-11T09:15:00Z
Maintained By: D-008