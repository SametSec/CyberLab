# SIEM & Security Monitoring

## Overview

The CyberLab SIEM project is designed to provide centralized log collection, security monitoring and basic event analysis within the isolated laboratory environment.

The project will use the Ubuntu Server as the monitored system and Kali Linux as the security testing workstation.

The main goal is to observe security-related events generated during authorized laboratory activities and analyze them through centralized logs.

## Project Architecture

```text
                    CyberLab Internal Network
                         192.168.50.0/24
                                |
                +---------------+---------------+
                |                               |
                |                               |
          Kali Linux                      Ubuntu Server
       192.168.50.10                    192.168.50.20
        Security Testing                  Log Source
                |                               |
                |                               |
                +------------ SIEM -------------+
                         Security Monitoring
