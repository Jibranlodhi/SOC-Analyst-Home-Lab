# Architecture

## Environment Overview

The SOC Analyst Home Lab was built in Oracle Cloud Infrastructure (OCI) as a segmented security-monitoring environment.

### Network Segmentation

```text
                         ┌──────────────────────────┐
                         │       SOC-Analyst-Lab     │
                         │       172.31.0.0/24       │
                         │                            │
                         │   Elastic / SOC Services  │
                         └────────────┬─────────────┘
                                      │
                           Telemetry / Peering
                                      │
                         ┌────────────┴─────────────┐
                         │        Target-VCN         │
                         │         10.0.0.0/23       │
                         │                            │
                         │ Windows Server / Ubuntu   │
                         └───────────────────────────┘

                         ┌───────────────────────────┐
                         │        Attacker-VCN       │
                         │        10.10.0.0/16       │
                         │                            │
                         │       Kali / C2 Lab      │
                         └───────────────────────────┘
                                  Isolated
```

## Design Goals

- Centralize endpoint telemetry in the SOC environment.
- Separate monitored targets from attacker infrastructure.
- Enable realistic security-event generation without mixing attacker and SOC roles.
- Provide a repeatable environment for detection engineering and incident-response practice.

## Components

| Component | Role |
|---|---|
| Elastic Stack / Fleet | Centralized telemetry, detection, investigation, and endpoint management |
| Windows Server 2022 | Primary Windows monitored endpoint |
| Ubuntu 24.04 | Linux monitored endpoint |
| Kali Linux | Controlled attacker platform |
| Mythic / Apollo | Controlled C2 simulation |
| OCI networking | VCNs, routing, security controls, and connectivity |

For the full deployment details and screenshots, see `../documentation/SOC-Lab-Documentation.pdf`.
