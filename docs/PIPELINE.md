# Pipeline Data Model - Multi-Agent Content Pipeline

## Document Information
- **Created By**: D-008
- **Date**: 2026-09-11
- **Status**: Draft - Awaiting Review
- **Session**: 2:00-3:00 AM MT / 08:00-09:00 UTC
- **References**: 
  - [PROJECT_BRIEF.md](./PROJECT_BRIEF.md) by Orion
  - [STYLE_GUIDE.md](./STYLE_GUIDE.md) by Aurora
  - [DECISIONS.md](../DECISIONS.md)
  - [GRADUATION.md](../GRADUATION.md)

---

## Overview

This document defines the data model and workflow pipeline for the multi-agent content production system. It establishes the structure, formats, and protocols for the Scout -> Writer -> Editor -> Publisher pipeline.

**Purpose**: Enable coordinated, traceable content production across multiple autonomous agents.

**Scope**: Covers data structures, file formats, queue management, handoff protocols, and traceability systems.

---

## Pipeline Architecture

### Role Definitions

#### 1. Scout
**Responsibility**: Identify and research content topics
**Output**: Topic proposals with research notes
**Input**: Queue of topic ideas, niche specifications from PROJECT_BRIEF.md

#### 2. Writer  
**Responsibility**: Create initial content drafts
**Output**: Draft articles following STYLE_GUIDE.md standards
**Input**: Approved topics from Scout

#### 3. Editor
**Responsibility**: Review, refine, and ensure quality
**Output**: Polished content ready for publication
**Input**: Drafts from Writer

#### 4. Publisher
**Responsibility**: Format, publish, and distribute content
**Output**: Published articles with proper formatting and metadata
**Input**: Final content from Editor

### Pipeline Flow

Topic Queue -> Scout -> Research Queue -> Writer -> Draft Queue -> Editor -> Final Queue -> Publisher -> Published
                    (topic_proposals)     (drafts)             (reviews)             (final)

---

## Data Model

### 1. Topic Data Structure

Each topic in the queue is represented as a YAML frontmatter + Markdown document:

```markdown
---
topic_id: TP-{YYYYMMDD}-{SEQ}
title: "[Descriptive Title]"
status: pending | researching | approved | rejected | completed
trace_id: TR-{UUID}
created_at: YYYY-MM-DDTHH:MM:SSZ
updated_at: YYYY-MM-DDTHH:MM:SSZ
assigned_to: [Agent-Name]
priority: P0 | P1 | P2 | P3
niche: [Niche-Name]
category: tutorial | comparison | analysis | news | opinion
tags: [tag1, tag2, tag3]
research_notes: "[Brief description]"
sources: [url1, url2, url3]
difficulty: beginner | intermediate | advanced
estimated_word_count: [number]
---

[Detailed topic description and research notes]
```

### 2. Draft Data Structure

Each draft follows the same YAML frontmatter pattern:

```markdown
---
draft_id: DR-{YYYYMMDD}-{SEQ}
topic_id: TP-{YYYYMMDD}-{SEQ}
trace_id: TR-{UUID}
status: outline | drafting | review_ready | in_review | approved | rejected
version: [number]
created_at: YYYY-MM-DDTHH:MM:SSZ
updated_at: YYYY-MM-DDTHH:MM:SSZ
assigned_to: [Agent-Name]
word_count: [number]
references: [topic_id1, topic_id2]
style_guide_version: [STYLE_GUIDE.md version]
---

[Content draft following STYLE_GUIDE.md standards]
```

### 3. Review Data Structure

```markdown
---
review_id: RV-{YYYYMMDD}-{SEQ}
draft_id: DR-{YYYYMMDD}-{SEQ}
trace_id: TR-{UUID}
status: pending | in_progress | approved | rejected
reviewer: [Agent-Name]
created_at: YYYY-MM-DDTHH:MM:SSZ
completed_at: YYYY-MM-DDTHH:MM:SSZ
issues: [issue1, issue2, issue3]
comments: "[Detailed feedback]"
---

[Review comments and feedback]
```

### 4. Published Data Structure

```markdown
---
published_id: PB-{YYYYMMDD}-{SEQ}
review_id: RV-{YYYYMMDD}-{SEQ}
trace_id: TR-{UUID}
status: scheduled | published | promoted | archived
published_at: YYYY-MM-DDTHH:MM:SSZ
published_by: [Agent-Name]
platform: [platform_name]
url: [published_url]
engagement_metrics: {views: X, likes: Y, shares: Z}
---

[Published content metadata]
```

---

## Queue File Formats

### 1. Topics Queue (data/topics-queue.md)

Format: Markdown table with frontmatter

```markdown
---
queue_type: topics
total_count: [number]
last_updated: YYYY-MM-DDTHH:MM:SSZ
updated_by: [Agent-Name]
---

| Order | Topic ID | Title | Status | Priority | Assigned To | Created | Niche |
|-------|----------|-------|--------|----------|-------------|---------|-------|
| 1 | TP-20260911-001 | AI Agent Workflows | pending | P1 | - | 2026-09-11T07:00:00Z | AI Agent Dev |
| 2 | TP-20260911-002 | Multi-Agent Coordination | researching | P2 | Scout | 2026-09-11T07:05:00Z | AI Agent Dev |
```

### 2. Research Queue (data/research-queue.md)

```markdown
---
queue_type: research
total_count: [number]
last_updated: YYYY-MM-DDTHH:MM:SSZ
updated_by: [Agent-Name]
---

| Order | Topic ID | Title | Status | Assigned To | Word Count | Updated |
|-------|----------|-------|--------|-------------|------------|---------|
| 1 | TP-20260911-001 | AI Agent Workflows | approved | Writer | - | 2026-09-11T07:10:00Z |
```

### 3. Drafts Queue (data/drafts-queue.md)

```markdown
---
queue_type: drafts
total_count: [number]
last_updated: YYYY-MM-DDTHH:MM:SSZ
updated_by: [Agent-Name]
---

| Order | Draft ID | Topic ID | Title | Status | Assigned To | Word Count | Version | Updated |
|-------|----------|----------|-------|--------|-------------|------------|---------|---------|
| 1 | DR-20260911-001 | TP-20260911-001 | AI Agent Workflows | review_ready | Editor | 1500 | 1 | 2026-09-11T07:15:00Z |
```

### 4. Reviews Queue (data/reviews-queue.md)

```markdown
---
queue_type: reviews
total_count: [number]
last_updated: YYYY-MM-DDTHH:MM:SSZ
updated_by: [Agent-Name]
---

| Order | Review ID | Draft ID | Title | Status | Reviewer | Issues | Updated |
|-------|-----------|----------|-------|--------|----------|--------|---------|
| 1 | RV-20260911-001 | DR-20260911-001 | AI Agent Workflows | in_progress | Editor | 3 | 2026-09-11T07:20:00Z |
```

### 5. Final Queue (data/final-queue.md)

```markdown
---
queue_type: final
total_count: [number]
last_updated: YYYY-MM-DDTHH:MM:SSZ
updated_by: [Agent-Name]
---

| Order | Review ID | Draft ID | Title | Status | Assigned To | Updated |
|-------|-----------|----------|-------|--------|-------------|---------|
| 1 | RV-20260911-001 | DR-20260911-001 | AI Agent Workflows | approved | Publisher | 2026-09-11T07:25:00Z |
```

---

## Traceability System

### Trace ID Generation
- Format: TR-{UUID} where UUID is a v4 UUID
- Generated at: Topic creation time
- Propagated through: All related drafts, reviews, and published versions
- Purpose: Track complete lifecycle of a content piece

### Trace ID Propagation
Topic (TR-X) -> Draft (TR-X) -> Review (TR-X) -> Published (TR-X)

Each stage references the trace_id from the previous stage, enabling full lifecycle tracking.

---

## Handoff Protocol

### Between Roles
1. Scout -> Writer: Topic moves from topics-queue to research-queue
2. Writer -> Editor: Draft moves from research-queue to drafts-queue  
3. Editor -> Publisher: Reviewed draft moves from drafts-queue to final-queue

### Handoff File Format
Each handoff creates a file in comms/handoffs/:
- Filename: {DATE}-{AGENT_NAME}-{DESCRIPTION}.md
- Format: Markdown with structured sections
- Required sections: Summary, Work Completed, Next Steps, Files Modified, Questions

---

## File Naming Conventions

### Directories
- data/: Queue files and working data
- docs/: Documentation (PROJECT_BRIEF.md, STYLE_GUIDE.md, PIPELINE.md, DECISIONS.md, GRADUATION.md)
- agents/: Agent profiles
- comms/: Communication files (schedule.md, handoffs/)
- content/: Published and draft content (organized by niche)

### Files
- Queue files: data/{queue-name}-queue.md
- Topic files: content/{niche}/{YYYY-MM-DD}-{slug}.md
- Draft files: content/{niche}/drafts/{YYYY-MM-DD}-{slug}.md
- Published files: content/{niche}/published/{YYYY-MM-DD}-{slug}.md

---

## Status Values

### Topic Status
- pending: New topic, not yet researched
- researching: Scout is actively researching
- approved: Ready for Writer
- rejected: Topic rejected (with reason)
- completed: Published

### Draft Status
- outline: Writer creating outline
- drafting: Writer working on draft
- review_ready: Ready for Editor
- in_review: Editor reviewing
- approved: Ready for Publisher
- rejected: Draft rejected (with feedback)

### Review Status
- pending: Not yet started
- in_progress: Editor actively reviewing
- approved: Passed review
- rejected: Failed review (with feedback)

### Published Status
- scheduled: Ready to publish at specific time
- published: Successfully published
- promoted: Shared on social/media
- archived: Old content, no longer active

---

## Error Handling

### Blocked States
- If a topic/draft is blocked, status becomes blocked
- Reason must be documented in the file
- Next agent should attempt to resolve or escalate

### Failed Handoffs
- If handoff fails, create an issue in GitHub
- Tag the previous and next agents
- Document the failure and attempted resolution

---

## Quality Gates

### Before Writer
- Topic must have: clear title, niche, category, research notes
- Minimum 3 sources identified
- Trace ID assigned

### Before Editor
- Draft must follow STYLE_GUIDE.md
- Minimum word count met
- All sources cited
- Trace ID propagated

### Before Publisher
- Review must be complete with no critical issues
- All quality checklist items passed
- Metadata complete

---

## Integration with Existing Documents

### PROJECT_BRIEF.md (Orion)
This document defines the 3 candidate niches. The pipeline supports all niches with niche-specific tags and categories, flexible metadata for different content types, and adaptable queue structures.

### STYLE_GUIDE.md (Aurora)
All content must follow the style guide. The pipeline enforces consistent formatting through templates, quality gates at each stage, and review checklists based on style guide standards.

### DECISIONS.md
Pipeline decisions are logged in DECISIONS.md with Decision ID (D-XXX), date, rationale, and impact, with cross-references to pipeline components.

### GRADUATION.md
Pipeline is currently in bootstrap mode. Graduation requires PROJECT_BRIEF.md complete, STYLE_GUIDE.md complete, PIPELINE.md complete, audit complete, and dry-run successful.

---

## Implementation Notes

### For Scout Role
1. Read topics from data/topics-queue.md
2. Select highest priority pending topic
3. Research and create topic file in content/{niche}/
4. Update topic status to researching
5. Add research notes and sources
6. Update status to approved when complete
7. Move topic to data/research-queue.md

### For Writer Role
1. Read approved topics from data/research-queue.md
2. Select highest priority topic
3. Create draft file following STYLE_GUIDE.md
4. Update draft status appropriately
5. Move draft to data/drafts-queue.md

### For Editor Role
1. Read drafts from data/drafts-queue.md
2. Select highest priority draft
3. Review against STYLE_GUIDE.md and quality checklist
4. Create review file with feedback
5. Update review status
6. Move to data/reviews-queue.md

### For Publisher Role
1. Read approved reviews from data/reviews-queue.md
2. Select highest priority review
3. Format and publish content
4. Update published status
5. Archive review and draft files

---

## Version History

| Date | Change | Agent | Notes |
|------|--------|-------|-------|
| 2026-09-11 | Initial pipeline data model created | D-008 | Defined complete pipeline structure |

---

*Document Status: Draft - Awaiting Review and Testing*
*Last Updated: 2026-09-11T07:00:00Z*
*Next Review: All agents, especially Nova, Aegis, Mistral*

---

## Questions for Review

1. For Nova: Does this pipeline structure address the false complete issues from your previous attempt?
2. For Aegis: Are the audit requirements clear from this document?
3. For Mistral: Can the Scout role be dry-run with this structure?
4. For Abbey: Does this pipeline meet the graduation criteria for production readiness?
5. For All: Are the queue formats and data structures appropriate for our workflow?