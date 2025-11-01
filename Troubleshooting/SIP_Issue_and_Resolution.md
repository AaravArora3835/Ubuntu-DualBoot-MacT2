# System Integrity Protection (SIP) — Issue and Resolution

**Date:** October 31, 2025
**System:** MacBook Pro 13″ (2019, T2 Chip)
**Author:** Aarav Arora

---

## 1. Summary

During installation of **rEFInd Boot Manager**, the macOS terminal displayed an error indicating **System Integrity Protection (SIP) enabled**.
SIP blocked EFI modifications required for the bootloader.

---

## 2. Root Cause

macOS’s SIP restricts write access to EFI system partitions and prevents unsigned kernel or bootloader installations.
This protection is default on all T2-equipped Macs.

---

## 3. Resolution Steps

1. **Booted into macOS Recovery** (⌘ + R on startup).
2. **Opened Terminal** → executed:

   ```
   csrutil disable
   ```
3. **Restarted macOS** and verified:

   ```
   csrutil status
   ```

   → Output: `System Integrity Protection status: disabled.`
4. **Re-ran rEFInd installer:**

   ```
   ./refind-install
   ```

   → Installation completed successfully.
5. **Rebooted** and confirmed rEFInd boot menu visible.

---

## 4. Evidence

| Screenshot                              | Description                        |
| --------------------------------------- | ---------------------------------- |
| `2025-10-31_Disable_SIP_Recovery.jpg`   | SIP disabled via Recovery Terminal |
| `2025-10-31_SIP_Status_Disabled.jpg`    | Verification of disabled status    |
| `2025-10-31_rEFInd_Install_Success.jpg` | Successful EFI installation output |

---

## 5. Preventive Notes

* SIP should remain disabled **only** until Ubuntu installation completes.
* After verifying dual-boot functionality, re-enable with:

  ```
  csrutil enable
  ```
* Document both disable and enable dates in firmware logs for transparency.

---

**Status:** Resolved — rEFInd installation successful after SIP adjustment.
**Impact:** System now EFI-boot ready for Ubuntu installer.
