# Lab 1 - Ubuntu Server Installation and SSH Confuguration

## Objective

Install Ubuntu Server and configure it for remote administartion

## Tasks

- [x] Install Ubuntu Server 26.04 LTS
- [x] Update and upgrade the OS
- [x] Enable SSH
- [x] Reserve IP address for server
- [x] Verify SSH connectivity from Powershell

## Issue Encountered

### Server did not receive an IPv4 address

**Symptoms**
- `ip addr` displayed:
    - `lo`
    - `enp3s0` with only IPv6 addresses
- `ip -4 -br addr` displayed:
    - `lo`
    - No `enp3s0`
  
**Cause**
- The Netplan configuration did not include `dhcp4: true` for the `enp3s0` interface.

**Resolution**
- Edited the Nerplan YAML file
  - Added: `dhcp4: true`
- Applied the configuration with: ```sudo netplan apply```
- Verified the server received an IPv4 address then reserved the IP.

## Lessons Learned

- The `lo` interface is the loopback interface and is always present.
- `enp3s0` is the physical Ethernet interface.
- Netplan controls network configuration on Ubuntu Server
- DHCP must be enabled for an interface to automatically obtain an IPv4 address.
