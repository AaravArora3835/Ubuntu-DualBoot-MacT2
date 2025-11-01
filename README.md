# Ubuntu Dual Boot on Mac (T2 Secure Boot Friendly)

**Author:** Aarav Arora
**Start Date:** October 30 2025
**Hardware Tested:** MacBook Pro 13-inch (2019, Four Thunderbolt 3 Ports)
**Processor:** 2.4 GHz Quad-Core Intel Core i5 **Memory:** 16 GB LPDDR3 **Graphics:** Intel Iris Plus 655 (1536 MB)
**Security Chip:** Apple T2 (Secure Boot Enabled by Default)

---

## 1. Project Overview

This repository documents the complete installation and configuration of **Ubuntu 24.04 LTS** alongside **macOS Ventura** on a 2019 MacBook Pro equipped with Apple’s T2 Security Chip.
It transforms a consumer Mac into a **dual-operating-system cybersecurity lab**, capable of running penetration-testing, forensics, and systems-administration workloads natively.

This implementation forms part of **Aarav Arora’s Cybersecurity Roadmap (2025–2026)** — a multi-year academic and professional initiative aligning practical infrastructure setup with certification-level cybersecurity education.

---

## 2. Objectives

Design and document a **reproducible, secure, and auditable** dual-boot configuration that:

* Respects Apple’s T2 security architecture (Secure Boot + SIP)
* Enables Ubuntu 24.04 for hands-on cybersecurity and networking labs
* Demonstrates firmware-level system control, verification discipline, and risk management

---

## 3. Educational and Professional Relevance

| Skill Area                   | Demonstrated Competency                                          |
| ---------------------------- | ---------------------------------------------------------------- |
| **System Security**          | Managing firmware trust chains (Secure Boot + SIP)               |
| **Linux Administration**     | Installing and configuring Ubuntu on protected hardware          |
| **Dual Boot Architecture**   | Setting up EFI and GRUB boot environments                        |
| **Cybersecurity Readiness**  | Checksum validation, ISO verification, and secure media creation |
| **Documentation Discipline** | Maintaining audit-ready GitHub documentation and evidence        |

---

## 4. Background — The T2 Security Challenge

Apple’s T2 chip enforces secure boot validation, encryption, and signed-OS enforcement.
While these safeguards protect macOS, they restrict Linux installation unless firmware policies are modified.
To achieve a secure and controlled dual-boot configuration:

1. Entered macOS Recovery → disabled Secure Boot (“No Security”)
2. Enabled External Boot (“Allow booting from external media”)
3. Temporarily disabled System Integrity Protection (SIP) for EFI access
4. Installed `rEFInd` Boot Manager to manage macOS + Ubuntu boot entries

These steps mirror enterprise-level security operations — balancing protection with controlled flexibility.

---

## 5. Repository Structure

| Path                | Purpose                                                |
| ------------------- | ------------------------------------------------------ |
| `README.md`         | Main public guide (this file)                          |
| `Reflection.md`     | Daily logs and weekly insights                         |
| `/Resources/`       | Hardware specs, firmware logs, checksums, and toolkits |
| `/Troubleshooting/` | Detailed issue resolution and command logs             |
| `/Screenshots/`     | Timestamped visual evidence of each step               |

---

## 6. Preparation Phase (Completed Oct 30 – 31 2025)

**Major Accomplishments**

* Created and initialized public GitHub repository with v4.9 documentation rules
* Recorded full hardware and firmware specifications under `/Resources`
* Verified 130 GB available storage for Ubuntu partition (70 GB targeted)
* Downloaded Ubuntu 24.04.3 ISO, balenaEtcher, and rEFInd
* Validated files via SHA-256 checksums and macOS signature verification
* Disabled Secure Boot and enabled External Boot in Recovery Utility
* Temporarily disabled SIP (System Integrity Protection) for EFI modifications
* Created bootable USB (16 GB Dynon Metrics, USB-C/USB-A) using balenaEtcher
* Installed `rEFInd` Boot Manager successfully after SIP adjustment
* Confirmed **EFI Boot** menu option appears on startup
* Archived all screenshots and logs in version control

---

## 7. Firmware and Verification Summary

| Component        | Status                 | Verification Method        |
| ---------------- | ---------------------- | -------------------------- |
| Ubuntu ISO       | ✅ Verified             | SHA-256 Checksum           |
| balenaEtcher DMG | ✅ Verified             | macOS Gatekeeper Signature |
| rEFInd ZIP       | ✅ Verified             | Manual SHA-256 Validation  |
| Secure Boot      | ✅ Disabled             | Startup Security Utility   |
| SIP              | ✅ Disabled (Temporary) | `csrutil status`           |
| External Boot    | ✅ Enabled              | Recovery Settings          |

---

## 8. Troubleshooting Highlights (Oct 31 2025)

| Issue                     | Root Cause              | Resolution                                    |
| ------------------------- | ----------------------- | --------------------------------------------- |
| SIP Blocking rEFInd       | EFI write protection    | Disabled SIP via Recovery (`csrutil disable`) |
| Secure Boot Prevented USB | T2 firmware policy      | Set to *No Security* + allowed external boot  |
| USB Not Detected          | Incorrect partition map | Reformatted as FAT + GUID, re-flashed ISO     |

Detailed logs and commands are available in `/Troubleshooting/`.

---

## 9. Tools and Resources

*(See `/Resources/Toolkit_Downloads.md` for sources and versions.)*

| Tool                 | Version     | Purpose                           |
| -------------------- | ----------- | --------------------------------- |
| Ubuntu 24.04.3 LTS   | Desktop ISO | Target Linux OS                   |
| balenaEtcher         | 2.1.4       | Create bootable USB media         |
| rEFInd Boot Manager  | 0.14.0.2    | Dual-boot management              |
| Disk Utility         | Built-in    | Drive formatting and partitioning |
| Terminal / `csrutil` | Built-in    | Firmware and SIP configuration    |
| Time Machine         | Built-in    | System backup before partitioning |

---

## 10. Commands and Procedures

**List Drives**

```
diskutil list
```

**Disable SIP (in Recovery)**

```
csrutil disable
```

**Post-Install Linux Setup**

```
sudo apt update && sudo apt upgrade -y
sudo apt install firmware-b43-installer tlp -y
```

---

## 11. Documentation Evidence

| Filename                             | Description                        |
| ------------------------------------ | ---------------------------------- |
| 2025-10-30_SecureBoot_Settings.jpg   | Firmware configuration in Recovery |
| 2025-10-30_DiskUtility_Layout.jpg    | Pre-partition disk layout          |
| 2025-10-31_Disable_SIP_Recovery.jpg  | SIP disable command executed       |
| 2025-10-31_SIP_Status_Disabled.jpg   | Confirmation of SIP disabled       |
| 2025-10-31_Etcher_Flash_Complete.jpg | USB flashing completed             |
| 2025-10-31_EFI_Boot_Menu.jpg         | EFI boot entry verified            |

---

## 12. Educational Takeaways

* Learned to navigate T2 firmware and SIP restrictions safely.
* Applied checksum verification and cryptographic validation standards.
* Balanced security controls with engineering flexibility.
* Practiced incident-style documentation with full audit trail.
* Built a reproducible process for future cybersecurity labs and projects.

---

## 13. Next Phases

| Date           | Focus                | Expected Outcome                                |
| -------------- | -------------------- | ----------------------------------------------- |
| Nov 1 2025     | Ubuntu Installation  | Partition SSD and install OS                    |
| Nov 2 2025     | Dual-Boot Validation | Test boot flow and drivers                      |
| Nov 3 – 9 2025 | Post-Install Labs    | Integrate into Google Cybersecurity Certificate |

---

**Status:** ✅ Pre-installation and troubleshooting complete
**Next Phase:** Ubuntu installation and system partitioning on Nov 1 2025
