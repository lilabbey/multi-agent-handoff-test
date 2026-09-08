# AGENT HANDOFF WORKFLOW

## YOUR MISSION
You are an autonomous agent. Choose your own unique name (e.g., Orion, Vibe, Claude).

## STEP 0: CHOOSE YOUR NAME (First time)
Pick a unique name: Orion, Vibe, Claude, Nova, Athena, Mercury, Zenith
- Unique across all agents
- No spaces (use hyphens: My-Name)
- 3-20 characters

## STEP 1: INITIALIZE (First time only)
1. Create profile: mkdir -p agents/[Your-Name]
2. Create agents/[Your-Name]/profile.md
3. Add introduction to README.md ABOVE existing entries

## STEP 2: CHECK STATE
1. Read latest handoff: ls -t comms/handoffs/*.md | head -1 | xargs cat
2. Review comms/schedule.md
3. Check docs/QUESTIONS.md
4. Review docs/DECISIONS.md

## STEP 3: UPDATE SCHEDULE
In comms/schedule.md: Change your Status to In Progress

## STEP 4: DO WORK
Perform your assigned task.

## STEP 5: CREATE HANDOFF LOG
File: comms/handoffs/YYYY-MM-DD-[Your-Name]-[description].md

Required sections:
- Metadata (Agent, Date, Time, Next Agent, Status)
- Summary
- Work Completed
- Next Steps (Priority 1, 2, 3)
- Files Modified
- Questions for Next Agent
- Time Tracking

## STEP 6: UPDATE SCHEDULE
Change your Status to Complete

## STEP 7: COMMIT
git add .
git commit -m "type(scope): description"
git push origin main

Types: feat, fix, docs, style, refactor, chore, test
Scopes: readme, schedule, handoff, profile, agents, comms, docs, workflow

## STEP 8: VERIFY
- README.md has my introduction
- agents/[Name]/profile.md exists
- comms/handoffs/ has my log
- schedule is updated
- commit follows conventional commits

## RULES
1. ALWAYS check latest handoff before starting
2. ALWAYS create handoff log when done
3. ALWAYS add introduction to README (first time)
4. ALWAYS update schedule status
5. ALWAYS use conventional commits
6. NEVER leave questions unanswered - add to QUESTIONS.md
7. NEVER make decisions alone - record in DECISIONS.md

## RESOURCES
- CONTRIBUTING.md - Conventions
- CHECKLIST.md - Per-session checklist
- docs/QUESTIONS.md - Open questions
- docs/DECISIONS.md - Decisions
- comms/schedule.md - Schedule

## NEED HELP?
- Read CONTRIBUTING.md
- Check QUESTIONS.md
- Create GitHub Issue
- Tag next agent

---
*Follow these instructions exactly.*