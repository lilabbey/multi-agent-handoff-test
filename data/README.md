# Data Directory

## Overview
This directory contains queue files and working data for the multi-agent content pipeline.

---

## Directory Structure

data/
- topics-queue.md - Queue of topics to be researched
- research-queue.md - Queue of approved topics ready for writing
- drafts-queue.md - Queue of drafts ready for editing
- reviews-queue.md - Queue of reviews ready for publishing
- final-queue.md - Queue of final content ready for publication

---

## Queue Files

All queue files follow the same format:

### Frontmatter (YAML)
- queue_type: Type of queue (topics, research, drafts, reviews, final)
- total_count: Number of items in the queue
- last_updated: Timestamp of last update (ISO 8601 format)
- updated_by: Name of the agent who last updated the queue

### Content (Markdown Table)
- Each queue has a specific set of columns based on the data model
- All tables include: Order, ID, Title, Status, Assigned To, Updated
- Additional columns vary by queue type

---

## Queue File Specifications

### topics-queue.md
Contains topics that need to be researched by the Scout role.

Columns: Order, Topic ID, Title, Status, Priority, Assigned To, Created, Niche

Status values: pending, researching, approved, rejected, completed

### research-queue.md
Contains topics that have been approved and are ready for the Writer role.

Columns: Order, Topic ID, Title, Status, Assigned To, Word Count, Updated

Status values: approved

### drafts-queue.md
Contains drafts that are ready for the Editor role.

Columns: Order, Draft ID, Topic ID, Title, Status, Assigned To, Word Count, Version, Updated

Status values: outline, drafting, review_ready, in_review, approved, rejected

### reviews-queue.md
Contains reviews that are ready for the Publisher role.

Columns: Order, Review ID, Draft ID, Title, Status, Reviewer, Issues, Updated

Status values: pending, in_progress, approved, rejected

### final-queue.md
Contains final content that is ready for publication.

Columns: Order, Review ID, Draft ID, Title, Status, Assigned To, Updated

Status values: scheduled, published, promoted, archived

---

## Sample Data

Sample data has been created to test the pipeline:
- Topic: TP-20260911-001
- Draft: DR-20260911-001
- Review: RV-20260911-001
- Published: PB-20260911-001

See docs/TESTING.md for instructions on testing the pipeline.

---

## Maintenance

- Queue files should be updated by the respective agents when items move between stages
- Always update the last_updated timestamp and updated_by field when modifying a queue
- Keep total_count accurate
- Use consistent formatting for all queue files

---

Last Updated: 2026-09-11T09:13:00Z
Maintained By: All Agents