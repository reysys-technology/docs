---
title: installation
---

# Installation

## Linux Package Managers

### APT (Debian/Ubuntu)

```shell
sudo apt update
sudo apt install ca-certificates curl -y
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://repo.reysys.com/apt/gpg.key -o /etc/apt/keyrings/reysys.asc
sudo chmod a+r /etc/apt/keyrings/reysys.asc

sudo tee /etc/apt/sources.list.d/reysys.sources <<EOF
Types: deb
URIs: https://repo.reysys.com/apt
Suites: /
Signed-By: /etc/apt/keyrings/reysys.asc
EOF

sudo apt update
sudo apt install -y rscli

# Specific version
sudo apt install -y rscli=1.0.2
```

### YUM (RHEL/Fedora/CentOS)

```shell
sudo tee /etc/yum.repos.d/reysys.repo <<EOF
[reysys]
name=reysys
baseurl=https://repo.reysys.com/yum/
enabled=1
gpgcheck=1
gpgkey=https://repo.reysys.com/yum/gpg.key
EOF

sudo dnf install -y rscli

# Specific version
sudo dnf install -y rscli-1.0.2-1
```

## Docker

### Docker Hub

```shell
docker run reysys/rscli:latest

# Specific version
docker run reysys/rscli:1
docker run reysys/rscli:1.0.2
```

### GitHub Container Registry

```shell
docker run ghcr.io/reysys-technology/rscli:latest

# Specific version
docker run ghcr.io/reysys-technology/rscli:1
docker run ghcr.io/reysys-technology/rscli:1.0.2
```

## Homebrew

```shell
brew tap reysys-technology/homebrew-tap
brew install rscli

# Specific version
brew install rscli@1
brew install rscli@1.0.2
```

## GitHub Releases

Download pre-built binaries from the [GitHub Releases](https://github.com/reysys-technology/rscli/releases) page.

```shell
# Example for Linux amd64
curl -LO https://github.com/reysys-technology/rscli/releases/latest/download/rscli_linux_amd64
chmod +x rscli_linux_amd64
sudo mv rscli_linux_amd64 /usr/bin/rscli

# Example for Linux amd64 specific version
curl -LO https://github.com/reysys-technology/rscli/releases/v1.0.2/download/rscli_linux_amd64
chmod +x rscli_linux_amd64
sudo mv rscli_linux_amd64 /usr/bin/rscli
```
