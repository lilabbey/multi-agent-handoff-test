# CLI Assessment Protocol

Read this file in full before doing anything. This governs the daily
local architecture/repo-health assessment run by Mistral CLI, Gemini
CLI, and Grok CLI — independent of the scheduled GitHub-agent rotation
in `comms/schedule.md`. You are doing analysis, not making changes.

## Every day, in this order

1. `git pull` — make sure you're reading the current state, not stale
   local files.
2. Read: the current file tree, the latest file in `comms/handoffs/`,
   `docs/GRADUATION.md`, and `docs/DECISIONS.md`. This is your context —
   don't answer from assumption or memory of a prior day.
3. Answer the assessment question given to you inline today (it changes
   daily — this file only governs mechanics, not the question itself).
4. Open `docs/assessments/YYYY-MM-DD.md` (today's date). If it doesn't
   exist, create it using the template structure below. **Read the
   current contents first if it already exists** — another CLI may
   have already written its section today. Add your own section; never
   overwrite or edit another model's section.
5. Your section header is your own name: `### Mistral CLI`,
   `### Gemini CLI`, or `### Grok CLI`. Under it, use exactly these
   sub-headers: `Key findings`, `Recommended changes`, `Flags/concerns`.
6. **Write only to `docs/assessments/YYYY-MM-DD.md`.** Do not touch
   `AGENT_PROMPT.md`, anything in `comms/`, anything in `agents/`, or
   `docs/DECISIONS.md`/`docs/GRADUATION.md`. If you think one of those
   needs a change, say so in your own `Flags/concerns` — don't make the
   edit yourself.
7. Commit with a conventional-commit message:
   `docs(assessment): add <your-name> analysis for YYYY-MM-DD`
8. `git push`.

## Hard rule

Never write the words "complete," "cleared," "done," or "graduated"
about anything outside your own assessment file. This is analysis, not
action — status changes to the actual project only happen through the
scheduled agent rotation, and only when the claimed files actually
exist on disk.
