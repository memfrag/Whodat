# Incident review — export timeouts

*2026-03-04*

**Attendees:** Alice Chen, Bob Ramirez, Priya Nair

---

**Alice Chen (00:00:12):** Let's keep this to twenty minutes. Bob, start with what we know.

**Bob Ramirez:** Three timeouts since Tuesday, all on the export path. Two of them were the same tenant. The third was a smaller account that happened to run a full re-export at the same moment.

**Priya Nair:** That last one only surfaced because a customer told us. I'd rather fix the alerting before we touch the export code at all.

**Unattributed:** Someone pointed out that the queue depth metric has been flat since January, which would explain the silence.

**Alice Chen:** Then do both. Priya takes alerting, Bob takes a bigger timeout and a retry for Friday, and the streaming rewrite goes in next sprint.
