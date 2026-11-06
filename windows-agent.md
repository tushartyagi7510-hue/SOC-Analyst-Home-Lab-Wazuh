# Windows Endpoint -- Wazuh Agent

## Endpoint identity

-   Agent name: `tushar-windows`
-   Agent ID: `001`
-   Operating system: Microsoft Windows 10 Pro `10.0.19045.3803`
-   Private IP: `192.168.234.133`
-   Wazuh agent version shown: `v4.14.9`

## Status verification

The Wazuh Endpoints page shows the Windows endpoint as **Active**.

## Sysmon telemetry verification

The supplied Discover screenshot shows Windows Sysmon telemetry with: -
Agent filter: `tushar-windows` - Channel:
`Microsoft-Windows-Sysmon/Operational` - Event ID: `10` - Event record
ID: `16014`

Event ID 10 is a Sysmon Process Access event. The screenshot is evidence
that Windows Sysmon events were ingested and searchable in Wazuh.

## Security event verification

A separate Discover screenshot shows Windows Security channel data with
Event ID `4726` and a message indicating a user account was deleted.
This is an observed Windows Security event in the lab. The Guest-account
enablement detection is documented separately under rule `100200`.

## Evidence

-   `../09-Evidence/02-active-agents.png`
-   `../09-Evidence/03-windows-sysmon.png`
-   `../09-Evidence/05-windows-security-events.png`
