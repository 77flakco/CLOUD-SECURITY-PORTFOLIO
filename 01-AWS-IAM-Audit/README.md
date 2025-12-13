# Project: AWS Identity & Access Management (IAM) Audit

## 🛡️ Overview
This project focuses on the **Principle of Least Privilege**. I constructed a secure user hierarchy to replace the Root account for daily operations and validated permission boundaries.

## ⚙️ Architecture
- **Root User:** Secured with MFA (Hardware/Virtual).
- **Admin User:** Created for daily DevOps tasks (`AdministratorAccess`).
- **Audit User:** Restricted scope (`S3ReadOnlyAccess`) for testing.

## 🧪 Validation
I attempted to create an S3 bucket using the restricted `Audit-User`.
- **Expected Outcome:** Access Denied.
- **Actual Outcome:** AWS blocked the API call `s3:CreateBucket`.

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/c057c88d-94ed-4dc1-af42-f3a9ce307358" />


## 🔑 Key Skills
- AWS IAM Policies (JSON)
- Role-Based Access Control (RBAC)
- Root Account Hardening
