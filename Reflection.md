## Day 1 — October 30 2025

**Phase:** Pre-Installation Setup
**Goal:** Prepare system, verify firmware settings, and download all required installation tools.

---

### Overview

The first session focused entirely on pre-installation readiness.
I set up the Ubuntu-DualBoot-MacT2 repository, documented hardware specifications, verified Secure Boot status, and confirmed that the MacBook was ready for a Linux install under Apple’s T2 security architecture.

---

### Tasks Completed

* Created and initialized the GitHub repository with proper folder structure.
* Added hardware specs and firmware notes to `/Resources`.
* Checked available storage (130 GB free on 512 GB SSD).
* Set Secure Boot to “No Security” and enabled External Boot.
* Downloaded and stored Ubuntu ISO, balenaEtcher, and rEFInd ZIP.
* Verified Ubuntu ISO checksum against official SHA-256 value.
* Logged every action and screenshot with timestamps.

---

### Key Takeaways

* The T2 chip requires firmware permission adjustments before Linux can boot.
* Systematic logging is essential for transparency and reproducibility.
* Preparing resources and backups up front minimizes installation risk.

---

### Challenges

No technical errors occurred; progress was limited only by the pending arrival of the USB drive for flashing.

---

### End-of-Day Summary

All firmware checks and verifications complete.
System is fully prepared for media creation and installation on Day 2.

**Status:** ✅ Preparation complete – awaiting USB drive.

---

## Day 2 — October 31 2025

**Phase:** Firmware and Verification Troubleshooting
**Goal:** Resolve security restrictions and prepare verified Ubuntu USB installer.

---

### Overview

Day 2 was devoted to overcoming macOS security barriers.
I encountered multiple firmware-level protections (SIP, Secure Boot, external boot restrictions) but resolved each through controlled configuration and command-line management.
By the end of the session, the MacBook was EFI-boot-ready for Ubuntu.

---

### Tasks Completed

* Disabled **System Integrity Protection (SIP)** via Recovery Terminal.
* Installed `rEFInd` Boot Manager after verifying EFI write permissions.
* Reformatted USB to **FAT32 + GUID Partition Map** and re-flashed ISO using balenaEtcher.
* Validated Etcher flash success and checksums.
* Confirmed appearance of EFI Boot option in Startup Manager.
* Updated `/Resources/Checksums_And_Verification.md` and `/Troubleshooting/` logs.
* Captured six screenshots documenting each firmware change and validation step.

---

### Challenges and Resolutions

| Challenge                         | Diagnosis                           | Solution                                                    |
| --------------------------------- | ----------------------------------- | ----------------------------------------------------------- |
| SIP prevented rEFInd installation | Terminal denied EFI writes          | Booted Recovery → `csrutil disable` → re-install successful |
| USB not recognized                | Formatted APFS by mistake           | Erased and reformatted to FAT32 + GUID                      |
| No EFI Boot option visible        | Secure Boot blocking unsigned media | Changed to “No Security” + “Allow External Boot”            |

---

### Key Takeaways

* The T2 chip represents a real-world security ecosystem requiring firmware-level understanding.
* The Recovery Terminal (`csrutil`) is a powerful administrative tool that must be used carefully.
* Systematic testing, evidence collection, and rollback options mirror professional incident response practices.

---

### Reflection

This day felt like real security operations work — identifying and safely overriding trusted boot barriers to achieve a controlled objective.
Documenting each error, command, and screenshot transformed a simple install into an audit-ready case study on Apple firmware management.
I gained a deeper respect for Apple’s security architecture and how it balances user freedom with system integrity.

---

### End-of-Day Summary

All firmware and USB issues resolved.
Dual-boot environment ready for Ubuntu installation on November 1 2025.
Repository and evidence logs fully updated.

**Status:** ✅ Pre-installation and troubleshooting complete.
**Next Goal:** Ubuntu installation and post-install driver configuration.
