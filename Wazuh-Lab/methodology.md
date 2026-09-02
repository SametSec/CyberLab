# Methodology

## Project Approach

The Wazuh project was developed as a controlled cybersecurity lab exercise during a software internship. The goal was to understand how endpoint events can be collected centrally, analyzed and reviewed through a SIEM workflow.

The work followed these stages:

1. Prepare the virtualized systems and network connectivity.
2. Install and configure the Wazuh Manager and Dashboard.
3. Register Wazuh Agents on the monitored systems.
4. Verify agent connectivity and collect system information.
5. Generate controlled SSH authentication events.
6. Generate controlled HTTP requests against Apache2.
7. Review local logs and Wazuh alerts.
8. Test Wazuh Active Response using the `firewall-drop` component.
9. Verify the resulting firewall action and agent status.

## Monitoring Sources

The project focused on practical events that could be generated safely in the lab:

- SSH authentication activity
- Apache2 access and error logs
- Endpoint and operating-system information reported by Wazuh Agents
- Firewall-related events associated with the Active Response test

## Validation Strategy

Each scenario was validated by comparing the expected event flow with the available evidence in local logs, Wazuh alerts and Dashboard views.

The Active Response scenario was considered successful when a repeated failed-authentication condition triggered the configured response and the source address was subsequently blocked by the firewall.

## Scope

The project is a learning and internship lab. It does not represent a production SIEM deployment. Environment-specific addresses, credentials, certificates and other sensitive configuration values are intentionally excluded from the public repository.
