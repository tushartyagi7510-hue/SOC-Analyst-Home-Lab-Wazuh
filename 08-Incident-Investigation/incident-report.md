# Incident Investigation Report -- Wazuh SOC Lab

## 1. Case information

  -----------------------------------------------------------------------
  Field                               Value
  ----------------------------------- -----------------------------------
  Case ID                             LAB-WAZUH-SSH-001

  Analyst                             Tushar Tyagi

  Environment                         Isolated three-VM Wazuh lab

  Status                              Lab exercise documented

  Nature                              Controlled SSH
                                      authentication-failure detection
                                      and response test
  -----------------------------------------------------------------------

## 2. Executive summary

Repeated SSH authentication failures were generated against the Ubuntu
endpoint in the Wazuh lab. The endpoint was identified as `tushar-Linux`
(`192.168.234.132`). The Discover evidence includes failed SSH
authentication messages for the invalid username `fakeuser`, with source
IP `192.168.234.133`.

A custom Wazuh rule, ID `100101`, was configured with a frequency of
three matching events within 120 seconds and a same-source-IP condition.
The dashboard shows the custom description
`Multiple SSH login failures observed from the same source IP`. A
subsequent Active Response log event records
`Host Blocked by firewall-drop Active Response` under rule `651`.

This report documents a controlled educational lab exercise. It does not
describe a confirmed real-world attack or production compromise.

## 3. Scope and environment

  -----------------------------------------------------------------------
  System                              Identity
  ----------------------------------- -----------------------------------
  Wazuh server                        Ubuntu Server 24.04.5 LTS, `wazuh`,
                                      `192.168.234.130`

  Linux target                        Ubuntu 24.04.4 LTS, `tushar-Linux`,
                                      `192.168.234.132`

  Windows test endpoint/source        Windows 10 Pro, `tushar-windows`,
                                      `192.168.234.133`
  -----------------------------------------------------------------------

Only the listed virtual lab systems are in scope.

## 4. Detection details

  Field                         Value
  ----------------------------- ----------------------------------------------------------
  Use case                      Repeated SSH authentication failures from same source IP
  Custom rule ID                `100101`
  Rule level                    `10`
  Frequency                     `3`
  Timeframe                     `120` seconds
  Correlation                   Same source IP
  Matched rule                  `5760`
  MITRE ATT&CK                  `T1110` -- Brute Force
  Source IP observed in event   `192.168.234.133`
  Target agent                  `tushar-Linux`
  Username observed             `fakeuser`

## 5. Evidence reviewed

1.  Linux SSH event records with `sshd` authentication failures.
2.  Expanded event showing invalid username `fakeuser` and source IP
    `192.168.234.133`.
3.  Custom rule configuration showing ID `100101`, frequency `3`,
    timeframe `120`, and same-source-IP correlation.
4.  Discover event showing the custom repeated-SSH-failure description.
5.  Active Response log event showing
    `Host Blocked by firewall-drop Active Response`.

## 6. Findings

### Confirmed observations

-   SSH authentication failures were recorded for the Ubuntu endpoint.
-   The visible event includes invalid username `fakeuser`.
-   The visible source IP is `192.168.234.133`.
-   The custom rule configuration uses three matching events within 120
    seconds from the same source IP.
-   The custom rule alert description appeared in Wazuh Discover.
-   Wazuh logged a `firewall-drop` Active Response event.

### Interpretation

The event pattern is consistent with repeated failed SSH authentication
attempts. In this lab, the activity was generated for detection testing.
The evidence supports successful alert generation and an Active Response
log entry.

### What the evidence does not establish

-   It does not establish a real external attacker.
-   It does not prove successful unauthorized SSH access.
-   It does not show the complete firewall state or a separate
    connectivity-restoration test.
-   It does not establish that the same events form part of one
    real-world incident.

## 7. Response

The Wazuh Discover evidence shows an Active Response log event at
`/var/ossec/logs/active-responses.log` with rule ID `651` and
description `Host Blocked by firewall-drop Active Response`.

The screenshot supports that the response was logged. A separate
firewall-rule inspection or post-test connectivity check is not included
in the supplied evidence.

## 8. Recommendations

-   Correlate failed logins with any subsequent successful
    authentication.
-   Review source IP, target account, timestamps, and surrounding
    endpoint activity.
-   Tune the detection rule to reduce false positives.
-   Maintain a tested rollback path for automated firewall actions.
-   Keep the test environment isolated and retain only the logs needed
    for the exercise.

## 9. Conclusion

The Wazuh lab successfully displayed repeated SSH authentication
failures, generated the custom same-source-IP detection alert, and
recorded a `firewall-drop` Active Response event. The exercise
demonstrates a basic detection-and-response workflow using Wazuh. The
findings are limited to the evidence captured in this educational lab.

## 10. Lab disclaimer

This report describes controlled activity in an educational virtual
environment. It is not a report of a confirmed real-world security
incident.
