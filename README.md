# Elevate Labs – Task 3  
**Perform a Basic Vulnerability Scan on My PC**

---

## Task Objective
Perform a basic vulnerability scan on my personal computer using a free vulnerability scanning tool (Nessus Essentials or OpenVAS) to identify potential security issues.

---

## Tool Used
**Nessus Essentials**  
- Chosen for its beginner-friendly interface and robust scanning capabilities.

---

## Scan Setup
- **Target:** Local machine (`127.0.0.1`)  
- **Scan Type:** Basic Network Scan  
- **Estimated Duration:** ~45 minutes  

---

## Summary of Findings

| Metric                    | Value                     |
|----------------------------|---------------------------|
| Scan Name                 | Local Vulnerability Scan  |
| Plugin Feed Version       | 202505290308              |
| Scan Duration             | 18 minutes                |
| Hosts Scanned             | 3 (Local and LAN)         |
| Critical Vulnerabilities  | 1                         |
| High Vulnerabilities      | 4                         |
| Medium Vulnerabilities    | 2                         |
| Info / Low                | 74+                       |

---

## Critical & High Vulnerabilities

### 1. Node.js Multiple Vulnerabilities (CVE-2024-21892, CVE-2024-22019, etc.)
- **Severity:** Critical  
- **Affected Package:** Node.js v20.11.0  
- **Description:** Multiple high-risk vulnerabilities impacting HTTP processing, path traversal, DoS, and crypto timing attacks.  
- **Recommendation:** Upgrade to Node.js version `20.11.1` or higher.

### 2. Tornado Python Library DoS (CVE-2025-47287)
- **Severity:** High  
- **Issue:** Denial-of-service vulnerability in Tornado versions < 6.5.0.  
- **Recommendation:** Upgrade to Tornado version `6.5.0`.

### 3. SSL Certificate Cannot Be Trusted
- **Severity:** Medium  
- **Issue:** Self-signed SSL certificate used by Nessus web interface.  
- **Recommendation:** Use a certificate issued by a trusted CA if exposed publicly.

---

## Lessons Learned
- Practiced identifying and prioritizing vulnerabilities using CVSS scores.  
- Observed how outdated software packages (Node.js, Tornado) can pose significant security risks.  
- Learned basic remediation techniques, such as updating software and using trusted certificates.

---

## 🖼️ Screenshots Included
- Scan summary dashboard  
- Vulnerabilities listed by severity  
- Detailed CVE information (Node.js, Tornado, SSL)  
- Host details (IP, MAC, OS)  

---

## Key Concepts Covered
- Vulnerability scanning fundamentals  
- Using Nessus Essentials effectively  
- Interpreting CVSS scores  
- Identifying critical system vulnerabilities  
- Planning and implementing basic remediation steps  

---

##  How to Run This Scan Yourself
```bash
# Start Nessus service
sudo systemctl start nessusd
sudo systemctl enable nessusd

# Open Nessus web interface
firefox https://127.0.0.1:8834

# Create a new scan
# 1. Select "Basic Network Scan"
# 2. Target: 127.0.0.1
# 3. Launch scan and review results
