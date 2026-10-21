# RTO and RPO worksheet

Use this sheet before you edit the plan. The two lines the checker reads are unindented `RTO:` and `RPO:` lines in the plan, each a number plus `m`, `h`, or `d`.

## How this pack uses the words

RTO is the duration the team will accept between the declared recovery and a readable service. RPO is the duration of recent work the team will accept losing. Both are choices for one service. They are not a vendor SLA. This sheet does not quote a figure from a standard.

## What to write

- Service: {{SERVICE_NAME}}
- Work a reader loses if you restore the previous copy: {{LOST_WORK}}
- How often a successful copy currently finishes: {{BACKUP_INTERVAL}}
- How long the team will accept the service staying unreadable: {{RTO}}
- How long a gap the team will accept between the failure and the last good copy: {{RPO}}

RTO: {{RTO}}
RPO: {{RPO}}

If a copy fails, the recovery point stays at the previous success. Write that time in the plan's exercise section when you drill. Do not type a stopwatch result you did not measure.

## A finished sheet

The filled example for Example Labs is `examples/lab-wiki/rto_rpo.md`. That lab chose a 15-minute copy interval and set the RPO line to match it. The RTO line is the unreadability they accepted for lab-wiki. Those two numbers are theirs. Copy the shape, not the claim that the same numbers fit another service.

Check upstream docs for the backup tool's scheduling flags before you treat a configured interval as the interval that actually succeeds.
