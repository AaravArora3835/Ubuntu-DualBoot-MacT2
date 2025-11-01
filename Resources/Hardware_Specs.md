# MacBook Pro Hardware Specifications

**Author:** Aarav Arora
**System:** MacBook Pro (13-inch, 2019, Four Thunderbolt 3 Ports)
**Last Updated:** October 31, 2025

---

## 1. System Overview

| Component            | Specification                                                  |
| -------------------- | -------------------------------------------------------------- |
| **Model Identifier** | MacBook Pro (13-inch, 2019, Four Thunderbolt 3 Ports)          |
| **Processor**        | 2.4 GHz Quad-Core Intel Core i5 (8th Generation)               |
| **Memory**           | 16 GB LPDDR3 2133 MHz                                          |
| **Graphics**         | Intel Iris Plus Graphics 655 (1536 MB)                         |
| **Chip**             | Apple T2 Security Chip                                         |
| **Storage**          | 512 GB SSD (130 GB available pre-installation)                 |
| **Operating System** | macOS Ventura 14.x                                             |
| **Ports**            | Four Thunderbolt 3 (USB-C)                                     |
| **Wi-Fi Adapter**    | Broadcom BCM4364 (requires `firmware-b43-installer` in Ubuntu) |

---

## 2. Firmware & BIOS Configuration

| Setting                 | Status                                        | Notes                                          |
| ----------------------- | --------------------------------------------- | ---------------------------------------------- |
| **Secure Boot**         | Disabled (“No Security”)                      | Required for non-Apple OS boot                 |
| **External Boot**       | Enabled (“Allow booting from external media”) | Enables boot from USB installer                |
| **Startup Manager Key** | Option (⌥)                                    | Access alternate boot drives                   |
| **Recovery Mode Key**   | Command (⌘) + R                               | Access macOS Recovery environment              |
| **Utility Used**        | Startup Security Utility                      | Adjusts Secure Boot and External Boot policies |

### Additional Security Adjustments

* **System Integrity Protection (SIP):** Temporarily disabled to allow `rEFInd` EFI bootloader installation.
* **Re-Enable Plan:** SIP and Secure Boot will be restored after Ubuntu installation for long-term system integrity.

---

## 3. Disk Configuration

| Item                         | Description                           |
| ---------------------------- | ------------------------------------- |
| **Drive Type**               | Apple NVMe SSD                        |
| **Total Capacity**           | 512 GB                                |
| **Available Space**          | 130 GB prior to installation          |
| **Partition Scheme**         | GUID Partition Map                    |
| **File System**              | APFS                                  |
| **Planned Ubuntu Partition** | 70 GB (allocated during installation) |

---

## 4. Compatibility Notes

* The **Apple T2 Security Chip** manages boot authentication, drive encryption, and Touch ID.
  These features require modification (via Recovery) to install third-party operating systems.
* **Wi-Fi, audio, and camera** on this model rely on Apple’s proprietary Broadcom firmware.
  Ubuntu will require additional driver installation (`firmware-b43-installer` for Wi-Fi).
* **All hardware components** were tested and confirmed functional under macOS before installation.
* Verified compatibility with **Ubuntu 24.04 LTS Desktop (64-bit AMD/Intel)**.

---

## 5. Summary

This hardware setup serves as a **dual-boot test environment** for Aarav Arora’s Cybersecurity Roadmap (2025–2026).
It enables side-by-side operation of macOS (primary) and Ubuntu Linux (secondary) for hands-on cybersecurity, networking, and system administration training.

All specifications and configurations are verified and documented for reproducibility, audit, and educational demonstration.

---

**Status:** Hardware verification and firmware configuration complete.
**Next Step:** Proceed with Ubuntu installation and partition setup.

**File Created:** October 30, 2025
**Last Updated:** October 31, 2025
**Purpose:** Baseline system reference for Ubuntu dual-boot configuration.
