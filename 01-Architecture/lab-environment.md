# Lab Environment

## Virtual machines

This lab uses three VMware virtual machines.

| Role | Operating system / hostname | Wazuh identity | IP shown in dashboard |
|---|---|---|---|
| SIEM server | Ubuntu Server 24.04.5 LTS (`wazuh`) | Manager / Indexer / Dashboard | `192.168.234.130` |
| Windows endpoint | Windows 10 Pro, build `10.0.19045.3803` | `tushar-windows`, agent `001` | `192.168.234.133` |
| Linux endpoint | Ubuntu 24.04.4 LTS | `tushar-Linux`, agent `002` | `192.168.234.132` |

The Agents view shows both endpoint agents as **Active** and displays agent version `v4.14.9`. This is the version visible for the agents in the screenshot; it should not be interpreted as independently verified versions for every server component.

## VMware evidence

The `../09-Evidence/VMware-Configuration/` folder contains 12 screenshots covering memory, processor, virtual disk, and network-adapter settings for all three VMs. Consult those images for exact resource allocations and network configuration.

## Network and scope

The screenshots show private lab addresses in the `192.168.234.0/24` range. The lab is intended for isolated educational testing. No public target or production environment is part of the documented exercise.

## Evidence limitations

The screenshots establish the values visible at capture time. They do not prove that the VMs always ran simultaneously, nor do they provide a complete export of all VMware settings or Wazuh configuration files.
