# Windows Security Telemetry Analysis

## Endpoint

-   Agent: `tushar-windows`
-   Agent ID: `001`
-   OS: Windows 10 Pro `10.0.19045.3803`
-   IP: `192.168.234.133`

## Observed events

### Sysmon Process Access

The Sysmon Discover screenshot shows: - Channel:
`Microsoft-Windows-Sysmon/Operational` - Event ID: `10` - Event record
ID: `16014`

### Windows Security account event

The Windows security Discover screenshot shows: - Channel: `Security` -
Event ID: `4726` - Target user field: `student1` - Message text begins:
`A user account was deleted`

### Guest account enabled detection

A separate event search for `guest` shows the custom rule description:

`Tushar Tyagi Windows Guest account was enabled.`

The matching custom rule ID is `100200`. The rule configuration matches
Event ID `4722` and target username `Guest`. See
`../06-FIM-and-Custom-Rules/custom-windows-detection.md`.

## Analyst workflow

1.  Filter Discover by `agent.name: tushar-windows`.
2.  Select a time range covering the test.
3.  Inspect the event channel and Event ID.
4.  Expand the event to review account, host, timestamp, and message
    fields.
5.  Correlate the event with the custom rule alert where relevant.

## Evidence

-   `../09-Evidence/03-windows-sysmon.png`
-   `../09-Evidence/05-windows-security-events.png`
-   `../09-Evidence/09-custom-windows-rule.png`
