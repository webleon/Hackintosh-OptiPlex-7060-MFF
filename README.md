# Hackintosh-OptiPlex-7070-SFF
**Opencore Bootloader tested on Catalina 10.15.7 and Big Sur 11.0.1**

**2020-11-15**
* Changed bootloader to Opencore 0.6.3
* Update MacOS to Big Sur 11.0.1
* Added a dedicate GPU RX560, changed SMBIOS to iMac 19,1
* ALC255 Audio didn't work with default OC configuration caused by IRQ conflicts. These has been patched with [SSDTTime](https://github.com/corpnewt/SSDTTime) 

**2020-03-27**
* Update MacOS to Catalina 10.15.4

## Introdution
This is the Hackintosh EFI Folder for Dell OptiPlex 7070 Small Form Factor. The configuration settings support MacOS Catalina and Big Sur. 
Because deep sleep will cause a kernel panic, I blocked sleep in BIOS. 

I'm using a iMac 19,1 SMBIOS to improve performance with dedicate GPU. If you only using the intergrated iGPU, set SMBIOS to Macmini 8,1 will avoid most of the issues with video. 

You will have to [**generate a new SMIBIOS**](https://github.com/corpnewt/GenSMBIOS) before login to your iCloud account.

## Hardware Specs
* **Desktop Computer**: [Dell OptiPlex 7070 Small Form Factor](https://www.dell.com/tc/business/p/optiplex-7070-desktop/pd) 
* **CPU**: [Intel® Core™ i7-9700](https://ark.intel.com/content/www/us/en/ark/products/191792/intel-core-i7-9700-processor-12m-cache-up-to-4-70-ghz.html)
* **iGPU**: Intel® UHD Graphics 630
* **GPU**: Radeon™ RX 560 (low profile)
* **RAM**: 64GB DDR4 2666 Daul Channel
* **HDD**: TOSHIBA RC500 NVMe SSD 500G
* **Wi-Fi & Bluetooth**: BCM943602CS with NGFF Adapter

## Working
* CPU Turbo Boost & Thermal Throttling
* Radeon™ RX 560 & iGPU acceleration
* ALC 255 audio
* All USB Ports
* LAN & Wireless Network
* Airdrop & Airplay
* Partly Sleep & Wakeup

## Not working
* 

## BIOS Settings
* General → Advanced Boot Options: ***uncheck***
* System Configuration → SATA Operation: ***AHCI***
* Secure Boot → Secure Boot Enable: ***Disabled***
* Intel® Software Guard Extensions™ → Intel® SGX™ Enable: ***Disabled***
* Power Management → Block Sleep: ***check***
* Virtualization Support → VT for Direct I/O: ***uncheck***

## BIOS Settings via GRUB (Optional)
* Set Pre-Allocated DVMT to 64M: 
***setup_var 0x8DC 0x02***
* Disable CFG lock: 
***setup_var 0x5BE 0x00***
