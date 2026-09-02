# Network Configuration

## Overview

CyberLab uses a private VirtualBox laboratory network so that the systems used for cybersecurity exercises can communicate in a controlled environment.

The network design keeps laboratory traffic separate from production systems and is intended only for authorized testing and learning.

## Laboratory Topology

```text
                     Private Laboratory Network
                               |
              +----------------+----------------+
              |                                 |
         Kali Linux                        Ubuntu Server
      Security Testing                    Server / Wazuh
              |                                 |
              +---------------+-----------------+
                              |
                           Windows
                         Wazuh Agent
```

## Network Configuration Principles

- Virtual machines are connected through the laboratory network required by the exercise.
- IP addresses are checked before connectivity and monitoring tests.
- Environment-specific addresses and interface names are not published here.
- Network configuration is adjusted according to the test scenario and the virtualization environment.

## Wazuh Communication

The monitored systems communicate with the Wazuh Manager so that endpoint events can be collected and analyzed centrally. The Wazuh Dashboard is then used to review agent status, alerts and related event data.

## Security Note

Real IP addresses, credentials, certificates and other sensitive configuration values are intentionally omitted from this public repository.
