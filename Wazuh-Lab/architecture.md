# Lab Architecture

## Systems

| System | Role |
|---|---|
| Ubuntu Server | Wazuh Manager and monitored server in the lab |
| Windows | Wazuh Agent endpoint |
| Kali Linux | Authorized test system and Wazuh Agent |

## Services Used

- Wazuh Manager
- Wazuh Dashboard
- Wazuh Agent
- OpenSSH
- Apache2
- UFW

## Monitoring Flow

1. Agents collect events from the monitored systems.
2. Events are sent to the Wazuh Manager.
3. The Manager analyzes the events and generates alerts when configured rules match.
4. Alerts and event details are reviewed through the Wazuh Dashboard.
5. In the SSH test scenario, repeated failed authentication events are used to test Active Response.
6. `firewall-drop` is used in the lab to block the detected source IP when the configured condition is met.

## Security Scope

The environment is intended for authorized testing only. IP addresses, credentials, certificates and other sensitive configuration values are intentionally omitted from this repository.
