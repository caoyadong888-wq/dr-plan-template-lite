# Disaster recovery plan

Replace each `{{TOKEN}}` before this plan is called finished. Mailboxes in a file this pack's checker accepts stay on `example.com`. A sample incident-lead mailbox is `incident-lead@example.com`. This outline belongs to this pack. It is not a clause list from a standard. Map it to the framework you follow after you read that text.

## Service

- Name: {{SERVICE_NAME}}
- What a healthy reader can do: {{SERVICE_SUMMARY}}
- Hostname: {{HOSTNAME}}
- Current address: {{HOST_ADDRESS}}

Name the team that owns the service in a sentence under these lines. Write the address as the one operators type, and keep a documentation address in any copy of this file that you share.

## Targets

The durations below are chosen by the team for this service. They are not a vendor SLA and they are not copied from a standard.

RTO: {{RTO}}
RPO: {{RPO}}

RTO is how long the service may stay unreadable after the incident lead declares the recovery. RPO is how much recent work the team accepts losing. When the plan is finished, replace the tokens with a number and a unit `m`, `h`, or `d`, in the shape `4h` or `15m`.

## Dependencies

- Replacement address: {{REPLACEMENT_ADDRESS}}
- Bucket: {{BUCKET_NAME}}
- Object-store host: {{ENDPOINT_HOST}}
- Name-resolution host: {{DNS_HOST}}

Say which copy a restore will read. Do not invent a vendor API field. Check upstream docs for the server you run, including the URL scheme, the port, and whether the server expects path-style requests.

## Roles

- Incident lead: {{INCIDENT_LEAD_EMAIL}}
- Backup operator: {{BACKUP_OPERATOR_EMAIL}}
- Communications: {{COMMS_EMAIL}}
- Service owner: {{SERVICE_OWNER_EMAIL}}

One sentence on what each role decides. The checker shipped here rejects any mailbox outside `example.com`.

## Backup

Write where the copy lands, how often the team runs it, and what they keep when a copy fails. State whether a failed copy moves the recovery point. The token for the copy interval is {{BACKUP_INTERVAL}}.

## Restore order

Write the order the team will follow. Include these moments: edits stop, a copy is selected, the first pass is a dry-run, the owner compares the result, then the name readers use is pointed at the replacement. The replacement path token is {{RESTORE_PATH}}.

## Communication

- Status mailbox: {{STATUS_EMAIL}}
- Update interval the team chose: {{UPDATE_INTERVAL}}

Say who sends the first note and what that note must name. Do not add a telephone number to this pack's files.

## Exercise

- Date: {{EXERCISE_DATE}}
- Copy that was restored: {{EXERCISE_COPY}}
- What the owner read: {{EXERCISE_CHECK}}

Record whether the team's own RTO and RPO still stand after the exercise. Leave a stopwatch number out unless the team actually measured one.

## Revision

- Date: {{REVISION_DATE}}
- Author: {{REVISION_EMAIL}}
- Note: {{REVISION_NOTE}}

Keep one line for each published revision of this plan.
