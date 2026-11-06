# Ubuntu Endpoint -- Wazuh Agent

## Endpoint identity

-   Agent name: `tushar-Linux`
-   Agent ID: `002`
-   Operating system: Ubuntu 24.04.4 LTS
-   Kernel shown at login: `6.8.0-147-generic`
-   Private IP: `192.168.234.132`
-   Wazuh agent version shown: `v4.14.9`

## Status verification

The Wazuh Endpoints page shows the Ubuntu endpoint as **Active**.

## Linux authentication telemetry

The Discover screenshot shows SSH authentication failures for agent
`tushar-Linux`. One expanded event includes: - Decoder: `sshd` -
Username: `fakeuser` - Full log: failed password for invalid user
`fakeuser` - Source IP shown in the event: `192.168.234.133`

## Sysmon for Linux telemetry

The `wazuh-archives*` screenshot shows: - Agent: `tushar-Linux` -
`predecoder.program_name`: `sysmon` - Provider: `Linux-Sysmon` - Event
ID: `1` - Event payload with process/event metadata

This confirms that Linux Sysmon events were present in the archive data
view.

## Evidence

-   `../09-Evidence/02-active-agents.png`
-   `../09-Evidence/04-linux-sysmon.png`
-   `../09-Evidence/06-linux-ssh-events.png`
