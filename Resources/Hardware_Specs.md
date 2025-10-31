# MacBook Pro Hardware Specifications

**Device Model:** MacBook Pro (13-inch, 2019, Four Thunderbolt 3 Ports)  
**Chip:** Apple T2 Security Chip  
**Processor:** 2.4 GHz Quad-Core Intel Core i5 (8th Generation)  
**Memory:** 16 GB 2133 MHz LPDDR3  
**Graphics:** Intel Iris Plus Graphics 655 (1536 MB)  
**Storage:** 512 GB SSD (130 GB available pre-installation)  
**Operating System:** macOS Ventura  
**Ports:** Four Thunderbolt 3 (USB-C)  
**Wi-Fi Adapter:** Broadcom BCM4364 (requires firmware-b43-installer on Ubuntu)

---

## Firmware & BIOS Details
- **Secure Boot:** Disabled (set to “No Security”)  
- **External Boot:** Enabled (set to “Allow booting from external media”)  
- **Startup Manager Key:** Option (⌥) during boot  
- **Recovery Mode Key:** Command (⌘) + R during boot  
- **Firmware Utility Used:** Startup Security Utility (in macOS Recovery)

---

## Disk Configuration
| Item | Description |
|------|--------------|
| Drive Type | Apple NVMe SSD |
| Total Capacity | 512 GB |
| Available Space | 130 GB |
| Partition Scheme | GUID Partition Map |
| File System | APFS |
| Planned Ubuntu Partition | 70 GB (to be created during installation) |

---

## Notes
- This model uses Apple’s **T2 Security Chip**, which manages Secure Boot and internal drive encryption.  
- Linux installation requires disabling Secure Boot and allowing external boot.  
- Wi-Fi, audio, and camera rely on proprietary Apple drivers that must be configured post-installation.  
- All hardware was verified functional under macOS prior to installation.

---

**File Created:** October 30, 2025  
**Author:** Aarav Arora  
**Purpose:** System reference for Ubuntu dual-boot configuration
