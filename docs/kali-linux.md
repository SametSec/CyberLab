# Kali Linux

## Overview

Kali Linux is used as the security testing machine in the CyberLab environment.

It is used for network analysis, security testing, vulnerability assessment and penetration testing experiments against authorized lab systems.

## Installation

Kali Linux 2026.1 was installed as a virtual machine using Oracle VirtualBox.

## Virtual Machine

| Component | Configuration |
|---|---|
| Operating System | Kali Linux 2026.1 |
| Hypervisor | Oracle VirtualBox |
| Primary Interface | eth0 |
| Lab Interface | eth1 |
| Lab IP Address | 192.168.50.10/24 |
| Role | Security Testing Machine |

## Network Configuration

Kali Linux uses two network interfaces.

- `eth0` → Internet connectivity
- `eth1` → CyberLab Internal Network

The `eth1` interface is configured with a static IP address:

```text
192.168.50.10/24
