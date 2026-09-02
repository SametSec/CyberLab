# Evidence and Documentation Guide

This repository intentionally separates the project documentation from the screenshots and other evidence collected during the internship.

## Recommended Evidence

For each major scenario, useful evidence includes:

- Wazuh Dashboard views showing the relevant alert or event
- Agent status and system-information views
- Sanitized SSH log records
- Sanitized Apache2 access/error log records
- Active Response events showing the response action
- Firewall output confirming the response result

## Sanitization Rules

Before publishing an image or log excerpt, remove or mask:

- Usernames and passwords
- API tokens and authentication material
- Private keys and certificates
- Real organizational IP addresses when they are not necessary
- Hostnames or system names that identify protected infrastructure
- Personal information
- Internal URLs and other sensitive configuration values

## Suggested Naming

Use descriptive names such as:

```text
01-agent-status.png
02-ssh-alert.png
03-apache-access.png
04-active-response.png
05-firewall-verification.png
```

The purpose of this folder is to make the evidence reproducible and easy to understand without exposing sensitive information.
