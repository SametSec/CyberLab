# Wazuh Lab Results

## Agent Monitoring

Wazuh Agent connections and endpoint information were checked through the Wazuh Dashboard. The monitored systems were visible in the central monitoring interface.

## SSH Monitoring

Controlled SSH authentication attempts were generated in the authorized laboratory environment. The corresponding authentication events were reviewed in the local logs and in Wazuh.

## Apache2 Monitoring

HTTP requests were generated against the Apache2 test service running on Ubuntu Server. Apache access and error logs were examined and related events were reviewed through Wazuh.

## Active Response

The Active Response workflow was tested using repeated failed SSH authentication events. The configured `firewall-drop` action was observed in the Wazuh event data, and the blocking result was checked on the firewall side.

## Outcome

The project provided practical experience with centralized endpoint monitoring, security-event analysis, log inspection, alert review and basic automated response using Wazuh.

## Scope Note

This report summarizes the laboratory work and intentionally excludes real IP addresses, credentials, certificates and other sensitive environment-specific values.
