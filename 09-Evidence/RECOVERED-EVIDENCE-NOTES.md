# Recovered Evidence Notes

This package restores the Wazuh evidence images from the earlier November 5 portfolio package and adds the 12 VMware hardware/network screenshots supplied on November 6.

The recovered Wazuh evidence includes dashboard, active agents, Windows/Linux Sysmon, Windows security events, Linux SSH events, SOC dashboard, FIM, custom Windows rule, SSH brute-force alert and Active Response screenshots.

`06-FIM-and-Custom-Rules/local_rules.xml` is a transcription from the earlier supplied rules screenshot, not a direct file export from the live Manager. Compare it with `/var/ossec/etc/rules/local_rules.xml` on your VM before using it. Do not overwrite your working configuration with this recovered copy without checking it first.
