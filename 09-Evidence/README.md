# Evidence index

All images in this directory were supplied from the user's lab. They are evidence of the configuration and events visible at capture time; they are not claims of production deployment.

## Main Wazuh evidence

| File | What it demonstrates |
|---|---|
| `01-wazuh-dashboard.png` | Wazuh Overview: 2 active agents, 0 disconnected, alert severity summary |
| `02-active-agents.png` | `tushar-windows` and `tushar-Linux` active; agent IDs 001/002; agent version v4.14.9 |
| `03-windows-sysmon.png` | Windows Sysmon telemetry in Discover; 52 hits in the shown time range |
| `04-linux-sysmon.png` | Linux Sysmon for Linux telemetry in Discover; 145 hits in the shown one-second interval |
| `05-windows-security-events.png` | Windows Security event ID 4726 (user account deleted) for `student1` |
| `06-linux-ssh-events.png` | Linux SSH authentication failure for invalid user `fakeuser`; source shown as `192.168.234.133` |
| `07-soc-dashboard.png` | Custom dashboard: failed Windows logons, Windows account-change trend, Linux failed SSH activity |
| `08-file-integrity-monitoring.png` | FIM events for `C:\companydata\payroll.txt`: modified (rule 550) and deleted (rule 553) |
| `09-custom-windows-rule.png` | Custom Windows Guest-account rule code, rule ID 100200, event ID 4722, target `Guest` |
| `10-ssh-bruteforce-alert.png` | SSH brute-force correlation alert from the same source IP |
| `11-active-response.png` | Active Response log event: host blocked by `firewall-drop`, rule ID 651 |

## VMware configuration evidence

`VMware-Configuration/` contains 12 screenshots for the three virtual machines: Wazuh server, Ubuntu endpoint, and Windows endpoint. These document memory, processor, virtual disk, and network-adapter settings as shown in VMware. Use these screenshots as the source of truth for the exact values.

## Supplementary screenshots

` supplementary/ ` contains alternate views of the Guest-account rule/event, SSH rule configuration and Active Response event. They supplement the main screenshots; they are not separate attack scenarios.

## Privacy note

The screenshots expose private RFC1918 lab IP addresses and local hostnames. Review before publishing if you prefer not to disclose local lab details.
