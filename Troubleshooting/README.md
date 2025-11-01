# Troubleshooting Overview — Ubuntu Dual Boot on MacBook Pro (2019, T2 Chip)

**Author:** Aarav Arora
**Last Updated:** October 31, 2025

---

## 1. Purpose

This directory documents every technical issue encountered during the Ubuntu dual-boot pre-installation phase and the steps taken to resolve them.
Each entry includes root cause analysis, recovery commands, and screenshot evidence.

---

## 2. Files Included

| File                                           | Description                                                                            |
| ---------------------------------------------- | -------------------------------------------------------------------------------------- |
| `2025-10-31_SIP_Issue_and_Resolution.md`       | SIP restriction blocking rEFInd installer — resolved via Recovery Terminal             |
| `2025-10-31_SecureBoot_Configuration_Error.md` | T2 Secure Boot prevented external boot media — resolved by adjusting firmware settings |
| `2025-10-31_USB_Not_Detected.md`               | USB media not recognized after flashing — resolved by reformatting and reflashing      |
| `README.md`                                    | Directory index and summary of troubleshooting logs                                    |

---

## 3. Key Takeaways

* Apple’s T2 chip adds multiple layers of firmware security that must be adjusted for Linux compatibility.
* Most issues stem from SIP and Secure Boot interference with EFI modifications.
* Careful logging and verification ensures reversible and secure configuration changes.
* Each resolution was documented with timestamped screenshots for portfolio evidence.

---

**Status:** All known issues resolved as of October 31, 2025.
**Next Phase:** Proceed with Ubuntu installation on November 1 and log any driver or bootloader issues encountered post-install.
