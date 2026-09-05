# Detection Engineering

The lab developed and validated seven security detections against telemetry generated in the environment.

| # | Detection | Detection Type | MITRE ATT&CK | Severity |
|---|---|---|---|---|
| 1 | SSH Brute Force | Threshold | T1110.001 | Medium |
| 2 | SSH Login from New Source IP | New Terms | T1078.003 | High |
| 3 | Suspicious Process Creation | Custom Query | T1059.003 | Medium |
| 4 | PowerShell Encoded Command | Custom Query | T1027 | High |
| 5 | RDP Brute Force | Threshold | T1110.001 | High |
| 6 | Network Scan Detection | Custom Query | T1046 | Low |
| 7 | RDP Brute Force Followed by Successful Login | EQL Sequence | T1110 + T1078 | Critical |

## Detection Philosophy

The project emphasized validating detections against the actual telemetry available in the lab rather than assuming that prebuilt rules would work unchanged. Differences in index and field mappings required several custom queries.

## Validation

Detection validation was performed by generating controlled security events and confirming that the resulting telemetry could be observed and correlated in Elastic.

See the complete project report in `../documentation/SOC-Lab-Documentation.pdf` for the implementation details, screenshots, troubleshooting, and validation results.
