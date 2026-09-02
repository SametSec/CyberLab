# Lab Architecture

## Purpose

The Wazuh lab was built to understand the flow from endpoint activity to centralized security monitoring and, in the Active Response scenario, from detection to automated response.

## Systems and Roles

| System | Role |
|---|---|
| Ubuntu Server | Wazuh Manager host and monitored server |
| Windows | Wazuh Agent endpoint |
| Kali Linux | Authorized test system and Wazuh Agent |

## Core Services

| Service | Purpose in the Lab |
|---|---|
| Wazuh Manager | Receives and analyzes events from agents |
| Wazuh Dashboard | Provides centralized event, alert and endpoint visibility |
| Wazuh Agent | Collects endpoint and security-related events |
| OpenSSH | Source of authentication events |
| Apache2 | Source of HTTP access and error logs |
| UFW | Firewall state used for response validation |

## End-to-End Architecture

```text
                         +----------------------+
                         |   Ubuntu Server      |
                         | Manager + Agent      |
                         | SSH / Apache2 Logs   |
                         +----------+-----------+
                                    |
                         +----------+-----------+
                         |                      |
              +----------v----------+  +------v-------+
              |       Windows       |  |   Kali Linux |
              |     Wazuh Agent     |  | Agent + Test |
              +----------+----------+  +------+-------+
                         |                      |
                         +----------+-----------+
                                    |
                                    v
                             +-------------+
                             | Wazuh        |
                             | Manager      |
                             +------+------+
                                    |
                       +------------+------------+
                       |                         |
                       v                         v
                Wazuh Dashboard          Active Response
                       |                         |
                       v                         v
                Event / Alert Review      firewall-drop
                                                 |
                                                 v
                                          Firewall Action
```

## Event Flow

1. A monitored system generates an event, such as an SSH authentication event or an Apache2 log entry.
2. The Wazuh Agent collects the relevant event data.
3. The event is sent to the Wazuh Manager.
4. The Manager evaluates the event using its configured analysis and detection logic.
5. Matching events become available for investigation through the Wazuh Dashboard.
6. In the Active Response scenario, the configured condition can trigger `firewall-drop`.
7. The firewall state is then checked to validate the response.

## Architectural Notes

The same Ubuntu Server can serve both as the Wazuh Manager host and as a monitored server in this learning environment. This keeps the lab compact while allowing server-side logs such as SSH and Apache2 to be observed through the monitoring platform.

The public repository intentionally avoids real IP addresses, credentials, certificates and other environment-specific values.

## Security Scope

This architecture represents an authorized learning and internship environment. It is not presented as a production-ready SIEM architecture. Any future experiments should remain within systems for which explicit authorization exists.
