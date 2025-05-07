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

###

