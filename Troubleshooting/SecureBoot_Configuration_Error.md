# Secure Boot Configuration — Issue and Resolution

**Date:** October 31, 2025
**System:** MacBook Pro 13″ (2019, T2 Chip)
**Author:** Aarav Arora

---

## 1. Summary

Initial USB boot attempts failed to show the “EFI Boot” option.
The T2 chip restricted external booting due to default firmware security settings.

---

## 2. Root Cause

**Secure Boot = Full Security** and **External Boot = Disallowed** in Startup Security Utility prevent any non-Apple OS media from booting.

---

## 3. Resolution Steps

1. Booted into **macOS Recovery (⌘ + R)**.
2. Opened **Startup Security Utility** → authenticated as admin.
3. Changed settings:

   * **Secure Boot:** *No Security*
   * **External Boot:** *Allow booting from external media*
4. Rebooted Mac and held **Option (⌥)** to access Startup Manager.
5. Verified appearance of **EFI Boot (orange USB icon)** for Ubuntu installer.

---

## 4. Evidence

| Screenshot                           | Description                                                |
| ------------------------------------ | ---------------------------------------------------------- |
| `2025-10-30_SecureBoot_Settings.jpg` | Secure Boot and External Boot options adjusted in Recovery |
| `2025-10-31_EFI_Boot_Menu.jpg`       | EFI Boot recognized after firmware changes                 |

---

## 5. Preventive Notes

* Keep Secure Boot = *No Security* until Ubuntu installation is complete.
* Post-installation, re-enable *Medium Security* or *Full Security* if macOS is primary OS.
* Maintain photo evidence for audit and portfolio records.

---

**Status:** Resolved — EFI Boot visible and functional.
**Impact:** MacBook now accepts external boot media for Ubuntu installation.
