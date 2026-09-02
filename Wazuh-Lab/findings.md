# Findings and Observations

## 1. Agent Monitoring

Wazuh Agents were used to connect monitored systems to the Wazuh Manager. Agent status and system information could then be reviewed through the Dashboard.

## 2. SSH Monitoring

Controlled successful and failed SSH authentication attempts produced log events that could be reviewed on the Ubuntu Server and investigated through Wazuh.

Repeated failed authentication attempts were also used as the trigger scenario for the Active Response test.

## 3. Apache2 Monitoring

HTTP requests sent to the Apache2 web server generated entries in the web-server logs. These records were examined locally and then reviewed through Wazuh to understand how application-level activity appears in a central monitoring platform.

## 4. Active Response

The Active Response test demonstrated the intended relationship between detection and automated response: an authentication event matched the configured condition, Wazuh triggered `firewall-drop`, and the source address was blocked by the firewall in the lab environment.

## 5. Overall Result

The project provided practical experience with centralized event collection, alert analysis and a basic detection-to-response workflow. It also demonstrated why endpoint monitoring, log analysis and controlled validation are important parts of a security monitoring process.

## Limitations

The repository documents the lab workflow rather than a production deployment. Exact rule tuning, internal addresses, credentials, certificates and production configuration details are intentionally omitted.
