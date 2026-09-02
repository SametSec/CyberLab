# Wazuh Manager Configuration Notes

The Wazuh Manager acts as the central management and analysis component of the laboratory.

## Responsibilities

- Receive events from Wazuh agents
- Analyze collected security events
- Apply configured detection rules
- Generate alerts for matching events
- Coordinate Active Response actions
- Provide data for investigation through the Wazuh Dashboard

## Lab Architecture

```text
Wazuh Agents
     │
     ▼
Wazuh Manager
     │
     ├── Detection Rules
     ├── Alerts
     └── Active Response
     │
     ▼
Wazuh Dashboard
```

## Configuration Approach

The internship environment used the Wazuh Manager as the central point for the monitored systems. Configuration was tested through the lab and the resulting events were verified in the Dashboard.

Exact configuration files are not published here because they may contain environment-specific values. If configuration examples are added later, they will be clearly marked as sanitized examples.

## Security Considerations

Do not publish:

- Credentials
- Private keys
- Certificates
- Internal production addresses
- Tokens or secrets
- Unnecessary environment-specific configuration
