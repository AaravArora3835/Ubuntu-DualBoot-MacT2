# Firmware Settings Notes

**Author:** Aarav Arora
**System:** MacBook Pro 13" (2019, Apple T2 Security Chip)
**Last Updated:** October 31, 2025

---

## 1. Overview

This document records all firmware-level changes made on the 2019 MacBook Pro to enable Ubuntu dual-boot installation while maintaining a secure, reversible configuration.

All changes were performed through **macOS Recovery → Startup Security Utility**, followed by **Terminal operations** where necessary.

---

## 2. Firmware Configuration Changes

### Secure Boot

* **Previous:** Full Security (default)
* **Changed To:** **No Security**

  * Disables Apple’s secure-boot verification chain, allowing non-Apple operating systems to boot.
  * Official Apple documentation states that *“No Security doesn’t enforce digital-signature verification”* for T2-equipped Macs.
  * Required to load the Ubuntu installer via external USB media.

### External Boot

* **Previous:** Disallow booting from external or removable media
* **Changed To:** **Allow booting from external media**

  * Enables startup from USB drives and third-party OS installers.
  * Without this change, the T2 chip blocks external drives at firmware level.

---

## 3. System Integrity Protection (SIP)

* **Previous:** Enabled (default)
* **Changed To:** **Disabled (temporary)**

  * Executed via Recovery Terminal: `csrutil disable`
  * Required to allow **rEFInd Boot Manager** to write to the EFI partition.
  * Verified using: `csrutil status` → “System Integrity Protection status: disabled.”
  * SIP will be re-enabled after successful Ubuntu installation to restore full macOS protection.

---

## 4. Verification Evidence

| File                                                 | Description                                                        |
| ---------------------------------------------------- | ------------------------------------------------------------------ |
| `/Screenshots/2025-10-30_SecureBoot_Settings.jpg`    | Startup Security Utility showing Secure Boot set to “No Security.” |
| `/Screenshots/2025-10-31_Disable_SIP_Recovery.jpg`   | Terminal screenshot taken in macOS Recovery during SIP disable.    |
| `/Screenshots/2025-10-31_SIP_Status_Disabled.jpg`    | Terminal output confirming SIP disabled.                           |
| `/Screenshots/2025-10-31_rEFInd_Install_Success.jpg` | Proof of rEFInd installation after firmware adjustments.           |
| `/Screenshots/2025-10-31_EFI_Boot_Menu.jpg`          | Visual confirmation of EFI Boot option at startup.                 |

---

## 5. Notes & Considerations

* These firmware adjustments are **mandatory** for installing Ubuntu on T2-equipped Macs.
* All modifications were made intentionally and can be reversed after installation.
* Administrator authentication was required in macOS Recovery before each change.
* Disabling SIP was performed only for the **rEFInd installation phase**, not for general use.
* After confirming a stable dual-boot environment, SIP and Secure Boot may both be re-enabled for long-term system security.

---

**Status:** Firmware reconfiguration and bootloader installation verified successfully on October 31, 2025.
**Next Step:** Proceed with Ubuntu installation and partition setup.
