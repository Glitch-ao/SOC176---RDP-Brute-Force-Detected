# SOC176 - RDP Brute Force Detected

This repo documents an investigation into a brute-force attack on the RDP service of an exposed Windows server.

## Summary

- **Attack Type:** RDP Brute Force
- **Detection Method:** Suricata alerts and Windows Security Logs
- **Tools Used:** SIEM (Kibana), Event Viewer, Zeek

## Key Findings

- Thousands of failed login attempts from IP `X.X.X.X`
- Attack succeeded using weak credentials
- Indicators: Event ID 4625, 4624

## Screenshots

![Failed Login Graph](images/rdp_failed_logins.png)

## Log Samples

See [`logs/security_events.txt`](logs/security_events.txt)

## Analysis Report

See [`analysis_report.md`](analysis_report.md)

## Remediation

- Implement Account Lockout Policy
- Enable MFA for RDP
- Geo-block IPs from risky regions
