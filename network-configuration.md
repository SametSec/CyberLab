# Network Configuration

## Overview

CyberLab uses an isolated VirtualBox Internal Network to allow communication between the Kali Linux security testing machine and the Ubuntu Server.

The laboratory network is separated from the host network and is used only for authorized security experiments.

## Network Configuration

| Machine | Operating System | IP Address | Interface |
|---|---|---|---|
| Kali | Kali Linux | 192.168.50.10/24 | eth1 |
| Ubuntu | Ubuntu Server | 192.168.50.20/24 | enp0s8 |

### Network

```text
Network: 192.168.50.0/24

Kali Linux
192.168.50.10
     │
     │
     │  VirtualBox Internal Network
     │
     │
Ubuntu Server
192.168.50.20
