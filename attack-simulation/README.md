# Attack Simulation

This section documents the controlled adversary activity used to generate telemetry and validate the SOC's detection and investigation workflow.

## Simulation Flow

```text
Reconnaissance
      ↓
Nmap Scanning
      ↓
RDP Brute Force
      ↓
Successful Access
      ↓
Mythic C2 / Apollo
      ↓
Defense Evasion
      ↓
Exfiltration Simulation
      ↓
Elastic Detection & Investigation
```

## Activities

- Network reconnaissance with Nmap
- RDP brute-force simulation
- Controlled access validation
- Mythic C2 / Apollo deployment
- Defense-evasion activity
- Data-exfiltration simulation
- Detection and investigation in Elastic

## Purpose

The objective was not to demonstrate exploitation for its own sake, but to create realistic security telemetry that could be detected, investigated, correlated, and documented from a SOC analyst perspective.

All activity was conducted against temporary lab infrastructure created specifically for the project. The infrastructure has since been decommissioned.

See `../documentation/SOC-Lab-Documentation.pdf` for the detailed attack narrative and evidence.
