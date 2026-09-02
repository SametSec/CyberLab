# Kali Linux

## Overview

Kali Linux is used as the security testing and analysis system in the CyberLab environment.

It is used for authorized network analysis, security testing, vulnerability assessment and controlled lab exercises.

## Virtual Machine

| Component | Configuration |
|---|---|
| Operating System | Kali Linux |
| Hypervisor | Oracle VirtualBox |
| Network | Private laboratory network |
| Role | Security testing and analysis system |

## Usage in the Lab

Kali Linux is used to generate controlled test traffic and security events against authorized laboratory systems. In the Wazuh project, it also participates as a monitored endpoint through the Wazuh Agent.

Examples of lab activities include:

- Network and service checks
- Controlled SSH authentication tests
- HTTP requests to the laboratory Apache2 service
- Review of the resulting logs and alerts in Wazuh

## Security Note

Environment-specific IP addresses, credentials, certificates and other sensitive configuration values are intentionally omitted from this public repository.
