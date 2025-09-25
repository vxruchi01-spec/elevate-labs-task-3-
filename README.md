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

## My Basic Network Scan – Nessus Report

**Scan Date:** Thursday, September 25, 2025  
**Scanner:** Tenable Nessus™  
**Target Host:** 192.168.0.2  

---

## 📊 Scan Summary

| Metric                     | Value                   |
|----------------------------|------------------------|
| Total Vulnerabilities      | 86                     |
| Critical                  | 0                      |
| High                      | 0                      |
| Medium                    | 5                      |
| Low                       | 0                      |
| Informational / Info      | 81                     |

---

## ⚠️ Medium Vulnerabilities

| Vulnerability                                      | CVSS v3.0 Score | Recommendation / Notes                 |
|--------------------------------------------------|----------------|---------------------------------------|
| Remote Desktop Protocol Server MitM Weakness     | 6.5            | Ensure RDP is secured and patched.    |
| SSL Certificate Cannot Be Trusted                | 6.5            | Replace with a trusted CA certificate |
| SSL Self-Signed Certificate                       | 6.5            | Replace with a trusted CA certificate |
| SSL Anonymous Cipher Suites Supported            | 5.9            | Disable anonymous ciphers             |
| nginx < 1.17.7 Information Disclosure           | 5.3            | Upgrade nginx to ≥ 1.17.7             |

---

## ℹ️ Informational Findings
The majority of findings were informational (81) and include details about:

- Installed software: Apache Cassandra, Apache Log4j, ClamAV, Docker  
- Detected services: Remote Desktop Protocol, Docker Se


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
