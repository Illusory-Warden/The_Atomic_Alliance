# Pi-Vate Cloud: A Self-Sovereign, Cost-Effective Personal Cloud on Raspberry Pi

## Overview

Pi-Vate Cloud is a self-hosted, privacy-preserving, cost-effective personal cloud ecosystem built using the Raspberry Pi and a suite of open-source technologies. It offers an alternative to commercial cloud platforms by providing users with full ownership, security, and control over their digital data while enabling remote access, file synchronization, and media streaming.

This project was developed as part of the Minor Project / Research Work presented at the 4th International Conference on Innovations in Data Analytics (ICIDA 2025). It integrates **OpenMediaVault (OMV)** for NAS services, **Docker** for modular deployment, **Plex Media Server** for media streaming, and **Twingate Zero-Trust Network Access (ZTNA)** for secure remote accessibility.

---

## Table of Contents

1. Introduction
2. Problem Statement
3. Objectives
4. Novelty of the Work
5. System Architecture
6. Hardware & Software Requirements
7. Methodology
8. Key Features
9. Performance Evaluation
10. Security Architecture
11. Cost Analysis
12. Results
13. Limitations
14. Future Improvements
15. Conclusion
16. Authors

---

## 1. Introduction

The rapid growth of personal digital data—including photos, videos, academic records, and media libraries—has made cloud storage essential. Commercial platforms such as Google Drive, iCloud, OneDrive, and Dropbox offer convenience, but they also introduce:

* Recurring subscription fees
* Privacy risks and corporate data mining
* Vendor lock-in
* Limited transparency and data sovereignty

Personal cloud storage provides a viable alternative by enabling users to privately host and manage their own cloud system using accessible hardware such as the Raspberry Pi.

Pi-Vate Cloud addresses these challenges by delivering a **low-cost**, **self-sovereign**, and **secure** cloud ecosystem designed for household-scale workloads.

---

## 2. Problem Statement

Users today face several challenges with commercial cloud storage:

* **Recurring Costs:** Paid plans accumulate significantly over time.
* **Privacy Concerns:** Sensitive data stored on third-party servers increases exposure to breaches and misuse.
* **Data Ownership Issues:** Cloud providers retain control over how and where user data is stored.
* **Vendor Lock-In:** Migration of large datasets is time-consuming and complicated.
* **Limited Remote Access on Local Devices:** Traditional personal storage lacks accessible remote connectivity.

Pi-Vate Cloud aims to eliminate these constraints by enabling a fully self-hosted, secure, user-controlled cloud platform.

---

## 3. Objectives

### Primary Objective

Develop a fully operational, user-friendly, cost-effective personal cloud solution that returns full data ownership to users.

### Specific Objectives

* Build a Raspberry Pi–based cloud storage system.
* Integrate file sharing, syncing, and media streaming.
* Enable secure remote access using Zero-Trust technologies (Twingate).
* Implement advanced security practices such as LUKS encryption, SSH key-only authentication, UFW, and fail2ban.
* Evaluate performance using real-world datasets.
* Deliver documentation for easy deployment by non-technical users.
* Compare Total Cost of Ownership (TCO) with commercial cloud services.

---

## 4. Novelty of the Work

* A complete, **self-sovereign personal cloud platform** built entirely using low-cost hardware.
* Eliminates all recurring subscription fees.
* Fully secure remote access using **ZTNA (Twingate)** instead of risky port forwarding or VPNs.
* Combines OMV + Docker + Plex to deliver a unified media and data ecosystem.
* Designed for **non-technical users** with simplified installation and modularity.

---

## 5. System Architecture

Pi-Vate Cloud integrates multiple components to form a complete personal cloud ecosystem:

### Core Components

* **OpenMediaVault (OMV):** NAS management for SMB/CIFS, SFTP, user permissions.
* **Docker Containerization:** Plex, monitoring tools, backup services.
* **Plex Media Server:** Organizes and streams personal media collections.
* **Twingate Zero-Trust Network Access:** Secure, port-less remote access.
* **UFW + fail2ban:** Protects against unauthorized access attempts.

### Twingate Architecture (Simplified)

* **Connector (Raspberry Pi):** Exposes local services securely.
* **Relay (Cloud):** Handles encrypted fallback connections.
* **Controller (Cloud):** Manages access policies and authentication.
* **Client (Devices):** Access OMV/Plex securely.

---

## 6. Hardware & Software Requirements

### Hardware

* **Raspberry Pi 4 Model B (1 GB RAM)**
* **32 GB Samsung microSD card** (Operating System)
* **1 TB Seagate Barracuda HDD** via USB 3.0 enclosure
* **USB 3.0–to–SATA enclosure** with UASP support
* **5V / 3A official Raspberry Pi power supply**
* **Ethernet connection** (preferred for performance)

### Software

* **Raspberry Pi OS Lite (64-bit)**
* **OpenMediaVault (OMV)**
* **Docker & Docker Compose**
* **Plex Media Server** (Docker)
* **Twingate Starter Plan** (free up to 5 users)
* **Security Tools:** UFW, fail2ban, SSH key-only access

---

## 7. Methodology

1. Install Raspberry Pi OS Lite.
2. Install OMV using official scripts.
3. Configure storage drives and SMB shares.
4. Install Docker and deploy Plex + auxiliary services.
5. Set up Twingate Connector for secure remote access.
6. Harden the system with UFW, fail2ban, SSH keys, and updates.
7. Test upload, sync, and streaming performance.
8. Conduct cost and performance comparisons.

A detailed workflow diagram was provided in the project documentation.

---

## 8. Key Features

### Storage & File Management

* NAS with SMB/CIFS support
* Multi-user access & permission control
* Docker-based extensions

### Media Features

* Plex media streaming over LAN & remote
* Optimized for Direct Play (no transcoding load)

### Security Features

* Zero-Trust remote access (ZTNA)
* SSH key-only authentication
* TLS encryption via Let’s Encrypt
* UFW firewall rules
* Intrusion detection with fail2ban
* Optional LUKS disk encryption

### Usability

* Simple Web UI (OMV)
* Modular Docker deployment
* Works across Windows, Linux, macOS, iOS, Android

---

## 9. Performance Evaluation

Testing was conducted using:

* Airtel 100 Mbps Internet Plan
* Local Gigabit LAN

### Observed Results

* Upload of 10 images (~120 MB): **45–60 seconds**
* Upload of 3.33 GB video: **25–30 minutes**
* Smooth **1080p streaming** via Plex on LAN
* Remote performance limited by ISP uplink speed

These values confirm that Raspberry Pi 4 is sufficient for household-scale cloud workloads.

---

## 10. Security Architecture

Pi-Vate Cloud integrates multi-layered defenses:

* **Data at Rest:** LUKS encryption (optional)
* **Data in Transit:** TLS (Twingate)
* **Access Control:** 2FA, SSH key-only login
* **Network Security:** UFW firewall + fail2ban
* **Zero Attack Surface:** No exposed public ports

ZTNA ensures only authenticated devices can reach services, vastly reducing attack exposure.

---

## 11. Cost Analysis

Commercial cloud storage (Google One, Dropbox, iCloud) involves recurring fees.

### Example Comparison (3–5 Year Period)

* Typical 1 TB plan costs **₹7,000–₹12,000 per year**.
* Over 5 years: **₹35,000–₹60,000**.

### Pi-Vate Cloud Cost

* Raspberry Pi + HDD + accessories ≈ **₹6,000–₹8,000** (one-time).
* No subscription fees.

**Overall Savings:** ~70% reduction in TCO.

---

## 12. Results

* Successfully deployed a complete personal cloud on Raspberry Pi.
* Achieved reliable file synchronization, media streaming, and remote access.
* Delivered measurable performance metrics for real-world workloads.
* Demonstrated major economic advantages vs. commercial cloud platforms.

---

## 13. Limitations

* Raspberry Pi cannot perform heavy Plex transcoding.
* Single-disk configuration has no redundancy (RAID not implemented).
* Remote access performance depends on ISP bandwidth.
* Requires basic technical knowledge for initial setup.

---

## 14. Future Improvements

* Add RAID or multi-disk storage for better reliability.
* Implement automated backup + restore verification.
* Add IDS/IPS and advanced security scanning.
* Integrate monitoring dashboards (Grafana, Prometheus).
* Develop a full web-based management UI.

---

## 15. Conclusion

Pi-Vate Cloud proves that a low-cost Raspberry Pi can replace expensive commercial cloud storage for personal and household use. It offers:

* Full data ownership
* Strong security architecture
* Cost savings
* Media and storage flexibility
* Remote accessibility via modern Zero-Trust principles

The project highlights the feasibility and value of self-sovereign personal cloud ecosystems for secure, sustainable digital data management.

---

## 16. Authors

* **Rushi Daulatkar**
* **Atharva Dhote**
* **Abhijeet Pathode**
* **Harsh Yadav**
* **Guide:** Prof. Renuka Raut

St. Vincent Pallotti College of Engineering & Technology
Department of Computer Science and Business Systems

---

**End of README.md**
