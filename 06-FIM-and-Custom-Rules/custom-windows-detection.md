# Custom Windows Detection -- Guest Account Enabled

## Detection objective

Generate a custom Wazuh alert when the Windows Guest account is enabled.

## Rule details

-   Custom rule ID: `100200`
-   Rule level: `12`
-   Parent rule ID: `60103`
-   Windows Security Event ID: `4722`
-   Matched target username: `Guest`
-   Rule description: `Tushar Tyagi Windows Guest account was enabled.`
-   MITRE ATT&CK technique ID shown: `T1078`
-   Groups:
    `windows, windows_account_management, account_enabled, guest_account`

## Rule XML visible in the supplied screenshot

``` xml
<group name="windows, windows_security, account_changed, adduser">
  <rule id="100200" level="12">
    <if_sid>60103</if_sid>
    <field name="win.system.eventID">^4722$</field>
    <field name="win.eventdata.targetUserName">^Guest$</field>
    <description>Tushar Tyagi Windows Guest account was enabled.</description>
    <mitre>
      <id>T1078</id>
    </mitre>
    <group>windows,windows_account_management,account_enabled,guest_account</group>
  </rule>
</group>
```

This is transcribed from the visible screenshot. Confirm the exact XML
in your live `local_rules.xml` before treating this transcription as a
byte-for-byte copy.

## Validation evidence

The Discover screenshot filtered by `guest` shows: - Rule description:
`Tushar Tyagi Windows Guest account was enabled.` - Rule ID: `100200` -
Rule level: `12` - Event source location: `EventChannel`

## Analyst interpretation

The rule is intended to alert on a Windows Guest-account enablement
event. It does not detect every type of account change or all privilege
escalation activity.

## Evidence

-   `../09-Evidence/09-custom-windows-rule.png`
-   `../09-Evidence/09-custom-windows-rule-code.png`
