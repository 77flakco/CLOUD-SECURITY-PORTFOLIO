# 🛡️ GCP Security Incident Response & Remediation

![Status](https://img.shields.io/badge/Status-Completed-success)
![Platform](https://img.shields.io/badge/Google_Cloud-Platform-blue)
![Focus](https://img.shields.io/badge/Focus-Incident_Response-red)
![Compliance](https://img.shields.io/badge/Compliance-PCI_DSS-green)

📖 Project Overview
A cloud security simulation focused on **identifying, containing, and remediating** a data breach within a Google Cloud environment. 

Acting as the Lead Security Engineer, I utilized **Security Command Center (SCC)** to detect active malware and exposed PII, eventually restoring the infrastructure to full **PCI DSS 3.2.1 compliance**.

---

🏗️ Architecture & Tech Stack
| Component | Service Used | Purpose |
| :--- | :--- | :--- |
| **Detection** | Security Command Center | Vulnerability scanning & Threat detection |
| **Compute** | Compute Engine (GCE) | VM Hardening & Snapshot Recovery |
| **Storage** | Cloud Storage (GCS) | ACL Management & Uniform Access |
| **Network** | VPC Firewall | Traffic Analysis & IAP Implementation |
| **Identity** | IAM | Least Privilege Enforcement |

---

⚡ The Scenario: "The Breach"
**The Alert:** Unusual activity detected in the `cc-app-01` instance and public access logs on a sensitive storage bucket.

The Findings (via SCC):**
* 🚨 **Critical:** Malware detected on `cc-app-01` (Bad Domain connection).
* 🚨 **Critical:** Storage bucket containing Credit Card data was **publicly accessible**.
* 🚨 **High:** Firewall allowed **0.0.0.0/0** access on ports 22 (SSH) and 3389 (RDP).
* ⚠️ **Medium:** Secure Boot disabled & Default Service Account in use.

---

🛠️ Remediation Actions

1️⃣ Compute Engine (Containment & Recovery)
- [x] **Stopped** the compromised VM immediately.
- [x] **Restored** service using a clean disk snapshot (`cc-app-02`).
- [x] **Hardened** the new instance:
    - Enabled **Shielded VM (Secure Boot)**.
    - Removed Public IP address.
    - Replaced Default Service Account with a custom User SA.

2️⃣ Network Hardening (Zero Trust)
- [x] **Deleted** overly permissive rules (`default-allow-ssh`, `default-allow-rdp`).
- [x] **Implemented** Identity-Aware Proxy (IAP) access.
    - Created rule `limit-ports` allowing SSH only from `35.235.240.0/20`.
- [x] **Enabled** Firewall Rule Logging for audit trails.

3️⃣ Data Protection (Cloud Storage)
- [x] **Revoked** `allUsers` (Public) access from the bucket.
- [x] **Enforced** Uniform Bucket-Level Access to prevent future ACL misconfigurations.

---

  📊 Results
* **Vulnerabilities Resolved:** 100% of High/Critical findings cleared in SCC.
* **Compliance:** Environment passed the **PCI DSS 3.2.1** audit report.
* **Attack Surface:** Drastically reduced by removing public IPs and closing open ports.

---

 📬 Connect with me
* **LinkedIn:** [https://linkedin.com/daniel-uzor]
