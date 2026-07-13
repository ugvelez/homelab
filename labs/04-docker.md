# Lab 4 - Docker

## Objective

Install and configure Docker on my server to learn what docker is, how it works, and improve on my Linux foundation.

## Tasks

- [] Install Docker
  - [x] Verfy my server can securely communicate with Docker
  - [x] Add GPG Key
  - [x] Verify key was added
  - [] Add repository to APT
  - [] Update the package list
  - [] Install Docker
- [] Verify the installation
- [] Understand Docker Architecture
- [] Pull the first Docker image
- [] Run the first container
- [] Manage the container
- [] Inspect images and containers
  
## Commands Used

```bash
sudo apt install -y ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
ls -l /etc/apt/keyrings/
```

## Issues Encountered

## Lessons Learned
