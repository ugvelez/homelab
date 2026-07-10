# Lab 2 - User Management

## Objective

Learn how Linux manages user accounts and permissions.

## Tasks

- [x] Create/Add a new user
- [x] Verify the user exists
- [x] Create/add group
- [x] Modify user group and permissions
- [x] Create a directory for the group
- [x] Change directory ownership and permissions to group

## Commands Used

```bash
sudo adduser lab02
ls /home
cat /etc/passwd
grep lab02 /etc/passwd
sudo usermod -aG sudo lab02
groups lab02
sudo groupadd labusers
sudo usermod -aG labusers lab02
sudo mkdir /shared
sudo chown :labusers /shared
sudo chmod ug+rwx /shared
sudo chmod o-rx /shared
ls -ld /shared
```

## Lessons Learned

- Each user has:
  - Username
  - Password
  - Home Directory
  - Groups
  - Permissions
- The principle of least privileges improves security

## Issues Encounted

None
