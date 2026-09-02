# Wazuh Security Monitoring Lab

This directory documents the Wazuh-based security monitoring work developed during my software internship.

## 30-Second Overview

This project demonstrates a small, controlled security-monitoring environment built with Wazuh. Ubuntu Server hosts the central Wazuh Manager and is also monitored as a server; Windows and Kali Linux participate as monitored endpoints. The lab focuses on endpoint visibility, SSH authentication monitoring, Apache2 log analysis and a detection-to-response workflow using Wazuh Active Response.

## Project Architecture

```text
                         Monitored / Test Systems

        +----------------+----------------+----------------+
        |                                 |                |
        v                                 v                v
   Ubuntu Server                       Windows        Kali Linux
   Manager + Agent                      Agent        Agent + Test
   SSH / Apache2 Logs
        |                                 |                |
        +----------------+----------------+----------------+
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
     Alert / Event Review       firewall-drop
                                      |
                                      v
                              Source IP blocked
```

### Component Roles

| Component | Role |
|---|---|
| Wazuh Manager | Central event collection, analysis and alert management |
| Wazuh Dashboard | Investigation and visualization interface |
| Wazuh Agent | Collects endpoint and security events |
| Ubuntu Server | Manager host and monitored server; SSH and Apache2 log source |
| Windows | Monitored endpoint |
| Kali Linux | Authorized test system and monitored endpoint |
| OpenSSH | Authentication event source used in the SSH scenario |
| Apache2 | Web-service and access/error-log source |
| UFW | Firewall state used during the response validation |

## Monitoring Pipeline

The core workflow can be summarized as:

```text
Event Source
    |
    v
Wazuh Agent
    |
    v
Wazuh Manager
    |
    +----> Detection / Alert
    |             |
    |             v
    |       Wazuh Dashboard
    |
    +----> Active Response
                  |
                  v
             firewall-drop
```

## Main Components

- **Wazuh Manager** — central component for receiving and analyzing agent events.
- **Wazuh Dashboard** — interface used to review alerts, events and endpoint information.
- **Wazuh Agent** — installed on monitored systems to collect relevant security and system data.
- **Ubuntu Server** — used for server-side monitoring and SSH/Apache2 log analysis.
- **Windows** — monitored endpoint.
- **Kali Linux** — authorized test system used to generate controlled test events.

## Test Scenarios

### 1. Agent Monitoring

Agent status and endpoint information were reviewed from the Wazuh Dashboard.

### 2. SSH Authentication Monitoring

Controlled successful and failed SSH authentication attempts were generated in the lab. The resulting authentication events were reviewed locally and through Wazuh.

### 3. Apache2 Log Monitoring

HTTP requests were sent to the Apache2 test service on Ubuntu Server. Access and error logs were inspected and related events were reviewed through Wazuh.

### 4. Active Response

Repeated failed SSH authentication events were used to test the configured Active Response workflow. The `firewall-drop` action was observed and the resulting firewall state was checked.

## Skills Demonstrated

The project provides practical evidence of the following skills:

| Skill | Demonstrated Through |
|---|---|
| Linux administration | Ubuntu Server setup, service checks and firewall management |
| Network configuration | Virtual machine connectivity and private lab networking |
| Virtualization | Building and operating a multi-system VirtualBox lab |
| SIEM fundamentals | Centralized event collection, detection, alert review and response |
| Wazuh administration | Manager, Dashboard and Agent workflow |
| Log analysis | SSH authentication and Apache2 access/error logs |
| Security monitoring | Endpoint status, event investigation and alert analysis |
| Incident-response basics | Detection followed by a controlled automated response |
| Firewall management | UFW state checks and response validation |
| Technical documentation | Architecture, methodology, scenarios, findings and results |

## What I Learned

- How a SIEM-style monitoring workflow connects endpoints, a central manager and an investigation interface.
- How authentication activity can be traced from local system logs into centralized security events.
- How Apache2 access and error logs can be useful sources for security monitoring.
- How endpoint agents provide visibility into monitored systems.
- How detection and response are connected through Wazuh Active Response.
- How `firewall-drop` can be used in a controlled lab to demonstrate an automated blocking response.
- Why testing should be validated from more than one point of view, such as local logs, Wazuh events and firewall state.
- Why production credentials, certificates, internal addresses and other sensitive configuration values should not be included in public documentation.

## Documentation

- [Lab Architecture](architecture.md)
- [Methodology](methodology.md)
- [Test Scenarios](test-scenarios.md)
- [Findings and Observations](findings.md)
- [Results](results.md)
- [Manager Configuration](configuration/manager.md)
- [Agent Configuration](configuration/agent.md)
- [Active Response / firewall-drop](active-response/firewall-drop.md)

## Security Scope

All tests described here are intended for authorized and isolated laboratory or internship environments. Real credentials, private keys, certificates, production secrets and environment-specific sensitive values are intentionally excluded from this repository.

## Project Status

The documented internship scenarios are complete. The roadmap lists defensive monitoring improvements that can be explored later in a separate authorized lab environment.
