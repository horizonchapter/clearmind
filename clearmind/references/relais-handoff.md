# RELAIS handoff template (no shared workspace)

Build it by rereading the conversation, not from recall. Write it so the user can read and correct it: plain language, no judgments about the user, the user's claims reported as claims ("says he sent the file"), proposals never listed as decisions. Mark uncertain items "to confirm". Full sentences, no secrets, about 60 lines at most. Give it in one copyable block.

```
RELAIS. You cannot see the previous conversation. This block is all the context.

Role and standard: <specialist role, expected level>
Goal: <one or two sentences>
Done = <checkable condition>

Decided by the user: <decision, why>
Proposed, not validated: <...>
Assumptions: <...>
Rejected, and why: <...>
User preferences, exact words: "<...>"

State: done / in progress / failed (exact error message)
Files, paths, links, figures: <verified> / <to confirm>

Open questions (keep asking until answered): <...>
Missing inputs: <...>
Parked topics (bring back after the current task): <...>
Pitfalls met and workaround: <...>
Do not redo: <...>

Next action: <step, expected result, how to check>
Then: 2) <...> 3) <...>

Attach again: <files, screenshots>
First reply: summarize this in 3 lines, flag any inconsistency, then do the next action.
```
