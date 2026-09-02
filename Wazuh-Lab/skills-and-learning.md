# Skills Demonstrated and Learning Outcomes

This document summarizes the technical skills practiced through the Wazuh internship project. It focuses on work that was actually performed in the laboratory rather than listing unrelated technologies.

## Technical Skills

| Skill | How It Was Practiced |
|---|---|
| Linux system administration | Ubuntu Server service checks, SSH configuration checks and firewall management |
| Network configuration | Virtual machine networking, IP/hostname checks and connectivity validation |
| Virtualization | Building and operating a multi-system VirtualBox laboratory |
| Wazuh administration | Manager, Agent and Dashboard workflow |
| SIEM fundamentals | Centralized event collection, detection, alert review and response |
| Log analysis | SSH authentication logs and Apache2 `access.log` / `error.log` analysis |
| Security monitoring | Endpoint status, event investigation and alert review |
| Firewall management | UFW checks and validation of the response action |
| Active Response | Testing the `firewall-drop` response workflow |
| Technical documentation | Recording architecture, methodology, scenarios, findings and results |

## What I Learned

### From Endpoint Monitoring

I learned how a Wazuh Agent provides visibility into a monitored system and how agent status and system information can be reviewed centrally instead of checking every system independently.

### From Log Analysis

I learned that application and authentication logs are useful security data sources. SSH authentication events and Apache2 access/error records can be examined locally and then investigated through a central monitoring platform.

### From the SIEM Workflow

I learned the basic relationship between an event source, an agent, a central manager and a dashboard. This helped me understand the path from raw system activity to a security event that can be investigated.

### From Active Response

I learned how detection can lead to an automated defensive action. In the lab scenario, repeated failed SSH authentication events were used to test a configured Active Response and the `firewall-drop` mechanism.

### From Validation

I learned that a security test should not be considered complete from a single screen or command alone. The project compared local logs, Wazuh event data and firewall state to validate the expected result.

### From Security Practices

I learned the importance of separating technical documentation from sensitive environment details. The public repository therefore avoids real credentials, private keys, certificates and unnecessary environment-specific addresses.

## Skills Summary

The strongest skills demonstrated by this project are:

**Linux Administration · Networking Basics · Virtualization · Wazuh · SIEM Fundamentals · Log Analysis · Security Monitoring · Firewall Management · Active Response · Technical Documentation**

## Scope

These skills were developed through a controlled internship/laboratory environment. The project is educational and defensive in scope and should not be interpreted as a production SIEM deployment.
