# Incident Response

## Case: INC-001

**Mythic C2 Apollo Agent Compromise - Windows-Target**

**Severity:** Critical

**Tags:** Windows, C2, Mythic, Apollo, RDP-BruteForce, Defense-Evasion, Exfiltration

## Investigation Flow

```text
Alert
  ↓
Initial Triage
  ↓
Event Correlation
  ↓
Attack Timeline Reconstruction
  ↓
Threat Hunting
  ↓
Impact Assessment
  ↓
Containment-Oriented Analysis
  ↓
Incident Documentation
```

## Analyst Objectives

- Establish how the compromise was detected.
- Correlate authentication, process, and network telemetry.
- Reconstruct the sequence of attacker activity.
- Identify relevant MITRE ATT&CK techniques.
- Determine the relationship between the initial access activity and subsequent C2 behavior.
- Document findings in a repeatable incident-response format.

The complete case study, screenshots, investigation evidence, and timeline are included in `../documentation/SOC-Lab-Documentation.pdf`.
