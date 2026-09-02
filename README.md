# CyberLab

> A practical, virtualized cybersecurity laboratory for learning network security, Linux administration, SIEM, security monitoring and incident response.

CyberLab is a personal lab environment built with Oracle VirtualBox. It brings together Linux systems, Windows endpoints and Wazuh to create a controlled environment for experimenting with security monitoring, log analysis and automated response.

The repository also contains the Wazuh project developed during my software internship, documented separately under [`Wazuh-Lab/`](Wazuh-Lab/).

## 🎯 Goals

- Understand basic network and system security concepts
- Practice Linux and Windows administration in a controlled environment
- Learn centralized log collection and security monitoring with Wazuh
- Analyze SSH authentication and Apache2 web-server events
- Understand alert generation and basic SIEM workflows
- Experiment with Wazuh Active Response in an authorized lab
- Keep practical notes and reproducible documentation for future learning

## 🧰 Technologies

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

## 🏗️ Repository Structure

```text
CyberLab/
├── README.md
├── SECURITY.md
├── .gitignore
├── Wazuh-Lab/
│   ├── README.md
│   ├── architecture.md
│   ├── test-scenarios.md
│   ├── results.md
│   ├── active-response/
│   │   └── firewall-drop.md
│   ├── configuration/
│   │   ├── manager.md
│   │   └── agent.md
│   └── screenshots/
│       └── README.md
│
└── documentation/
    ├── kali-linux.md
    ├── ubuntu-server.md
    ├── network-configuration.md
    └── siem.md
```

## 🔭 Wazuh Project

The internship project focuses on centralized security monitoring with Wazuh. The environment uses Ubuntu Server as the central management system, while Windows and Kali Linux systems are monitored through Wazuh agents.

The lab workflow includes:

```text
 Windows ──────────┐
                   │
 Kali Linux ───────┼──> Wazuh Agent ──> Wazuh Manager
                   │                         │
 Ubuntu Server ────┘                         ▼
                                      Wazuh Dashboard
                                             │
                              ┌──────────────┴──────────────┐
                              │                             │
                         Event Analysis              Active Response
                              │                             │
                         SSH / Apache2               firewall-drop
```

More detailed project documentation is available in [`Wazuh-Lab/`](Wazuh-Lab/).

## 🧪 Main Lab Scenarios

### Agent Monitoring

Wazuh agents are connected to the Manager and their connection status and system information are reviewed through the Dashboard.

### SSH Authentication Monitoring

Successful and failed SSH authentication attempts are generated in the authorized lab environment. The resulting security events are investigated through local logs and Wazuh alerts.

### Apache2 Log Monitoring

Apache2 is used as a monitored web service on Ubuntu Server. HTTP requests are generated from the test system and the resulting access/error logs are examined locally and through Wazuh.

### Active Response

Repeated failed SSH authentication events are used to test Wazuh Active Response. The lab demonstrates how the `firewall-drop` response can block a detected source IP when the configured detection condition is met.

## 🔐 Security & Privacy

This repository is intentionally sanitized for public use.

- No real credentials are stored.
- Private keys and certificates are excluded.
- Production configuration is not published.
- Sensitive IP addressing and environment-specific values are omitted where appropriate.
- Testing is limited to systems for which authorization has been granted.

See [`SECURITY.md`](SECURITY.md) for the repository security policy.

## 📚 Documentation

- [Wazuh Lab](Wazuh-Lab/README.md)
- [Lab Architecture](Wazuh-Lab/architecture.md)
- [Test Scenarios](Wazuh-Lab/test-scenarios.md)
- [Lab Results](Wazuh-Lab/results.md)
- [Active Response](Wazuh-Lab/active-response/firewall-drop.md)
- [Manager Configuration Notes](Wazuh-Lab/configuration/manager.md)
- [Agent Configuration Notes](Wazuh-Lab/configuration/agent.md)
- [Kali Linux](documentation/kali-linux.md)
- [Ubuntu Server](documentation/ubuntu-server.md)
- [Network Configuration](documentation/network-configuration.md)
- [SIEM & Security Monitoring](documentation/siem.md)

## 🚧 Project Status

**Status:** Active learning project

The repository is gradually expanded as new lab exercises, monitoring scenarios and documentation are completed.

## 👤 Author

**Samet Gündüz**

Computer Programming Student · Cybersecurity Enthusiast

GitHub: [@SametSec](https://github.com/SametSec)
