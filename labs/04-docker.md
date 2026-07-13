# Lab 4 - Docker

## Objective

Install and configure Docker on my server to learn what docker is, how it works, and improve on my Linux foundation.

## Tasks

- [x] Remove any included Docker packages
- [x] Install Docker
  - [x] Verfy my server can securely communicate with Docker
  - [x] Add GPG Key
  - [x] Verify key was added
  - [x] Add repository to APT
  - [x] Update the package list
  - [x] Install Docker
- [x] Verify the installation
- [x] Pull the first Docker image
- [] Understand Docker Architecture
- [] Run the first container
- [] Manage the container
- [] Inspect images and containers
  
## Commands Used

```bash
for pkg in docker.io docker-doc docker-compose docker-compose-v2 podman-docker;
> do sudo apt remove -y $pkg
> done
sudo apt install -y ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
ls -l /etc/apt/keyrings/
sudo chmod a+r /etc/apt/keyrings/docker.asc
sudo tee /etc/apt/sources.list.d/docker.sources <<EOF
Types: deb
URIs: https://download.docker.com/linux/ubuntu
Suites: $(. /etc/os-release && echo "${UBUNTU_CODENAME:-$VERSION_CODENAME}")
Components: stable
Architectures: $(dpkg --print-architecture)
Signed-By: /etc/apt/keyrings/docker.asc
EOF
sudo apt install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
sudo systemctl status docker
sudo docker run hello-world
```

## Issues Encountered

## Lessons Learned
