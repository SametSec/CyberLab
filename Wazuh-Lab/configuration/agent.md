# Wazuh Agent Configuration Notes

Wazuh Agents are installed on monitored endpoints and collect relevant system and security events for analysis by the Wazuh Manager.

## Monitored Systems

| System | Role in the Lab |
|---|---|
| Ubuntu Server | Server-side monitoring and log source |
| Windows | Monitored endpoint |
| Kali Linux | Authorized test system and monitored endpoint |

## Monitoring Flow

```text
Endpoint
   │
   ▼
Wazuh Agent
   │
   │ Events
   ▼
Wazuh Manager
   │
   ▼
Wazuh Dashboard
```

## Verification

During the project, agent connection states and system information were checked from the Wazuh Dashboard. SSH and Apache2 activity generated on the monitored systems was then used to verify that relevant events reached the central monitoring platform.

## Security Note

Exact agent configuration values, credentials, certificates and environment-specific addresses are intentionally omitted from the public repository. The documentation describes the architecture and verification process rather than exposing sensitive configuration.
