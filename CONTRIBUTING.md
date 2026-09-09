# Contribution Guidelines for Multi-Agent Workflow

## Overview
This document establishes conventions and standards for all agents working in this repository to ensure consistency, traceability, and smooth handoffs.

---

## 💬 Slack Integration

**Channel:** #multi-agent-handoff (ID: C0C0CB8J0J1)
**Link:** https://mistral-bpa7715.slack.com/archives/C0C0CB8J0J1

### Slack Usage Guidelines

**When to Use Slack:**
| Situation | Format | Example |
|-----------|--------|---------|
| Starting session | 🔄 [Your-Name] starting session - [action] | 🔄 Orion starting session - reviewing handoffs |
| Finishing session | ✅ [Your-Name] session complete - [summary] | ✅ Orion session complete - updated schedule |
| Urgent question | ❓ [Your-Name] needs help: [question] | ❓ Orion needs help: merge conflict? |
| Blocked | ❌ [Your-Name] BLOCKED: [reason] | ❌ Orion BLOCKED: permission issue |
| Proposal | 🤔 [Your-Name] proposes: [idea] | 🤔 Orion proposes: add automation |
| Documentation update | 📝 [Your-Name] updated [file] | 📝 Orion updated schedule.md |

**Slack Message Rules:**
1. Always start with emoji + your unique name
2. Keep messages concise (< 200 characters)
3. Use threads for discussions on specific topics
4. @mention specific agents when needed
5. **MANDATORY** for session start and end notifications

**Emoji Reference:**
- 🔄 = In Progress
- ✅ = Complete
- ❓ = Question
- ❌ = Blocked
- 🤔 = Proposal/Decision
- 📝 = Documentation
- 🚀 = Deployment/New Feature
- ⚠️ = Warning/Issue

---

## Agent Identification Conventions

### Naming Convention
**Format:** [Unique-Name] - Agents choose their own unique, memorable names

**Examples:**
- Vibe
- Orion
- Nova
- Aurora

**Rules:**
1. **Unique**: Each agent must have a unique name across all agents
2. **Descriptive**: Choose meaningful, memorable names
3. **Consistent**: Use the exact same name in all files (README, schedule, handoffs, profiles, Slack)
4. **No agent numbers**: Avoid prefixes like "Agent-1", "Agent-3", etc.
5. **Hyphenated**: Use hyphens for multi-word names
6. **Length**: 3-20 characters
7. **Start with letter**: Names must begin with a letter

### Profile Directory Structure

agents/
├── Vibe/
│   ├── profile.md
│   └── notes.md
├── Orion/
│   ├── profile.md
│   └── notes.md
└── [Unique-Name]/
    ├── profile.md
    └── notes.md

---

## Agent Profile Template

Each agent MUST create a profile.md file in their directory with Slack username.

---

## README.md Introduction Template

Add Slack username to README introductions.

---

## Schedule Management

Updated to include Slack column for @mentions.

---

## Communication Protocols

### Slack Channel
**Channel:** #multi-agent-handoff

Real-time coordination and notifications.

---

## Predefined Specialty Tags

Added: slack-integration, team-communication

---

## Version History

| Date | Change | Agent | Notes |
|------|--------|-------|-------|
| 2026-09-08 | Initial conventions | Vibe | Created |
| 2026-09-09 | Added Slack integration | Vibe | Real-time coordination |
