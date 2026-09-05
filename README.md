# SOC Analyst Home Lab

A practical Security Operations Center (SOC) lab built in Oracle Cloud Infrastructure (OCI) to demonstrate hands-on experience with security monitoring, endpoint telemetry, detection engineering, threat hunting, incident response, and controlled adversary simulation.

> **Project status:** Completed — all OCI lab infrastructure was decommissioned after the project. The public IP addresses and ports documented in the report are historical lab values and are no longer active.

## Overview

This project was designed as a realistic SOC environment combining a centralized Elastic security stack with Windows and Linux telemetry, custom detection rules, and a controlled attacker infrastructure.

The lab covers the full defensive workflow:

**Collect → Detect → Investigate → Hunt → Respond → Document**

## Architecture

The environment used three logical OCI networks:

| Network | CIDR | Purpose |
|---|---|---|
| `SOC-Analyst-Lab` | `172.31.0.0/24` | SOC infrastructure and monitoring |
| `Target-VCN` | `10.0.0.0/23` | Windows/Linux monitored endpoints |
| `Attacker-VCN` | `10.10.0.0/16` | Isolated adversary simulation |

Target-to-SOC connectivity was established for telemetry collection, while the attacker environment remained logically separated from the monitoring infrastructure.

## Technology Stack

- **Oracle Cloud Infrastructure (OCI)**
- **Elastic Stack 9.4.2**
- **Elastic Fleet / Elastic Agent**
- **Windows Server 2022**
- **Ubuntu 24.04**
- **Kali Linux**
- **Mythic C2 / Apollo**
- **Nmap**
- **RDP / SSH**
- **MITRE ATT&CK**

## Detection Engineering

Seven custom/validated detections were developed or tested during the project:

| Detection | Method | MITRE ATT&CK | Severity |
|---|---|---|---|
| SSH Brute Force | Threshold | T1110.001 | Medium |
| SSH Login from New Source IP | New Terms | T1078.003 | High |
| Suspicious Process Creation | Custom Query | T1059.003 | Medium |
| PowerShell Encoded Command | Custom Query | T1027 | High |
| RDP Brute Force | Threshold | T1110.001 | High |
| Network Scan Detection | Custom Query | T1046 | Low |
| RDP Brute Force → Successful Login | EQL Sequence | T1110 + T1078 | Critical |

The project also documents differences between prebuilt Elastic detection rules and the actual index/field mappings available in the lab, including the resulting use of custom detections.

## Adversary Simulation

A controlled attack scenario was used to generate realistic telemetry and validate the defensive pipeline. Activities included:

1. Network reconnaissance with Nmap
2. RDP brute-force simulation
3. Initial access validation
4. Mythic C2 / Apollo deployment
5. Defense-evasion activity
6. Data-exfiltration simulation
7. Detection and investigation in Elastic

All testing was performed against infrastructure created specifically for the lab.

## Incident Response

The project includes a complete incident-response case study:

**INC-001 — Mythic C2 Apollo Agent Compromise - Windows-Target**

Severity: **Critical**

The investigation demonstrates how multiple detections can be correlated into an attack narrative, followed by investigation, threat hunting, containment-oriented analysis, and documentation.

## What This Project Demonstrates

- SOC monitoring and alert investigation
- Endpoint telemetry collection
- Elastic Security and Fleet administration
- Detection engineering
- MITRE ATT&CK mapping
- Windows security monitoring
- Linux/SSH monitoring
- RDP attack detection
- PowerShell detection
- Network reconnaissance detection
- Threat hunting
- Incident response
- Cloud networking and troubleshooting
- Adversary simulation in a controlled environment

## Documentation

The complete technical project write-up is maintained in the repository under:

`documentation/SOC-Lab-Documentation.pdf`

The report contains the architecture, deployment process, telemetry configuration, detection engineering, attack simulation, incident response, troubleshooting, detection summary, and lessons learned.

## Key Lessons Learned

- Cloud-level firewall rules are only one layer of network security; host-level controls must also be validated.
- Correct architecture is often more maintainable than relying on workarounds.
- Detection rules must be validated against the actual telemetry and field mappings in the environment.
- Threshold tuning is essential for balancing detection coverage and false positives.
- Complex SOC troubleshooting often involves several independent configuration issues compounding together.
- Clear documentation is part of effective security operations.

## Disclaimer

This repository documents a personal cybersecurity lab conducted for educational, defensive-security, and controlled adversary-simulation purposes. The infrastructure was temporary and has been fully decommissioned. Historical IP addresses, ports, and configuration details shown in the documentation do not represent currently accessible systems.

---

**Author:** Jibran Khan  
**GitHub:** [Jibranlodhi](https://github.com/Jibranlodhi)
