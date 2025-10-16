# Simple Ubuntu 22.04 base with common pentest/dev tools
FROM ubuntu:22.04

ENV DEBIAN_FRONTEND=noninteractive
RUN apt-get update && apt-get upgrade -y \
  && apt-get install -y --no-install-recommends \
     sudo curl wget ca-certificates gnupg lsb-release apt-transport-https \
     build-essential git vim net-tools iproute2 openssh-client \
     nmap sqlmap john hydra python3 python3-pip unzip zip netcat \
  && apt-get clean && rm -rf /var/lib/apt/lists/*

# Optional: add a non-root user (codespaces uses 'vscode' user)
RUN useradd -m -s /bin/bash vscode && echo 'vscode ALL=(ALL) NOPASSWD:ALL' >> /etc/sudoers

USER vscode
WORKDIR /home/vscode
ENV PATH="/home/vscode/.local/bin:${PATH}"
