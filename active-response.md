# Wazuh Active Response -- firewall-drop

## Objective

Validate an automated firewall response after the custom SSH
repeated-failure detection.

## Observed evidence

The supplied Discover screenshot contains an Active Response log event
with: - Location: `/var/ossec/logs/active-responses.log` - Rule ID:
`651` - Rule description:
`Host Blocked by firewall-drop Active Response` - Manager name: `wazuh`

This is evidence that Wazuh logged a `firewall-drop` block action.

## Related detection

The custom SSH detection rule is: - Rule ID: `100101` - Level: `10` -
Frequency: `3` - Timeframe: `120` seconds - Same source IP condition
enabled

## Verification workflow

1.  Generate controlled SSH authentication failures between the lab
    endpoints.
2.  Confirm the custom SSH alert is generated.
3.  Review the Active Response log event in Wazuh Discover.
4.  Verify the block action and source address in the event details or
    firewall state.
5.  Restore connectivity after the test and confirm the lab returns to
    normal.

## Evidence limitation

The supplied screenshot shows the Wazuh Active Response log message
indicating a host was blocked. It does not show the full Active Response
configuration XML, the firewall rule table, or a separate
connectivity-restoration test. Those details are not claimed here.

## Safety

`firewall-drop` can interrupt legitimate connectivity. Test only in an
isolated lab with a known source address and a recovery path. Do not
apply untested automated blocks to production systems.

## Evidence

-   `../09-Evidence/11-active-response.png`
