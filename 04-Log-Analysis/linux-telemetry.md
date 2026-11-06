# Linux Authentication and Sysmon Telemetry Analysis

## Endpoint

-   Agent: `tushar-Linux`
-   Agent ID: `002`
-   OS: Ubuntu 24.04.4 LTS
-   IP: `192.168.234.132`

## SSH authentication failures

The supplied Discover evidence shows multiple SSH-related events for
`tushar-Linux`, including: - `sshd: authentication failed` -
`PAM: User login failed` - `sshd: connection reset` -
`Multiple SSH login failures observed from the same source IP`

An expanded event identifies username `fakeuser` and source address
`192.168.234.133`.

## Linux Sysmon

The archive Discover evidence shows `predecoder.program_name: sysmon`,
provider `Linux-Sysmon`, and Event ID `1`.

## Analyst interpretation

Repeated failed SSH logins may be consistent with password guessing, but
can also result from a controlled test, mistyped credentials, or
automated activity. The event source, target account, source IP, timing,
and surrounding events should be checked before concluding malicious
intent.

## Evidence

-   `../09-Evidence/04-linux-sysmon.png`
-   `../09-Evidence/06-linux-ssh-events.png`
