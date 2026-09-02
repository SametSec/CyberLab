# CyberLab

> A practical, virtualized cybersecurity laboratory for learning network security, Linux administration, SIEM, security monitoring and incident response.

CyberLab is a personal lab environment built with Oracle VirtualBox. It brings together Linux systems, Windows endpoints and Wazuh to create a controlled environment for experimenting with security monitoring, log analysis and automated response.

The repository also contains the Wazuh project developed during my software internship, documented separately under [`Wazuh-Lab/`](Wazuh-Lab/).

## Project Goals

- Understand network and system security fundamentals
- Practice Linux and Windows administration in a controlled environment
- Learn centralized log collection and security monitoring with Wazuh
- Analyze SSH authentication and Apache2 web-server events
- Understand the basic SIEM workflow from event collection to alert analysis
- Experiment with Wazuh Active Response in an authorized lab
- Build clear technical documentation around practical cybersecurity work

## Technologies

| Area | Technologies |
|---|---|
| Virtualization | Oracle VirtualBox |
| Security Testing | Kali Linux |
| Server | Ubuntu Server |
| Endpoint Monitoring | Windows + Wazuh Agent |
| SIEM / Monitoring | Wazuh Manager, Wazuh Dashboard, Wazuh Agent |
| Authentication | OpenSSH |
| Web Server | Apache2 |
| Firewall | UFW |

## Architecture

```text
 Windows Endpoint ───────┐
                         │
 Kali Linux ─────────────┼──> Wazuh Agent ──> Wazuh Manager
                         │                         │
 Ubuntu Server ──────────┘                         ▼
                                           Wazuh Dashboard
                                                  │
                                   ┌──────────────┴──────────────┐
                                   │                             │
                              Event Analysis              Active Response
                                   │                             │
                              SSH / Apache2               firewall-drop
```

The public repository intentionally omits environment-specific IP addresses, credentials, certificates and other sensitive values.

## Repository Structure

```text
CyberLab/
├── README.md
├── SECURITY.md
├── .gitignore
│
├── Wazuh-Lab/
│   ├── README.md
│   ├── architecture.md
│   ├── methodology.md
│   ├── test-scenarios.md
│   ├── findings.md
│   ├── results.md
│   ├── roadmap.md
│   ├── active-response/
│   │   └── firewall-drop.md
│   └── configuration/
│       ├── manager.md
│       └── agent.md
│
└── documentation/
    ├── kali-linux.md
    ├── ubuntu-server.md
    ├── network-configuration.md
    └── siem.md
```

## Wazuh Internship Project

The main project in this repository is a Wazuh-based security monitoring lab developed during my software internship.

The project demonstrates the following workflow:

1. Wazuh Agents are installed on monitored systems.
2. Security and system events are collected by the agents.
3. Events are forwarded to the Wazuh Manager.
4. The Manager analyzes events according to configured rules.
5. Alerts and event details are reviewed through the Wazuh Dashboard.
6. Repeated failed SSH authentication attempts are used to test Active Response.
7. `firewall-drop` is used to block the detected source IP when the configured condition is met.

## Skills Demonstrated

- Linux system administration
- Basic network configuration
- Virtualized lab design
- Wazuh Manager / Agent architecture
- SIEM fundamentals
- Log collection and event analysis
- SSH authentication monitoring
- Apache2 log monitoring
- Firewall and UFW basics
- Active Response concepts
- Technical documentation
- Security-minded handling of configuration data

## Documentation

### Wazuh Lab

- [Project Overview](Wazuh-Lab/README.md)
- [Architecture](Wazuh-Lab/architecture.md)
- [Methodology](Wazuh-Lab/methodology.md)
- [Test Scenarios](Wazuh-Lab/test-scenarios.md)
- [Findings](Wazuh-Lab/findings.md)
- [Results](Wazuh-Lab/results.md)
- [Active Response](Wazuh-Lab/active-response/firewall-drop.md)
- [Manager Configuration Notes](Wazuh-Lab/configuration/manager.md)
- [Agent Configuration Notes](Wazuh-Lab/configuration/agent.md)
- [Project Roadmap](Wazuh-Lab/roadmap.md)

### General Lab Documentation

- [Kali Linux](documentation/kali-linux.md)
- [Ubuntu Server](documentation/ubuntu-server.md)
- [Network Configuration](documentation/network-configuration.md)
- [SIEM & Security Monitoring](documentation/siem.md)

## Security & Privacy

This repository is intentionally sanitized for public use.

- No real credentials are stored.
- Private keys and certificates are excluded.
- Production configuration is not published.
- Environment-specific IP addresses and sensitive values are omitted where appropriate.
- Testing is limited to systems for which authorization has been granted.

See [`SECURITY.md`](SECURITY.md) for the project's security and responsible-use guidelines.

## Project Status

**Status:** Active learning project

The lab will continue to evolve as new monitoring scenarios, documentation and defensive security exercises are completed.

## Author

**Samet Gündüz**  
Computer Programming Student · Cybersecurity Enthusiast

GitHub: [@SametSec](https://github.com/SametSec)
