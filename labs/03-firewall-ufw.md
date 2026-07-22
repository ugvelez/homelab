# Lab 3 - Firewall (UFW)

## Date

July 10, 2026

## Objective

Learn how to secure Ubuntu Server by enabling the firewall (UFW) via SSH

## Tasks

- [x] Verify current status of UFW
- [x] Add a new rule to UFW to allow OpenSSH
- [x] Verify that rule was added
- [x] Enable UFW
- [x] Verify that UFW is active

## Commands Used

```bash
sudo ufw status
sudo ufw allow OpenSSH
sudo ufw app list
sudo ufw enable
sudo ufw status verbose
```

## Issues Encountered

None

## Lessons Learned

- Allowing SSH connections before enabling UFW as it could interrupt my SSH connection.
- A firewall prevents network traffic; it does not stop services from running.
