# CLI Assessment Protocol

Read this file in full before doing anything. This governs the daily
local architecture/repo-health assessment run by Mistral CLI, Gemini
CLI, and Grok CLI — independent of the scheduled GitHub-agent rotation
in `comms/schedule.md`. You are doing analysis, not making changes.

## Every day, in this order

1. `git checkout main && git pull` — start from current `main`, not a
   leftover local branch from a prior day.
2. Check whether today's shared assessment branch already exists:
   `git fetch origin assessment/YYYY-MM-DD` (today's date). Two cases:
   - **It doesn't exist yet (you're first today):** create it —
     `git checkout -b assessment/YYYY-MM-DD`.
   - **It already exists (another CLI ran today before you):**
     check it out and pull it — `git checkout assessment/YYYY-MM-DD`
     then `git pull origin assessment/YYYY-MM-DD`. Do NOT create a
     second branch. All three CLIs share one branch per day.
3. Read: the current file tree, the latest file in `comms/handoffs/`,
   `docs/GRADUATION.md`, and `docs/DECISIONS.md`. This is your context —
   don't answer from assumption or memory of a prior day.
4. Answer the assessment question given to you inline today (it changes
   daily — this file only governs mechanics, not the question itself).
5. Open `docs/assessments/YYYY-MM-DD.md` (today's date). If it doesn't
   exist, create it using the template structure below. **Read the
   current contents first if it already exists** — another CLI may
   have already written its section today. Add your own section; never
   overwrite or edit another model's section.
6. Your section header is your own name: `### Mistral CLI`,
   `### Gemini CLI`, or `### Grok CLI`. Under it, use exactly these
   sub-headers: `Key findings`, `Recommended changes`, `Flags/concerns`.
7. **Write only to `docs/assessments/YYYY-MM-DD.md`.** Do not touch
   `AGENT_PROMPT.md`, anything in `comms/`, anything in `agents/`, or
   `docs/DECISIONS.md`/`docs/GRADUATION.md`. If you think one of those
   needs a change, say so in your own `Flags/concerns` — don't make the
   edit yourself.
8. Commit with a conventional-commit message:
   `docs(assessment): add <your-name> analysis for YYYY-MM-DD`
9. Push the branch — `git push origin assessment/YYYY-MM-DD` (never
   `main`, it's protected). Then:
   - **If you created this branch today (you were first):** open a
     pull request — `gh pr create --title "docs(assessment): daily
     assessment for YYYY-MM-DD" --body "Shared branch for today's
     three-CLI assessment."`
   - **If the branch already existed:** do NOT open a new PR — your
     push automatically updates the existing one. Just confirm with
     `gh pr list` that a PR for this branch is already open.

Angel reviews and merges the PR once all CLIs that ran today have
added their sections — the same review flow as any other PR in this
repo. The CLI never merges its own PR.

## Hard rule

Never write the words "complete," "cleared," "done," or "graduated"
about anything outside your own assessment file. This is analysis, not
action — status changes to the actual project only happen through the
scheduled agent rotation, and only when the claimed files actually
exist on disk.
