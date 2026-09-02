# Wazuh Active Response — firewall-drop

## Overview

Wazuh Active Response provides an automated response mechanism when a monitored event satisfies a configured security condition.

In this lab, `firewall-drop` was used to demonstrate a controlled response to repeated failed SSH authentication events.

## Workflow

```text
Failed SSH Authentication
          │
          ▼
     Wazuh Agent
          │
          ▼
    Wazuh Manager
          │
          ▼
   Detection / Alert
          │
          ▼
   Active Response
          │
          ▼
    firewall-drop
          │
          ▼
  Source IP blocked
```

## Test Process

1. Confirm that the SSH service and Wazuh Agent are running.
2. Verify the Active Response configuration.
3. Generate repeated failed SSH authentication attempts in the authorized lab.
4. Observe the resulting alerts in the Wazuh Dashboard.
5. Check the Active Response event to determine whether `firewall-drop` was triggered.
6. Verify the resulting firewall state.

## Result

The test demonstrated the relationship between authentication events, Wazuh detection and an automated firewall response. When the configured detection condition was reached, the `firewall-drop` mechanism was observed blocking the detected source IP.

## Security Note

The repository does not contain the production or internship environment's exact rules, credentials, IP addresses or certificates. This page documents the concept and observed workflow rather than publishing environment-specific security configuration.
