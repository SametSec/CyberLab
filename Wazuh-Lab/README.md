# Wazuh Security Monitoring Lab

This directory documents the Wazuh-based security monitoring work developed during my software internship.

## Project Overview

The lab uses Wazuh to centrally monitor security events from Linux and Windows systems. The main goal is to understand how endpoint events and log data are collected, analyzed and reviewed from a central security monitoring platform.

## Lab Architecture

```text
                           Wazuh Security Lab
                                    |
                    +---------------+---------------+
                    |               |               |
               Ubuntu Server     Windows        Kali Linux
               Manager / Agent     Agent        Agent / Test
                    |               |               |
                    +---------------+---------------+
                                    |
                             Wazuh Manager
                                    |
                             Wazuh Dashboard
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

Controlled successful and failed SSH authentication attempts were generated in the lab and the resulting events were reviewed through Wazuh.

### 3. Apache2 Log Monitoring

HTTP requests were sent to the Apache2 test service on Ubuntu Server. Access and error logs were then inspected and correlated with Wazuh events.

### 4. Active Response

The lab was used to test the Active Response workflow. Repeated failed SSH authentication events were used to trigger the configured response, and the `firewall-drop` action was checked to verify source-IP blocking.

## Documentation

- [Lab Architecture](architecture.md)
- [Test Scenarios](test-scenarios.md)
- [Manager Configuration](configuration/manager.md)
- [Agent Configuration](configuration/agent.md)
- [Active Response / firewall-drop](active-response/firewall-drop.md)
- [Screenshot Guide](screenshots/README.md)

## Security Scope

All tests are intended for authorized and isolated laboratory or internship environments. Real credentials, private keys, certificates, production secrets and environment-specific sensitive values are intentionally excluded from this repository.

## Project Status

The documentation covers the monitoring architecture, test scenarios and Active Response work completed in the lab. Configuration examples in this repository are documentation-oriented and should not be treated as production deployment files.
