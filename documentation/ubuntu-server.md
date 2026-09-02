# Ubuntu Server

## Overview

Ubuntu Server is used as the server-side system in the CyberLab environment. It provides a Linux-based system for networking, system administration, SSH, web service and security monitoring exercises.

## Virtual Machine

| Component | Configuration |
|---|---|
| Operating System | Ubuntu Server |
| Hypervisor | Oracle VirtualBox |
| Network | Private laboratory network |
| Role | Lab server and Wazuh monitoring system |

## Services Used

- OpenSSH for controlled authentication tests
- Apache2 for HTTP and access-log monitoring
- UFW for basic firewall management
- Wazuh Manager for centralized security monitoring
- Wazuh Agent for endpoint event collection

## Usage in the Lab

Ubuntu Server is used both as a monitored server and as the central Wazuh Manager system in the documented internship environment. SSH authentication events and Apache2 web-server logs are generated and reviewed through Wazuh.

## Security Note

Environment-specific IP addresses, credentials, certificates and other sensitive configuration values are intentionally omitted from this public repository.
