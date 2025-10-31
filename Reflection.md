# Reflection Log — Ubuntu Dual Boot on Mac (T2 Secure Boot Friendly)

## Day 1 — October 30, 2025
**Phase:** Pre-Installation Setup  
**Goal:** Prepare system, verify firmware settings, and download all required tools before flashing the Ubuntu USB installer.

---

### Overview
The first day focused entirely on preparation. I created and configured the `Ubuntu-DualBoot-MacT2` repository, documented my hardware, verified Secure Boot settings, and ensured the MacBook was ready to install Ubuntu safely. This step was critical for T2-chip Macs, which restrict external booting by default.

---

### Tasks Completed
1. Created GitHub repository and set up folder structure (`Screenshots`, `Resources`, `Troubleshooting`).
2. Added README, Reflection, and hardware documentation file.
3. Verified Secure Boot configuration:
   - Set Secure Boot to **No Security**
   - Allowed booting from external media
   - Captured screenshot evidence (`2025-10-30_SecureBoot_Settings.jpg`)
4. Checked available disk space (130 GB free on 512 GB SSD) — sufficient for a 70 GB Ubuntu partition.
5. Downloaded required tools:
   - `ubuntu-24.04.3-desktop-amd64.iso`
   - `balenaEtcher-2.1.4-x64.dmg`
   - `refind-bin-0.14.0.2.zip`
6. Verified ISO integrity using SHA-256 checksum.
7. Wrote all documentation and pushed commits to GitHub.

---

### Key Takeaways
- Apple’s T2 security chip requires specific firmware changes before Linux can boot.
- Verifying disk space early prevents partitioning errors later.
- Keeping documentation in a structured GitHub repo makes the process reproducible.

---

### Challenges
- None major. The only delay is waiting for the USB drive to arrive before creating the bootable installer.

---

### Pending Tasks
1. Format and flash the USB installer once the 16 GB USB-C drive arrives.
2. Install rEFInd boot manager.
3. Partition the SSD and install Ubuntu 24.04 LTS.

---

### End-of-Day Summary
All pre-installation requirements have been completed.  
The system is backed up, the firmware is configured correctly, and all tools are prepared.  
Next session (October 31) will focus on flashing the ISO and beginning the installation.

**Status:** Preparation complete – awaiting USB drive for installation.
