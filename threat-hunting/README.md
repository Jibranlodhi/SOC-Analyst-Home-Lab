# Threat Hunting

Threat hunting in this lab focused on using centralized endpoint telemetry to investigate suspicious activity and connect individual events into broader attack narratives.

## Hunting Areas

- Authentication anomalies
- New source IP activity
- Suspicious process creation
- PowerShell execution
- RDP authentication patterns
- Network scanning
- C2-related activity
- Correlation of pre-compromise and post-compromise events

## Hunting Approach

```text
Establish Baseline
      ↓
Identify Anomalous Activity
      ↓
Pivot Across Host / User / Network Fields
      ↓
Correlate Related Events
      ↓
Map to ATT&CK
      ↓
Determine Scope and Impact
      ↓
Document Findings
```

The detailed queries, investigation screenshots, findings, and lessons learned are included in `../documentation/SOC-Lab-Documentation.pdf`.
