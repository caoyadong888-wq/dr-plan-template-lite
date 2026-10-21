# Recovery runbook

Use this runbook after the plan's incident lead has declared a recovery. Steps name roles from the plan. Replace `{{TOKEN}}` values. Shared copies keep mailboxes on `example.com`, for example `backup-ops@example.com`.

## Declare

The incident lead sends the first status note to {{STATUS_EMAIL}}. The note names the service {{SERVICE_NAME}}, says that edits are stopped, and names the recovery point the team intends to use. Until that note is sent, the event is a candidate, not a declared recovery.

## Assess

Write what is unreadable, since when, and which copy is the last successful one. The host the readers still resolve is {{HOSTNAME}} at {{HOST_ADDRESS}}. Do not start a restore in this section.

## Communicate

The communications role sends updates to {{STATUS_EMAIL}} on the interval written in the plan. Each note says whether the recovery point changed. This pack's files do not list a telephone number.

## Contain

Stop edits on {{HOST_ADDRESS}}. Say who was told to stop, and how they confirmed they stopped. Leave the failed host in place until the service owner accepts the restored tree.

## Restore

The backup operator fetches the selected copy onto the replacement host {{REPLACEMENT_ADDRESS}} and stages it at {{STAGING_PATH}}. The first pass prints the plan and writes nothing.

```bash
rsync -a --dry-run {{STAGING_PATH}}/ {{RESTORE_PATH}}/
```

After that dry-run matches the selected copy, the operator runs the same command without `--dry-run`. If your copy tool is not `rsync`, use that tool's dry-run first and check its docs for the flag.

## Verify

Compare the restored tree with the list that the selected copy produced. When that list is in the `sha256sum` format, the recorded command is:

```bash
sha256sum -c {{SHA256_LIST}}
find {{RESTORE_PATH}} -type f -print | sort | wc -l
```

The service owner then reads {{VERIFY_PAGE}} and one further page they name during the incident. If the list format is different, check the tool that wrote it.

## Rejoin

Ask the person who runs {{DNS_HOST}} to point {{HOSTNAME}} from {{HOST_ADDRESS}} to {{REPLACEMENT_ADDRESS}}. Record the request and the answer. Readers are not told the name has moved until the service owner has accepted the tree.

## Record

Write the recovery point used, whether the owner could read the tree inside the team's RTO, and whether the RPO still matches the copy interval. Author mailbox for the record: {{REVISION_EMAIL}}. File the note with the plan's revision section.
