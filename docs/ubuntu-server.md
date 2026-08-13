# Ubuntu Server

## Overview

Ubuntu Server is used as the server-side system in the CyberLab environment.

It provides a Linux-based target system for networking, system administration, SSH, logging and security monitoring experiments.

## Installation

Ubuntu Server 26.04 LTS was installed as a virtual machine using Oracle VirtualBox.

### Virtual Machine

| Component | Configuration |
|---|---|
| Operating System | Ubuntu Server 26.04 LTS |
| Hypervisor | Oracle VirtualBox |
| Network Interface | enp0s8 |
| IP Address | 192.168.50.20/24 |
| Role | Lab Server |

## Network Configuration

The server is connected to the CyberLab Internal Network.

```text
Ubuntu Server
     │
     │ enp0s8
     │
192.168.50.20/24
     │
     │
CyberLab Internal Network
192.168.50.0/24
