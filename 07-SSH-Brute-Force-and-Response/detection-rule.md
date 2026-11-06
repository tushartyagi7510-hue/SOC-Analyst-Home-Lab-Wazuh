# SSH Repeated Authentication-Failure Detection

## Detection objective

Detect repeated SSH login failures from the same source IP and generate
a custom Wazuh alert.

## Rule details visible in the rules screenshot

-   Rule ID: `100101`
-   Rule level: `10`
-   Frequency: `3`
-   Timeframe: `120` seconds
-   Parent/matched rule ID: `5760`
-   Source correlation: `<same_source_ip />`
-   Description:
    `Multiple SSH login failures observed from the same source IP`
-   MITRE ATT&CK technique: `T1110`
-   Groups: `authentication_failed, ssh_bruteforce, credential_access`

## Rule XML

``` xml
<group name="local,syslog,sshd,authentication_failed,">
  <rule id="100101" level="10" frequency="3" timeframe="120">
    <if_matched_sid>5760</if_matched_sid>
    <same_source_ip />
    <description>Multiple SSH login failures observed from the same source IP</description>
    <mitre>
      <id>T1110</id>
    </mitre>
    <group>authentication_failed,ssh_bruteforce,credential_access,</group>
  </rule>
</group>
```

## Observed test evidence

The Discover screenshots show repeated SSH failures for agent
`tushar-Linux`. An expanded event shows: - Username: `fakeuser` - Source
IP: `192.168.234.133` - Decoder: `sshd` - Full log indicating failed
password for an invalid user

The custom alert screenshot shows the description
`Multiple SSH login failures observed from the same source IP`.

## Test interpretation

The rule correlates three matching authentication-failure events within
120 seconds from the same source IP. This is a lab detection pattern and
should be tuned before any production use.

## Evidence

-   `../09-Evidence/06-linux-ssh-events.png`
-   `../09-Evidence/10-ssh-bruteforce-alert.png`
-   `../09-Evidence/10-ssh-rule-configuration.png`
