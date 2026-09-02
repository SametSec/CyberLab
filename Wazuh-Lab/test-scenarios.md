# Test Scenarios

This document summarizes the security-monitoring scenarios performed in the Wazuh lab.

## 1. Agent Connectivity

**Objective:** Verify that monitored systems are connected to the Wazuh Manager.

**Process:**
1. Check the Wazuh Agent service on the monitored endpoint.
2. Open the Wazuh Dashboard.
3. Review the agent list and connection status.
4. Inspect basic system information reported by the agent.

**Expected result:** The configured agents appear in the Dashboard and report their current connection state.

## 2. SSH Authentication Monitoring

**Objective:** Observe how SSH authentication events are collected and detected.

**Process:**
1. Verify that the SSH service is running on Ubuntu Server.
2. Confirm the firewall state used by the lab.
3. Generate authorized successful and failed SSH authentication attempts from the test system.
4. Review the resulting authentication records.
5. Search for the corresponding events in the Wazuh Dashboard.

**Expected result:** Authentication events are collected by the agent and become available for analysis through Wazuh.

## 3. Apache2 Log Monitoring

**Objective:** Monitor web-server activity through Apache2 logs.

**Process:**
1. Verify that Apache2 is running on Ubuntu Server.
2. Confirm that the web service is listening on its configured HTTP port.
3. Open the test web page and generate HTTP requests from the authorized test system.
4. Inspect `access.log` and `error.log` on the server.
5. Review the related events in the Wazuh Dashboard.

**Expected result:** HTTP activity is recorded by Apache2 and the relevant log events can be investigated through Wazuh.

## 4. Active Response Test

**Objective:** Verify the response workflow for repeated failed SSH authentication events.

**Process:**
1. Confirm that the Active Response configuration is enabled in the lab.
2. Verify that the `firewall-drop` response component is available.
3. Generate repeated failed SSH authentication attempts from the authorized test system.
4. Observe the alerts and Active Response events in Wazuh.
5. Verify that the response action is recorded and that the detected source is blocked when the configured condition is met.
6. Check the firewall state to confirm the response.

**Expected result:** The configured Active Response is triggered after the required detection condition is met and the source IP is blocked by the lab firewall mechanism.

## 5. Final Verification

After the scenarios were completed, the agent list and system status were checked again. The purpose was to confirm that the monitored systems remained connected to the Wazuh Manager and that the laboratory environment was left in a known state.

## Notes

These scenarios are documentation of an authorized internship/laboratory environment. Exact credentials, certificates, private configuration values and environment-specific IP addresses are intentionally excluded from the public repository.
