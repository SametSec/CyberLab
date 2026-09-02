# Project Roadmap

This roadmap separates the completed internship work from possible future improvements.

## Completed

- Virtualized laboratory environment prepared
- Wazuh Manager and Dashboard used as the central monitoring platform
- Windows, Ubuntu Server and Kali Linux systems monitored with Wazuh Agents
- SSH authentication events generated and analyzed
- Apache2 HTTP activity generated and analyzed
- Wazuh Active Response tested with `firewall-drop`
- Firewall state verified after the response test
- Architecture, methodology, scenarios, findings and results documented
- Public repository cleaned of environment-specific sensitive values

## Possible Improvements

### Detection Engineering

- Create custom Wazuh rules for selected laboratory events
- Document rule logic and the reason for each detection
- Record false-positive considerations for custom rules

### Endpoint Monitoring

- Add more Windows security-event monitoring scenarios
- Add File Integrity Monitoring examples
- Expand endpoint visibility and system-change monitoring

### Web and Network Monitoring

- Expand Apache2 test cases and alert analysis
- Add additional service-monitoring scenarios within the lab

### Incident Response

- Create a small incident-response report for each scenario
- Document the investigation timeline from event to response
- Record response validation steps and expected outcomes

### Project Quality

- Add sanitized configuration examples when they can be published safely
- Add automated documentation checks or Markdown linting
- Keep the repository structure focused on reproducible defensive security work

Future additions should remain inside an authorized lab environment and should not include credentials, private keys, certificates or sensitive organizational data.
