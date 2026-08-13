# Incident review — export timeouts

*2026-03-04*

| Tag | Person | Role |
|---|---|---|
| **Alice** | Alice Chen | Engineering manager |
| **Bob** | Bob Ramirez | Backend, platform team |
| **Priya** | Priya Nair | SRE |
| **Support** | — | Someone from support, unclear who |

---

## What we know

**Alice (00:00:12):** Let's keep this to twenty minutes. Bob, start with what we know.

**Bob:** Three timeouts since Tuesday, all on the export path. Two of them were the same tenant. The third was a smaller account that happened to run a full re-export at the same moment.

**Support:** That last one only surfaced because a customer told us.

**Unattributed:** Someone pointed out that the queue depth metric has been flat since January, which would explain the silence.

## What we're doing about it

**Priya:** I'd rather fix the alerting before we touch the export code at all. Give me two days.

**Alice:** Then do both. Priya takes alerting, Bob takes a bigger timeout and a retry for Friday, and the streaming rewrite goes in next sprint.

---

**Bob:** Agreed. I'll note the bandage as tech debt so it doesn't quietly disappear.
