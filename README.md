# CyberLab

A personal virtualized cybersecurity laboratory built with Kali Linux and Ubuntu Server using Oracle VirtualBox.

The purpose of this lab is to practice Linux administration, computer networking, cybersecurity concepts, security monitoring and penetration testing in an isolated environment.

## 🏗️ Lab Architecture

```text
                    CyberLab
                       │
              Internal Network
               192.168.50.0/24
                       │
          ┌────────────┴────────────┐
          │                         │
     Kali Linux                Ubuntu Server
     192.168.50.10             192.168.50.20
          │                         │
          └────────────┬────────────┘
                       │
                Security Lab
