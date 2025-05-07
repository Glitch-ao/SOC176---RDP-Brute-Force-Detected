# SOC176 - RDP Brute Force Detected


In this project, I investigated a simulated security incident on the LetsDefend platform, where a Windows machine was targeted by a brute-force attack on the Remote Desktop Protocol (RDP). The attacker attempted multiple login attempts using various usernames, eventually gaining unauthorized access to the system.

## 🧠 Key Takeaways

- **Identified** a brute-force attack targeting RDP on a Windows machine.
- **Analyzed** Windows Security Event Logs to trace failed and successful login attempts.
- **Detected** post-compromise activities indicating potential privilege escalation.
- **Mapped** the attack techniques to the MITRE ATT&CK framework.
- **Recommended** mitigation strategies to prevent similar future incidents.

---

## 🛡️ Incident Overview

- **Alert Name:** SOC176 - RDP Brute Force Detected
- **Detection Time:** March 7, 2024, 11:44 AM UTC
- **Affected Hostname:** Matthew
- **IP Address:** 172.16.17.148
- **Severity Level:** Medium
- **MITRE ATT&CK Techniques:**
  - T1110 – Brute Force
  - T1078 – Valid Accounts
  - T1059 – Command and Scripting Interpreter
  - T1087 – Account Discovery

---

## 🔍 Investigation Steps

### 1. Alert Analysis

Upon receiving the alert, I noted multiple failed login attempts from the external IP address `218.92.0.56` targeting the host `Matthew` over RDP (port 3389). The usernames attempted included `admin`, `guest`, and `sysadmin`.

### 2. Log Analysis

Using the Log Management module, I filtered Security Event Logs for Event ID `4625` (failed login attempts) and found numerous entries corresponding to the attacker's IP. Subsequently, an Event ID `4624` (successful login) was recorded for the username `Matthew`, indicating a successful breach.

### 3. Endpoint Investigation

Examining the endpoint details for `Matthew`, I discovered unusual command executions in the terminal history:

- `whoami`
- `net user`
- `net localgroup`
- `netstat`

These commands suggest the attacker was attempting to gather system information and enumerate user accounts, possibly for privilege escalation.

### 4. Threat Intelligence

Checking the reputation of the source IP `218.92.0.56` on platforms like VirusTotal and AbuseIPDB confirmed it as malicious, reinforcing the legitimacy of the alert.

---

## 🧰 Tools & Techniques Used

- **LetsDefend Platform:** For alert monitoring, log analysis, and endpoint investigation.
- **Windows Event Viewer:** To analyze Security Event Logs (Event IDs 4624 and 4625).
- **Threat Intelligence Platforms:** VirusTotal and AbuseIPDB for IP reputation checks.
- **MITRE ATT&CK Framework:** For mapping and understanding the attack techniques.

---

## 📝 Recommendations

- **Enforce Strong Password Policies:** Implement complex password requirements and regular password changes.
- **Implement Account Lockout Policies:** Lock accounts after a defined number of failed login attempts to prevent brute-force attacks.
- **Enable Multi-Factor Authentication (MFA):** Especially for remote access services like RDP.
- **Restrict RDP Access:** Limit RDP access to trusted IP addresses using firewalls or VPNs.
- **Regular Monitoring:** Continuously monitor Security Event Logs for unusual login activities.

---

## 📸 Screenshots & Artifacts

*(Include relevant screenshots such as alert details, Event Log entries, and terminal command histories.)*

---



