# Ubuntu Dual Boot on Mac (T2 Secure Boot Friendly)

**Author:** Aarav Arora
**Start Date:** October 30, 2025
**Hardware Tested:** MacBook Pro 13-inch (2019, Four Thunderbolt 3 Ports)
**Processor:** 2.4 GHz Quad-Core Intel Core i5
**Memory:** 16 GB LPDDR3
**Graphics:** Intel Iris Plus 655 (1536 MB)

---

## 1. Purpose

This repository documents the complete process of installing **Ubuntu 24.04 LTS** alongside **macOS** on a 2019 MacBook Pro with Apple’s T2 security chip.
It serves as a practical systems-level guide for students and cybersecurity learners who want to build a reliable dual-boot lab environment on Mac hardware.

All steps, screenshots, and reflections will be updated progressively as the installation proceeds.

---

## 2. Background

The 2019 MacBook Pro uses the Apple T2 chip, which enforces secure boot and external boot protection.
Installing Linux on this hardware requires changing firmware settings, partitioning the APFS drive, and applying Broadcom drivers for Wi-Fi functionality.
This project is part of **Aarav Arora’s Cybersecurity Roadmap (2025-2026)** and is aligned with the **Google Cybersecurity Professional Certificate** hands-on environment setup phase.

---

## 3. Current Phase: Pre-Installation (Thursday, October 30, 2025)

The current phase focuses on preparing the system and repository before flashing the Ubuntu installer.
By the end of this phase:

* The repository structure should be initialized.
* All required software and ISO files should be downloaded.
* Secure Boot should be disabled, and external booting should be allowed.
* A Time Machine backup should be verified.

---

## 4. Repository Structure

| Path                | Description                                                |
| ------------------- | ---------------------------------------------------------- |
| `README.md`         | Main public guide and documentation of each stage          |
| `Reflection.md`     | Weekly reflections and post-installation analysis          |
| `/Screenshots/`     | Dated screenshots and setup photos                         |
| `/Resources/`       | Hardware specifications, ISO metadata, configuration files |
| `/Troubleshooting/` | Logs and solutions to common setup issues                  |

---

## 5. Preparation Summary (Completed 10/30/2025)

**Tasks Done:**

1. Installed Git and created public GitHub repository.
2. Cloned repo locally and built folder structure.
3. Recorded Mac hardware details and verified storage space.
4. Downloaded Ubuntu 24.04 LTS ISO, balenaEtcher, and rEFInd.
5. Checked Secure Boot and external boot permissions in Recovery Mode.
6. Verified Time Machine backup before partitioning.

---

## 6. Next Steps (Friday, October 31, 2025)

1. Use **balenaEtcher** to flash the Ubuntu ISO to the 16 GB Dynon Metrics USB-C drive.
2. Partition the internal SSD for dual-booting (60–80 GB for Ubuntu).
3. Install or verify the rEFInd boot manager.
4. Boot from USB and begin Ubuntu installation.
5. Capture all screenshots for each phase and add them to `/Screenshots/`.

---

## 7. Planned Commands and Tools

**System Preparation:**

```bash
diskutil list
```

*(Used to identify the internal SSD before partitioning.)*

**Linux Installation Verification (after Ubuntu install):**

```bash
sudo apt update && sudo apt upgrade -y
sudo apt install firmware-b43-installer tlp -y
```

---

## 8. Attribution

All instructions are written and tested by **Aarav Arora** as part of a multi-year cybersecurity roadmap focused on system administration, OS security, and lab configuration.
Future updates will include detailed troubleshooting steps and reflections once Ubuntu installation and GRUB configuration are complete.

---

**Status:** Preparation phase complete – ready for USB flashing and partitioning.
**Next Update:** Friday, October 31, 2025 – ISO flashing and disk partition guide.
