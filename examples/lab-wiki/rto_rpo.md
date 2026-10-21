# RTO and RPO for lab-wiki

Example Labs filled this sheet for lab-wiki on 2026-10-21. The numbers are their choices for that notes site. They are not a vendor SLA and they are not taken from a standard.

## Choices

- Service: lab-wiki, the internal Markdown notes on wiki.example.com.
- Work a reader loses if the previous copy is restored: notes written after the last successful copy.
- How often a successful copy currently finishes: every 15 minutes, into bucket lab-offsite.
- How long the team will accept the service staying unreadable: 4 hours after the incident lead declares the recovery.
- How long a gap the team will accept: 15 minutes, matching the copy interval they chose.

RTO: 4h
RPO: 15m

A failed copy does not move the recovery point. During the 2026-10-20 drill the point they used was the successful copy at 2026-10-20 09:00 UTC. The drill record says Dana Example could read the tree the same afternoon. It does not include a stopwatch time.

The plan file repeats these two lines. The template tokens are already replaced on this sheet. Check upstream docs before treating a scheduler setting as proof that every copy succeeded.
