# CyberLab

> A practical, virtualized cybersecurity laboratory for learning network security, Linux administration, SIEM, security monitoring and incident response.

CyberLab is a personal lab environment built with Oracle VirtualBox. It brings together Linux systems, Windows endpoints and Wazuh to create a controlled environment for experimenting with security monitoring, log analysis and automated response.

The repository also contains the Wazuh project developed during my software internship, documented separately under [`Wazuh-Lab/`](Wazuh-Lab/).

## 🎯 Goals

- Understand network and system security fundamentals
- Practice Linux and Windows administration in a controlled environment
- Learn centralized log collection and security monitoring with Wazuh
- Analyze SSH authentication and Apache2 web-server events
- Understand the basic SIEM detection workflow
- Experiment with Wazuh Active Response in an authorized lab
- Keep clear technical documentation for future learning and portfolio use

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
│
├── Wazuh-Lab/
│   ├── README.md
│   ├── architecture.md
│   ├── methodology.md
│   ├── test-scenarios.md
│   ├── findings.md
│   ├── results.md
│   ├── roadmap.md
│   ├── evidence.md
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

The internship project focuses on centralized security monitoring with Wazuh. The environment uses Ubuntu Server as the central management system, while Windows, Ubuntu and Kali Linux systems are monitored through Wazuh Agents according to the lab scenario.

The main workflow is:

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

### Key Scenarios

**Agent Monitoring**  
Agent connectivity and system information are reviewed through the Wazuh Dashboard.

**SSH Authentication Monitoring**  
Controlled successful and failed SSH authentication attempts are generated and analyzed using local logs and Wazuh alerts.

**Apache2 Log Monitoring**  
HTTP requests are generated against Apache2 and the resulting access/error logs are reviewed locally and through Wazuh.

**Active Response**  
Repeated failed SSH authentication events are used to test the configured Active Response workflow. The lab demonstrates how `firewall-drop` can block the detected source address when the configured condition is met.

## 📋 Project Documentation

Start with the [Wazuh Lab](Wazuh-Lab/README.md), then continue with the [methodology](Wazuh-Lab/methodology.md), [test scenarios](Wazuh-Lab/test-scenarios.md) and [findings](Wazuh-Lab/findings.md).

Additional technical references are available in the [`documentation/`](documentation/) directory.

## 🔐 Security & Privacy

This repository is intentionally sanitized for public use.

- No credentials are stored in the repository.
- Private keys and certificates are excluded.
- Production configuration is not published.
- Environment-specific addresses and sensitive values are omitted where appropriate.
- All security testing is limited to systems for which authorization has been granted.

See [SECURITY.md](SECURITY.md) for the project security scope.

## 🚧 Project Status

**Status:** Active learning project

The lab is expanded gradually as new monitoring scenarios, configuration notes and documentation are completed.

## 👤 Author

**Samet Gündüz**  
Computer Programming Student · Cybersecurity Enthusiast

GitHub: [@SametSec](https://github.com/SametSec)
