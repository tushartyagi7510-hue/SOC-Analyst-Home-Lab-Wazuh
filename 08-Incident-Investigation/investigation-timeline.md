# Lab Investigation Timeline

## Case context

This is a reconstruction of the test evidence visible in the supplied
screenshots. The screenshots contain events from different dates and
time windows; they are not presented as one continuous incident
timeline.

## Observed event sequence -- SSH test

  -------------------------------------------------------------------------------------------------
  Evidence time           Endpoint                Observation
  (dashboard display)                             
  ----------------------- ----------------------- -------------------------------------------------
  Nov 4, 2026, around     `tushar-Linux`          SSH failure events for invalid user `fakeuser`
  23:06                                           

  Nov 5, 2026, around     `tushar-Linux`          Repeated SSH authentication failures and
  21:46                                           same-source-IP custom detection

  Nov 5, 2026, around     Wazuh manager           Active Response log:
  22:14                                           `Host Blocked by firewall-drop Active Response`
  -------------------------------------------------------------------------------------------------

The dashboard time zone and the host log time zone may differ. Preserve
the original event timestamp and timezone when performing a formal
investigation.

## Other observed activity

-   Windows Sysmon Process Access event ID `10`.
-   Linux Sysmon event ID `1`.
-   Windows Security event ID `4726` showing an account deletion
    message.
-   Guest-account enablement custom alert, rule `100200`.
-   FIM modification and deletion events for
    `C:\companydata\payroll.txt`, rules `550` and `553`.

## Investigation notes

The supplied screenshots establish that these events were ingested and
visible. They do not establish that all events occurred during one
incident or that a real attacker compromised the lab. Treat each
exercise as controlled lab activity unless additional evidence
demonstrates otherwise.
