# CyberLab

A personal virtualized cybersecurity laboratory built with Kali Linux and Ubuntu Server using Oracle VirtualBox.

CyberLab provides an isolated environment for practicing Linux administration, computer networking, cybersecurity, security monitoring, SIEM operations and authorized penetration testing.

## Lab Architecture

```text
                         CyberLab
                            |
                  VirtualBox Internal Network
                       192.168.50.0/24
                            |
             +--------------+--------------+
             |                             |
             |                             |
        Kali Linux                   Ubuntu Server
      192.168.50.10                192.168.50.20
      Security Testing              Monitored Server
             |                             |
             |                             |
             +---------- Wazuh ------------+
                    SIEM / Monitoring
