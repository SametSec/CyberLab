# CyberLab

> A practical, virtualized cybersecurity laboratory for learning network security, Linux administration, SIEM, security monitoring and incident response.

CyberLab is a personal lab environment built with Oracle VirtualBox. It combines Linux systems, Windows endpoints and Wazuh to provide a controlled environment for security-monitoring, log-analysis and defensive-response exercises.

The main project in this repository is the Wazuh security-monitoring lab developed during my software internship.

## 30-Second Overview

| Area | What this project demonstrates |
|---|---|
| Platform | Wazuh Manager, Wazuh Dashboard and Wazuh Agents |
| Systems | Ubuntu Server, Windows and Kali Linux |
| Monitoring | Endpoint status, SSH authentication and Apache2 logs |
| Detection | Security-event collection and alert analysis |
| Response | Wazuh Active Response with `firewall-drop` |
| Environment | Controlled virtualized laboratory |

## Architecture

```text
                         CyberLab Monitoring Architecture

   Ubuntu Server              Windows              Kali Linux
   Manager + Agent             Agent              Agent + Test
   SSH / Apache2 Logs
          \                      |                    /
           \                     |                   /
            +--------------------+------------------+
                                 |
                                 v
                          Wazuh Manager
                                 |
                    +------------+------------+
                    |                         |
                    v                         v
             Wazuh Dashboard          Active Response
                    |                         |
                    v                         v
             Event / Alert Review       firewall-drop
                                              |
                                              v
                                       Firewall Action
```

The public repository intentionally omits environment-specific IP addresses, credentials, certificates and other sensitive values.

## Project Goals

- Understand network and system security fundamentals
- Practice Linux and Windows administration in a controlled environment
- Learn centralized security-event collection with Wazuh
- Analyze SSH authentication and Apache2 activity
- Understand the detection-to-response workflow
- Document practical cybersecurity work clearly and safely

## Technologies

| Area | Technologies |
|---|---|
| Virtualization | Oracle VirtualBox |
| Security Testing | Kali Linux |
| Server | Ubuntu Server |
| Endpoint Monitoring | Wazuh Agent on Windows, Ubuntu Server and Kali Linux |
| SIEM / Monitoring | Wazuh Manager, Wazuh Dashboard, Wazuh Agent |
| Authentication | OpenSSH |
| Web Server | Apache2 |
| Firewall | UFW |

## Wazuh Internship Project

The internship project follows this monitoring pipeline:

```text
Endpoint Event
      |
      v
Wazuh Agent
      |
      v
Wazuh Manager
      |
      +----> Detection / Alert ----> Wazuh Dashboard
      |
      +----> Active Response -----> firewall-drop
```

### Scenarios Performed

1. Agent connectivity and endpoint information were verified.
2. Successful and failed SSH authentication events were generated and analyzed.
3. Apache2 HTTP activity was generated and its `access.log` and `error.log` records were reviewed.
4. Repeated failed SSH authentication was used to test the Active Response workflow.
5. The resulting `firewall-drop` action and firewall state were verified.

## Skills Demonstrated

| Skill | Practical Demonstration |
|---|---|
| Linux administration | Ubuntu Server service and firewall management |
| Network configuration | Virtual machine networking and connectivity checks |
| Virtualization | Multi-system VirtualBox laboratory setup |
| SIEM fundamentals | Centralized event collection, detection and alert review |
| Wazuh | Manager, Agent, Dashboard and Active Response workflow |
| Log analysis | SSH and Apache2 log investigation |
| Security monitoring | Endpoint visibility and event investigation |
| Incident-response basics | Detection followed by a controlled automated response |
| Firewall management | UFW checks and response validation |
| Technical documentation | Architecture, methodology, scenarios, findings and results |

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
│   ├── skills-and-learning.md
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

## Documentation

### Wazuh Lab

- [Project Overview](Wazuh-Lab/README.md)
- [Architecture](Wazuh-Lab/architecture.md)
- [Methodology](Wazuh-Lab/methodology.md)
- [Test Scenarios](Wazuh-Lab/test-scenarios.md)
- [Findings and Observations](Wazuh-Lab/findings.md)
- [Results](Wazuh-Lab/results.md)
- [Skills Demonstrated and Learning Outcomes](Wazuh-Lab/skills-and-learning.md)
- [Manager Configuration Notes](Wazuh-Lab/configuration/manager.md)
- [Agent Configuration Notes](Wazuh-Lab/configuration/agent.md)
- [Active Response](Wazuh-Lab/active-response/firewall-drop.md)
- [Project Roadmap](Wazuh-Lab/roadmap.md)

### General Lab Documentation

- [Kali Linux](documentation/kali-linux.md)
- [Ubuntu Server](documentation/ubuntu-server.md)
- [Network Configuration](documentation/network-configuration.md)
- [SIEM & Security Monitoring](documentation/siem.md)

## Security & Privacy

This repository is intentionally sanitized for public use.

- No credentials, private keys or certificates are stored.
- Production configuration is not published.
- Environment-specific addresses and sensitive values are omitted where appropriate.
- Testing is limited to authorized laboratory systems.

See [SECURITY.md](SECURITY.md) for the project's responsible-use guidelines.

## Project Status

**Internship scenarios:** Completed  
**Repository:** Active learning project

Future work will focus on additional defensive monitoring scenarios and better detection documentation.

## Author

**Samet Gündüz**  
Computer Programming Student · Cybersecurity Enthusiast

GitHub: [@SametSec](https://github.com/SametSec)
