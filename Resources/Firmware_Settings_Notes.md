# Firmware Settings Notes

**Author:** Aarav Arora  
**System:** MacBook Pro 13" (2019, Apple T2 Security Chip)  

---

## Firmware Configuration Changed

### Secure Boot  
- Previous: Full Security (default)  
- Changed to: **No Security**  
  (This disables the secure-boot verification chain on the T2 chip, allowing non-Apple OS boot)  
  Reference: Apple support says “No Security doesn’t enforce digital-signature verification” for T2 Macs. :contentReference[oaicite:2]{index=2}

### External Boot  
- Previous: Disallow booting from external or removable media  
- Changed to: **Allow booting from external media**  
  (Enables USB or other external drives to be used as startup disks) :contentReference[oaicite:3]{index=3}

---

## Verification Evidence  
- Screenshot file: `/Screenshots/2025-10-30_SecureBoot_Settings.jpg`  
  (Shows the Startup Security Utility window with the correct settings)  
- Date of change: October 30, 2025  

---

## Notes & Considerations  
- These changes are required before installing Ubuntu on T2-equipped Macs, otherwise the system will refuse to boot from the USB installer. :contentReference[oaicite:4]{index=4}  
- After installation is complete and working, you may optionally restore more secure firmware settings if you desire.  
- Changing firmware settings requires administrator authentication in Recovery Mode. :contentReference[oaicite:5]{index=5}  

