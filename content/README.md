# Content Directory

## Overview
This directory contains all content files for the multi-agent content pipeline, organized by niche.

---

## Directory Structure

content/
- {niche}/
  - {YYYY-MM-DD}-{slug}.md - Topic files
  - drafts/
    - {YYYY-MM-DD}-{slug}-draft.md - Draft files
  - reviews/
    - {YYYY-MM-DD}-{slug}-review.md - Review files
  - published/
    - {YYYY-MM-DD}-{slug}-published.md - Published files

---

## File Types

### Topic Files
- Location: content/{niche}/{YYYY-MM-DD}-{slug}.md
- Format: YAML frontmatter + Markdown content
- Contains: Topic metadata and research notes
- Created by: Scout role
- Status values: pending, researching, approved, rejected, completed

### Draft Files
- Location: content/{niche}/drafts/{YYYY-MM-DD}-{slug}-draft.md
- Format: YAML frontmatter + Markdown content
- Contains: Article draft following STYLE_GUIDE.md
- Created by: Writer role
- Status values: outline, drafting, review_ready, in_review, approved, rejected

### Review Files
- Location: content/{niche}/reviews/{YYYY-MM-DD}-{slug}-review.md
- Format: YAML frontmatter + Markdown content
- Contains: Review feedback and comments
- Created by: Editor role
- Status values: pending, in_progress, approved, rejected

### Published Files
- Location: content/{niche}/published/{YYYY-MM-DD}-{slug}-published.md
- Format: YAML frontmatter + Markdown content
- Contains: Published content with metadata
- Created by: Publisher role
- Status values: scheduled, published, promoted, archived

---

## Niche Structure

Each niche has its own subdirectory under content/. The niche name should match one of the niches defined in docs/PROJECT_BRIEF.md:

- AI-Agent-Dev (AI Agent Development and Workflow Automation)
- Open-Source-Biz (Sustainable Open-Source Business Models)
- Dev-Productivity (Developer Productivity and Workflow Optimization)

Note: Niche selection is pending Abbey's decision. Currently using AI-Agent-Dev for sample data.

---

## File Naming Convention

All content files follow this naming pattern:
- Topics: {YYYY}-{MM}-{DD}-{slug}.md
- Drafts: {YYYY}-{MM}-{DD}-{slug}-draft.md
- Reviews: {YYYY}-{MM}-{DD}-{slug}-review.md
- Published: {YYYY}-{MM}-{DD}-{slug}-published.md

Where:
- YYYY: 4-digit year
- MM: 2-digit month
- DD: 2-digit day
- slug: URL-friendly title (lowercase, hyphens for spaces)

---

## Sample Data

Sample content files have been created in content/AI-Agent-Dev/ to test the pipeline:
- content/AI-Agent-Dev/2026-09-11-multi-agent-workflows.md
- content/AI-Agent-Dev/drafts/2026-09-11-multi-agent-workflows-draft.md
- content/AI-Agent-Dev/reviews/2026-09-11-multi-agent-workflows-review.md
- content/AI-Agent-Dev/published/2026-09-11-multi-agent-workflows-published.md

---

## Traceability

All content files are linked through trace_id:
- Topic file has trace_id
- Draft file references the same trace_id
- Review file references the same trace_id
- Published file references the same trace_id

This allows tracking the complete lifecycle of a content piece.

---

## Maintenance

- Create new niche directories as needed (after Abbey selects niches)
- Follow the naming conventions for all files
- Keep YAML frontmatter consistent with PIPELINE.md specifications
- Update related queue files when creating or modifying content files

---

Last Updated: 2026-09-11T09:13:00Z
Maintained By: All Agents