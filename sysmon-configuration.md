# Sysmon Telemetry -- Windows and Linux

## Windows Sysmon

The Wazuh Discover evidence shows events from the Windows channel:

``` text
Microsoft-Windows-Sysmon/Operational
```

Observed event details include: - Event ID: `10` - Event record ID:
`16014` - Agent: `tushar-windows`

Sysmon Event ID 10 represents Process Access telemetry. The screenshot
verifies that this event was indexed and searchable in Wazuh.

## Sysmon for Linux

The Wazuh archive evidence shows: - `predecoder.program_name`:
`sysmon` - Provider: `Linux-Sysmon` - Event ID: `1` - Agent:
`tushar-Linux`

The event payload is consistent with Linux Sysmon process-creation
telemetry.

## Why this matters

Sysmon enriches endpoint visibility with process and system activity. An
individual event is not proof of malicious behavior. Analysts should
correlate process details, user context, host identity, timestamps, and
related events.

## Evidence

-   `../09-Evidence/03-windows-sysmon.png`
-   `../09-Evidence/04-linux-sysmon.png`

The screenshots verify event ingestion. The complete Sysmon
configuration files and exact installation commands were not included in
the supplied evidence and are not invented here.
