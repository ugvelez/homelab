# Lab 1 - Ubuntu Server Installation and SSH Configuration

## Date

July 9,2026

## Objective

Install Ubuntu Server and configure it for remote administartion

## Tasks

- [x] Install Ubuntu Server 26.04 LTS
- [x] Update and upgrade the OS
- [x] Enable SSH
- [x] Reserve IP address for server
- [x] Verify SSH connectivity from Powershell

## Issues Encountered

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

# *Configuration of SSH Amendment*

## Date Added

July 21, 2026

## Objective

Allow the server to connect via an outside of network

## Issue Encountered

### Symptom

Unable to SSH into server from an external network. Given the message:
`Connection timed out.`

## Amendment explanation

The server was initially configured to allow for SSH administration via local network. Unbeknownst to me external access was needed to be configured to allow SSH administration from an  external network.

## Changes deployed

Added a port forwarding assignment:
    `Port Assignment: SSH`
    `External Port: 22`
    `Internal Port: 22`
    `Protocol: TCP
    `
## Lessons Learned

- Initially, I attempted to establish an SSH connection using a private IP address, not realizing that private IP addresses are only accessible within the local network and cannot be         reached from external networks. I learned that external SSH access requires the use of a public IP address.
- Port forwarding enables external SSH access by directing incoming connections from a public IP address to the appropriate internal device on the network.
