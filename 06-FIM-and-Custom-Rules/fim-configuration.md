# File Integrity Monitoring (FIM)

## Monitored endpoint and path

-   Endpoint: `tushar-windows`
-   Agent ID: `001`
-   Monitored file shown: `C:\companydata\payroll.txt`

## Observed FIM events

The supplied Wazuh File Integrity Monitoring Events screenshot shows two
events for `C:\companydata\payroll.txt`:

  Rule ID   Description                  Event
  --------- ---------------------------- ------------
  `550`     Integrity checksum changed   `modified`
  `553`     File deleted                 `deleted`

## What this demonstrates

The screenshot demonstrates that Wazuh FIM detected a modification and a
deletion for the monitored file path.

## Analyst considerations

FIM alerts identify changes to monitored files. The analyst should
determine whether the change was expected, authorized, and associated
with a legitimate user or process. A file modification alone does not
prove compromise.

## Configuration limitation

The supplied screenshot verifies the monitored path and resulting
events, but it does not show the full FIM configuration block from the
Windows agent's configuration file. The repository therefore documents
the observed behavior rather than inventing the complete XML
configuration.

## Evidence

-   `../09-Evidence/08-file-integrity-monitoring.png`
