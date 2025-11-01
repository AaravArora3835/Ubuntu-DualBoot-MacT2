# Toolkit and Downloads — Ubuntu Dual-Boot Setup

**Author:** Aarav Arora
**Verification Date:** October 31, 2025
**Location:** `~/Downloads/UbuntuSetup/`

---

## 1. Core Installation Files

| File                               | Source                                                                      | Purpose                                                         |
| ---------------------------------- | --------------------------------------------------------------------------- | --------------------------------------------------------------- |
| `ubuntu-24.04.3-desktop-amd64.iso` | [ubuntu.com/download/desktop](https://ubuntu.com/download/desktop)          | Primary Ubuntu 24.04 LTS installer ISO (64-bit Intel/AMD)       |
| `balenaEtcher-2.1.4-x64.dmg`       | [etcher.balena.io](https://etcher.balena.io)                                | Utility to flash the Ubuntu ISO onto a USB drive                |
| `refind-bin-0.14.0.2.zip`          | [sourceforge.net/projects/refind](https://sourceforge.net/projects/refind/) | Boot manager enabling macOS + Ubuntu coexistence                |
| `Time Machine Backup`              | Built-in macOS Utility                                                      | Full system backup for rollback or recovery before partitioning |

---

## 2. Verification & Storage Details

* All files were downloaded via official vendor websites over HTTPS.
* ISO and ZIP packages were validated via **SHA-256 checksums** (see `Checksums_And_Verification.md`).
* macOS DMG packages (balenaEtcher) were verified through **Apple Gatekeeper** signature validation.
* Files stored under `~/Downloads/UbuntuSetup/` before flashing to USB media.

---

## 3. Recommended Utilities (Pre-Installed on macOS)

| Tool                 | Function                                      | Notes                                                |
| -------------------- | --------------------------------------------- | ---------------------------------------------------- |
| `shasum`             | Validate ISO checksums                        | Used to compare cryptographic hashes                 |
| `diskutil`           | List and format connected drives              | Used to identify USB device before flashing          |
| `Terminal`           | Execute system commands and EFI installations | Primary interface for verification and rEFInd setup  |
| `Screenshot Utility` | Capture progress and firmware settings        | Used for reproducibility and portfolio documentation |

---

## 4. Additional Notes

* The selected USB drive for flashing was a **16 GB Dynon Metrics dual USB-C/USB 3.0 flash drive**, water-resistant alloy casing.
* Minimum capacity required: **8 GB**, though 16 GB recommended for stable write performance.
* Verified successful flash completion via BalenaEtcher on **October 31, 2025**.

---

**Status:** All toolkit components verified and successfully used for ISO flashing and bootloader setup.
**Next Step:** Use USB to initiate Ubuntu installer and begin partition configuration.
