# Hackintosh-OptiPlex-7060-MFF
**Bootloader tested on Big Sur 11.0.1**

## Introdution
This is the Hackintosh EFI Folder for Dell OptiPlex 7060 Micro Form Factor. The configuration settings support MacOS Big Sur. 

ALC255 Audio didn't work with default OC configuration caused by IRQ conflicts, has been patched with [SSDTTime](https://github.com/corpnewt/SSDTTime) .

You will have to [**generate a new SMIBIOS**](https://github.com/corpnewt/GenSMBIOS) before login to your iCloud account.

## Hardware Specs
* **Desktop Computer**: [Dell OptiPlex 7060 Micro Form Factor](https://www.dell.com/tc/business/p/optiplex-7060-micro/pd) 
* **CPU**: [Intel® Core™ i5-8600T](https://ark.intel.com/content/www/us/en/ark/products/129938/intel-core-i5-8600t-processor-9m-cache-up-to-3-70-ghz.html)
* **iGPU**: Intel® UHD Graphics 630
* **RAM**: 32GB DDR4 2666 Daul Channel
* **HDD**: WD SN550 NVMe SSD 1T
* **Wi-Fi & Bluetooth**: BCM94360CS2 with NGFF Adapter

## Working
* CPU Turbo Boost & Thermal Throttling
* iGPU acceleration
* ALC255 audio
* All USB Ports
* LAN & Wireless Network
* Airdrop & Airplay
* Partly Sleep & Wakeup

## Not working
* HDMI/DP Sound (Disabled because of the conflict with AppleALC.)

## BIOS Settings
* General → Advanced Boot Options: ***uncheck***
* System Configuration → SATA Operation: ***AHCI***
* Secure Boot → Secure Boot Enable: ***Disabled***
* Intel® Software Guard Extensions™ → Intel® SGX™ Enable: ***Disabled***
* Power Management → Block Sleep: ***check***
* Virtualization Support → VT for Direct I/O: ***uncheck***

## BIOS Settings via GRUB
* Set Pre-Allocated DVMT to 64M: 
***setup_var 0x8DC 0x02***
* Disable CFG lock: 
***setup_var 0x5BE 0x00***
