# Ubuntu Dual Boot on Mac (T2 Secure Boot Friendly)

**Author:** Aarav Arora
**Start Date:** October 30, 2025
**Hardware Tested:** MacBook Pro 13-inch (2019, Four Thunderbolt 3 Ports)
**Processor:** 2.4 GHz Quad-Core Intel Core i5
**Memory:** 16 GB LPDDR3
**Graphics:** Intel Iris Plus 655 (1536 MB)
**Security Chip:** Apple T2 (Secure Boot Enabled by Default)

---

## 1. Project Overview

This project documents the **secure installation and configuration of Ubuntu 24.04 LTS alongside macOS Ventura** on Apple’s 2019 MacBook Pro (T2 chip).
It transforms a macOS laptop into a **dual-operating-system cybersecurity lab** — capable of running penetration testing, forensics, and system administration workloads natively.

This work was conducted as part of **Aarav Arora’s Cybersecurity Roadmap (2025–2026)** — an academic and professional initiative designed to integrate real-world infrastructure setup with cybersecurity certification studies.

---

## 2. Objective

To design and document a **T2-secure, reproducible dual-boot configuration** that:

* Complies with Apple’s security architecture (T2, SIP, and Secure Boot)
* Enables Ubuntu 24.04 for hands-on cybersecurity labs
* Demonstrates systems-level competency, verification discipline, and risk awareness

---

## 3. Educational & Professional Relevance

| Skill Area                   | Demonstrated Competency                                                     |
| ---------------------------- | --------------------------------------------------------------------------- |
| **System Security**          | Managing firmware trust chains (Secure Boot, SIP)                           |
| **Linux Administration**     | Installing and configuring Ubuntu on protected hardware                     |
| **Dual Boot Architecture**   | Configuring EFI/GRUB and multi-OS bootloaders                               |
| **Cybersecurity Readiness**  | Verifying checksums, validating ISO integrity, controlling boot permissions |
| **Documentation Discipline** | Structured GitHub-based lab documentation for audit and reproducibility     |

This guide reflects both **technical capability** and **professional documentation standards** — the same skillset used in security engineering, IT infrastructure, and DevOps roles.

---

## 4. Background: The Challenge of T2 Security

Apple’s **T2 chip** secures the boot process using firmware validation, disk encryption, and signed OS verification.
While this protects macOS, it prevents unverified operating systems from booting unless the user manually adjusts the firmware.

Installing Linux on a T2-based system therefore requires:

1. Entering macOS Recovery and changing **Startup Security Utility** settings
2. **Disabling Secure Boot** and allowing external boot media
3. **Temporarily disabling SIP (System Integrity Protection)** to allow EFI modifications
4. Using **rEFInd Boot Manager** to manage the boot process securely

This configuration mimics the level of precision used in enterprise-level system hardening and multi-environment testing.

---

## 5. Repository Overview

| Path                | Purpose                                                            |
| ------------------- | ------------------------------------------------------------------ |
| `/README.md`        | Main public-facing guide (this file)                               |
| `/Reflection.md`    | Day-by-day progress, troubleshooting notes, and insights           |
| `/Resources/`       | Hardware specs, firmware logs, checksum verification, and toolkits |
| `/Screenshots/`     | Dated screenshots documenting each technical step                  |
| `/Troubleshooting/` | Resolutions for installation or driver issues                      |

Each directory represents a **phase in the technical lifecycle** — ensuring complete traceability from preparation → installation → validation.

---

## 6. Preparation Phase (Completed Oct 30–31, 2025)

### ✅ Accomplishments

1. Initialized public GitHub repository and version-controlled documentation.
2. Verified 130 GB available storage for dual-boot partition.
3. Collected and recorded all system hardware and firmware specifications.
4. Downloaded and verified Ubuntu 24.04.3 ISO, balenaEtcher, and rEFInd using SHA-256 checksums.
5. Disabled **Secure Boot** and enabled **External Boot** in macOS Recovery.
6. Temporarily disabled **System Integrity Protection (SIP)** to permit EFI bootloader installation.
7. Created bootable Ubuntu installer using a 16 GB USB-C drive (Dynon Metrics).
8. Installed **rEFInd Boot Manager** successfully after resolving SIP restrictions.
9. Verified appearance of **EFI Boot** menu entry on system startup.
10. Captured and archived all screenshots under `/Screenshots/`.

---

## 7. Firmware & Verification Summary

| Component        | Status                 | Verification Method            |
| ---------------- | ---------------------- | ------------------------------ |
| Ubuntu ISO       | ✅ Verified             | SHA-256 Checksum               |
| balenaEtcher DMG | ✅ Verified             | macOS Gatekeeper Signature     |
| rEFInd ZIP       | ✅ Verified             | Manual SHA-256 Validation      |
| Secure Boot      | ✅ Disabled             | macOS Recovery Startup Utility |
| SIP              | ✅ Disabled (temporary) | Terminal `csrutil status`      |
| External Boot    | ✅ Allowed              | macOS Recovery Settings        |

---

## 8. Tools and Resources

| Tool                               | Version     | Purpose                                   |
| ---------------------------------- | ----------- | ----------------------------------------- |
| **Ubuntu 24.04.3 LTS**             | Desktop ISO | Target Linux OS                           |
| **balenaEtcher (2.1.4)**           | macOS App   | Bootable USB flashing                     |
| **rEFInd Boot Manager (0.14.0.2)** | ZIP         | Dual-boot management                      |
| **Disk Utility**                   | Built-in    | Drive formatting and GUID partition setup |
| **Terminal / csrutil**             | Built-in    | SIP and security configuration            |
| **Time Machine**                   | Built-in    | Full macOS system backup prior to install |

All tools were downloaded from **official vendor sources** and verified using cryptographic hashes or system signatures.

---

## 9. Verified Commands and Procedures

### System Information

```
diskutil list
```

Lists all partitions and helps identify the target SSD volume before partitioning.

### Disable SIP (System Integrity Protection)

```
csrutil disable
```

Executed in macOS Recovery → Terminal. Required for rEFInd EFI installation.

### Post-Installation (to be executed in Ubuntu)

```
sudo apt update && sudo apt upgrade -y
sudo apt install firmware-b43-installer tlp -y
```

Installs Broadcom wireless drivers and power optimization tools.

---

## 10. Documentation Evidence

All screenshots are stored under `/Screenshots/` with full-date naming:

| Filename                               | Description                           |
| -------------------------------------- | ------------------------------------- |
| `2025-10-30_SecureBoot_Settings.jpg`   | Secure Boot configuration in Recovery |
| `2025-10-30_DiskUtility_Layout.jpg`    | Drive layout before partitioning      |
| `2025-10-31_Disable_SIP_Recovery.jpg`  | Terminal showing SIP disable command  |
| `2025-10-31_SIP_Status_Disabled.jpg`   | Confirmation of SIP disabled          |
| `2025-10-31_Etcher_Flash_Complete.jpg` | Completed USB creation in Etcher      |
| `2025-10-31_EFI_Boot_Menu.jpg`         | Proof of EFI Boot entry on startup    |

---

## 11. Educational Takeaways

This setup was performed manually and documented to simulate real-world technical workflows:

* Balancing **system security** with **engineering flexibility**
* Applying **forensics-grade verification** (checksums, logs, and evidence)
* Understanding **firmware-level risk control** in mixed-OS environments
* Demonstrating **critical troubleshooting** (resolving SIP, EFI, and boot issues)
* Building **long-term lab infrastructure** for cybersecurity learning

---

## 12. Future Phases

| Date              | Focus                | Outcome                                                     |
| ----------------- | -------------------- | ----------------------------------------------------------- |
| **Nov 1, 2025**   | Ubuntu Installation  | Partition drive and install OS                              |
| **Nov 2, 2025**   | Dual-Boot Validation | Test bootloader and Wi-Fi functionality                     |
| **Nov 3–9, 2025** | Post-Install Labs    | Integrate into Google Cybersecurity Certificate environment |

Upon completion, the system will serve as a **dedicated Linux workspace** for ethical hacking, networking, and cloud security labs — complementing coursework and certification milestones.

---

## 13. Credits and Authorship

All research, testing, and documentation were conducted by **Aarav Arora**, Los Angeles, CA.
This project represents both a **technical demonstration** and a **professional development artifact** for college and internship applications.
Every section was written to highlight applied cybersecurity skills, technical literacy, and systems-level problem-solving.

---

**Status:** ✅ Pre-installation phase complete
**Next Phase:** Ubuntu Installation and System Partitioning (Saturday, November 1, 2025)
