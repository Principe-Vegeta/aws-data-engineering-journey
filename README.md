# 🚀 AWS Data Engineering & Cloud Security Journey

Welcome to my portfolio! This repository serves as the central hub for my preparation for the **AWS Certified Data Engineer - Associate (DEA-C01)** certification. Here, I document all my hands-on labs, architectural deployments, and security hardening procedures.

---

## 🔐 Lab 1: Foundational Cloud Infrastructure & Post-Quantum SSH Hardening

### 📋 Overview
In this foundational lab, I deployed a secure Linux instance on Amazon EC2, configured strict network access controls via Security Groups, performed network port auditing using Netcat, and hardened the remote access channel against future threats using **Post-Quantum Cryptography (PQC)**.

### 🏗️ Architecture Diagram
![AWS Cloud Infrastructure & CyberSecurity](arquitetura.png)

---

### 🛠️ Step-by-Step Implementation

#### Step 1: Secure EC2 Deployment & IAM Check
* Deployed an **Amazon Linux 2023** instance on AWS EC2.
* Configured an IAM-vetted Key Pair (`.pem`) for secure authentication.
* Restrained network access by applying the principle of least privilege on the AWS Security Group, allowing SSH traffic (Port 22) strictly from my administrator IP (`/32` mask).

#### Step 2: Service Management & Network Auditing
* Connected via SSH from my local Kali Linux environment.
* Installed and managed core system services using `systemd` (`systemctl`).
* Utilized **Netcat (`nc -zv`)** to perform proactive network troubleshooting, successfully mapping out `Connection refused` states to isolate and fix service downtimes.
* Configured service persistence using `systemctl enable` to guarantee high availability after system reboots.

#### Step 3: Post-Quantum Cryptography (PQC) Hardening
* Addressed the modern cryptographic threat known as **"Store Now, Decrypt Later"** (where adversaries intercept encrypted traffic today to decrypt it in the future using quantum computers).
* Upgraded the OpenSSH packages on both the client (Kali Linux) and the server (AWS EC2).
* Enforced the use of hybrid quantum-resistant key exchange algorithms (`mlkem768x25519-sha256`), eliminating standard handshake warnings and ensuring next-generation session defense.

---

### 🧠 Skills Validated
* **Cloud Infrastructure:** AWS EC2, Security Groups, Network Isolation (`/32` masking).
* **Linux Administration:** Systemd initialization, Package Management (`dnf`/`apt`), Session Logging.
* **Network Security:** Port scanning and diagnostics with Netcat (`nc`), OpenSSH tuning, Post-Quantum Cryptography (PQC).

---

## 📈 Next Phase: Data Engineering Core
With the secure infrastructure foundation established, the next module will cover **Data Ingestion and Storage**, focusing on:
* **Amazon S3** Data Lakes design and partitioning.
* **AWS IAM** fine-grained policies for data access.
* **Amazon Kinesis** real-time data streaming ingestion.

*Course followed: AWS Certified Data Engineer Associate 2026 by Stephane Maarek & Frank Kane.*
