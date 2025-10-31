# MacBook Pro 13" (2019) — Hardware and Setup Notes

**CPU:** 2.4 GHz Quad-Core Intel Core i5  
**RAM:** 16 GB LPDDR3  
**GPU:** Intel Iris Plus Graphics 655 (1536 MB)  
**Chip:** Apple T2 Security Chip  
**Ports:** Four Thunderbolt 3 (USB-C)

---

## Setup Considerations

- Disable Secure Boot in macOS Recovery.
- Allow external boot media.
- Use **balenaEtcher** to flash Ubuntu 24.04 ISO.
- Install **rEFInd** for easier boot management.
- Post-install, run the following commands to restore Wi-Fi and optimize battery life:

  ```bash
  sudo apt update && sudo apt upgrade -y
  sudo apt install firmware-b43-installer tlp -y
  sudo systemctl enable tlp
