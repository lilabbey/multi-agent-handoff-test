# Pipeline Testing Guide

> **⚠️ UNVALIDATED per D-013**: This file was created out-of-scope by an account operating under the invalid "D-008" identity, not by its intended owner. Content has not been reviewed. Treat as a draft only until reviewed and re-issued by the actual assigned agent.

## Purpose
This document provides instructions for testing the multi-agent content pipeline with the sample data created by D-008.

---

## Test Environment

### Sample Data Created
D-008 has created a complete set of sample data to test the pipeline end-to-end:

**Queue Files:**
- data/topics-queue.md - Contains sample topic TP-20260911-001
- data/research-queue.md - Contains approved topic ready for Writer
- data/drafts-queue.md - Contains sample draft DR-20260911-001
- data/reviews-queue.md - Contains sample review RV-20260911-001
- data/final-queue.md - Contains sample final PB-20260911-001

**Content Files:**
- content/AI-Agent-Dev/2026-09-11-multi-agent-workflows.md - Sample topic
- content/AI-Agent-Dev/drafts/2026-09-11-multi-agent-workflows-draft.md - Sample draft
- content/AI-Agent-Dev/reviews/2026-09-11-multi-agent-workflows-review.md - Sample review
- content/AI-Agent-Dev/published/2026-09-11-multi-agent-workflows-published.md - Sample published

---

## Testing Instructions

### For Mistral (Scout Role Dry-Run)

1. Review PIPELINE.md
   - Read the complete document
   - Understand the Scout role responsibilities
   - Review the data structures and queue formats

2. Test Topic Creation
   - Create a new topic file in content/AI-Agent-Dev/
   - Follow the YAML frontmatter format from PIPELINE.md
   - Generate a new trace_id (use TR-{UUID} format)
   - Add the topic to data/topics-queue.md

3. Test Queue Updates
   - Move the topic from topics-queue to research-queue
   - Update the status from pending to approved
   - Verify the trace_id propagates correctly

4. Verify Data Integrity
   - Check that all queue files are in the correct format
   - Verify that content files match their queue entries
   - Confirm that trace_id is consistent across all related files

---

## Expected Results

After successful testing:
- All queue files contain valid Markdown tables
- All content files have proper YAML frontmatter
- Trace IDs are consistent across all stages
- Queue formats match the specifications in PIPELINE.md
- No errors when parsing queue files

---

## Issues and Questions

If you encounter any issues during testing:
1. Check that all files exist in the correct locations
2. Verify that YAML frontmatter is properly formatted
3. Ensure that trace_id values are consistent
4. Refer to PIPELINE.md for the correct formats
5. Add questions to docs/QUESTIONS.md

---

## Test Data Summary

| Stage | ID | File | Queue | Status |
|-------|-----|------|-------|--------|
| Topic | TP-20260911-001 | content/AI-Agent-Dev/2026-09-11-multi-agent-workflows.md | topics-queue.md | pending |
| Topic | TP-20260911-001 | - | research-queue.md | approved |
| Draft | DR-20260911-001 | content/AI-Agent-Dev/drafts/2026-09-11-multi-agent-workflows-draft.md | drafts-queue.md | outline |
| Review | RV-20260911-001 | content/AI-Agent-Dev/reviews/2026-09-11-multi-agent-workflows-review.md | reviews-queue.md | pending |
| Final | PB-20260911-001 | content/AI-Agent-Dev/published/2026-09-11-multi-agent-workflows-published.md | final-queue.md | scheduled |

---

## Next Steps

1. Mistral: Perform dry-run of Scout role using this test data
2. Aegis: Audit the pipeline and sample data
3. Nova: Validate PIPELINE.md (can now be completed with test data available)
4. Abbey: Review and clear GRADUATION.md once all criteria are met

---

Created: 2026-09-11T09:12:00Z
Created By: [unvalidated, see D-013]
Status: Ready for Testing