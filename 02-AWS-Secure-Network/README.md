# Project: Secure Network Architecture (The Invisible Server)

## 🛡️ Overview
This project implements **Network Whitelisting** to secure cloud compute resources. Unlike default settings which often allow `0.0.0.0/0` (Anywhere), this architecture is invisible to internet scanners.

## ⚙️ Configuration
- **Resource:** AWS EC2 (Amazon Linux).
- **Firewall:** AWS Security Group configured with strict ingress rules.
- **Authentication:** 2048-bit RSA Key Pair (No password login).

## 🧪 Validation
- **Authorized Access:** Verified SSH connection from my static Home IP.
- **Unauthorized Access:** Attempted connection from external mobile network.
- **Result:** Packets were silently dropped by the firewall (Connection Timed Out).

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/41a36926-a0c3-42f6-9c3d-259ed4708463" />


## 🔑 Key Skills
- VPC & Subnet Security
- Security Group Configuration
- SSH Key Management
