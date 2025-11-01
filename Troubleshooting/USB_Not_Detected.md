# USB Boot Media Not Detected — Issue and Resolution

**Date:** October 31, 2025
**System:** MacBook Pro 13″ (2019, T2 Chip)
**Author:** Aarav Arora

---

## 1. Summary

After flashing Ubuntu ISO to the 16 GB USB-C drive with balenaEtcher, the drive did not appear as a boot option.

---

## 2. Root Cause

Drive was formatted incorrectly prior to flashing — used APFS scheme instead of GUID Partition Map with FAT32.
macOS and T2 firmware require **GUID Partition Map** for bootable external media.

---

## 3. Resolution Steps

1. Opened **Disk Utility → View → Show All Devices**.
2. Selected the top-level USB drive (not the volume).
3. Clicked **Erase** → set:

   * **Format:** MS-DOS (FAT)
   * **Scheme:** GUID Partition Map
4. Re-flashed ISO using **balenaEtcher**.
5. Validated flashing and verification completed successfully.
6. Rebooted → USB now detected under EFI Boot.

---

## 4. Evidence

| Screenshot                                | Description                                         |
| ----------------------------------------- | --------------------------------------------------- |
| `2025-10-31_USB_Format_Settings.jpg`      | Correct format (FAT + GUID) applied before flashing |
| `2025-10-31_Etcher_Flashing_Progress.jpg` | Etcher in progress writing ISO                      |
| `2025-10-31_Etcher_Flash_Complete.jpg`    | Etcher validation successful                        |

---

## 5. Preventive Notes

* Always select the top-level USB device in Disk Utility before erasing.
* Use GUID Partition Map for bootable media on Mac hardware.
* Verify USB recognition in Startup Manager immediately after flashing.

---

**Status:** Resolved — USB installer detected and verified via EFI Boot menu.
**Impact:** Installation media ready for Ubuntu setup (11/1/2025).
