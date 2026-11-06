# Wazuh Archive Collection

## Purpose

Archive collection was part of the lab build so the analyst could review
a broader set of collected events in addition to rule-generated alerts.

## Configuration notes

The tutorial workflow used the Wazuh manager configuration file:

``` text
/var/ossec/etc/ossec.conf
```

The archive-related global options discussed in the lab are:

``` xml
<global>
  <logall>yes</logall>
  <logall_json>yes</logall_json>
</global>
```

This is an illustrative configuration fragment, not a complete
`ossec.conf`. The screenshots supplied show events being searched in the
`wazuh-archives*` data view, including Linux Sysmon events. The
screenshots do not show the full server configuration or the Filebeat
archive-ingestion settings, so those exact settings are not reproduced
here.

## Evidence of archive ingestion

The Linux Sysmon screenshot uses the `wazuh-archives*` data view and
shows `predecoder.program_name: sysmon`, agent `tushar-Linux`, and a
Linux-Sysmon event payload with Event ID `1`.

See `04-linux-sysmon.png`.

## Operational consideration

Archive collection increases the volume of stored data. In production,
storage capacity, retention, access control, and data minimization must
be considered.
