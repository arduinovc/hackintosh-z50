# Hackintosh-z50

EFI boot folder based on OpenCore for Toshiba Z50  
Last update: December 12th 2024. 

## Description

EFI files based on OpenCore  
OpenCore version: 1.0.3  
Compatible macOS version: __Sequoia 15.1.1__  
Tested with: __Monterey 12.7.4__ & __Ventura 13.7.2__ & __Sonoma 14.7.2__ 

Updated with the latest versions :
![Toshiba Tecra Z50 macOS versions](/Assets/macos-versions.png "Toshiba Tecra Z50") 

## How to use

1/ Download a release corresponding to your macOS version  
2/ Extract it on USB stick (GPT disk with FAT32 primary partition) or EFI partition  
3/ Generate a new "SystemSerialNumber" and "SystemUUID" using OCAuxiliaryTools for example  
4/ Save and reboot  

### Important note: macOS Ventura, Sonoma and Sequoia  

Required to patch root with OpenCore Legacy Patcher (actual version 2.2.0) to enable GPU acceleration and Wifi(Sequoia).  
To root patch, I edit boot-args and csr-active-config inside config.plist file :  
- enable AMFIPass.kext to disable AMFI  
- csr-active-confi=EF0F0000 to disable SIP  

Some apps cannot work with this : Steam / Shadow.tech / Music (Apple DRM) / Adobe apps (Illustrator / Photoshop)    

I recommend to use MacOS Monterey for full support.  

MacOS Monterey is the last OS supporting natively HD4000 iGPU.  

### Important note: Intel Wireless Card with Sequoia  

Airportitlwm actually doesn't support Sequoia. That's the trick:  
- use OCAuxiliaryTools and edit config.plist to uncomment DP/PCIExpress entry (remove #)  
- reboot computer and patch with OpenCore Legacy Patcher
- reboot computer again and comment DP/PCIExpress entry (set #)  
- reboot another time your laptop  

It uses *Ventura*-airportitlwm.kext to work under Sequoia.  
Actually, there is no Bluetooth support.  

## Hardware

__Laptop Toshiba Tecra Z50-A__  
![Toshiba Tecra Z50](/Assets/TecraZ50.jpeg "Toshiba Tecra Z50")  
[Datasheet Toshiba](/Assets/Toshiba-Z50-A-Datasheet.pdf)  

| Type	| Name                   |
|:------|:-----------------------|
| CPU	| Intel i5 4210U	 |
| RAM	| 2xDDR3l 1600MHz - 8Gb  |
| GPU	| Intel HD Graphics 4400 |
| Drive	| mSATA SSD 500 Gb	 |
| Sound	card	| Realtek ALC283	 |
| WLAN	| Intel Wireless 7260 	 |
| Bluetooth | Intel Wireless 7260 #Port008 |
| LAN	| Intel I218-V 		 |
| Display | LVDS or eDP display |

## SMBIOS Info

System Product Name : Macbook Pro 16.4  
System Serial : C02DH04QMD6T  

## Working and Not-Working

### Working
WIFI : ok  
GPU : ok   
Shutdown/Restart : ok  
USB Port : ok  
Sound : ok (speakers and microphone)  
Brightness : ok  
Webcam : ok  
Keyboard : ok  
Card Reader : ok  
Bluetooth : ok  
Auto-unlock : with BLEUnlock  
Boot shime : ok

### Working with issue

Sleep/Wake : partially (randomly not enter in sleep mode)    
Touchpad : partially (need improvements / broken gestures)    
  
### Not-Working
  
HDMI port: doesn't work at all. Not included in this Macbook Pro SMBIOS.  
  
## Screenshots
  
### macOS Sequoia 15.1.1  
![Toshiba Tecra Z50 Sequoia](/Assets/Sequoia.png "Toshiba Tecra Z50")
![Toshiba Tecra Z50 SystemInfo](/Assets/Sequoia-SystemInfo.png "Toshiba Tecra Z50")
![Toshiba Tecra Z50 SystemSettings](/Assets/Sequoia-SystemSettings.png "Toshiba Tecra Z50")
![Toshiba Tecra Z50 Passwords](/Assets/Sequoia-Passwords.png "Toshiba Tecra Z50")
  
### macOS Sonoma 14.3  
Upgrade from Ventura to Sonoma
![Toshiba Tecra Z50 Monterey](/Assets/Sonoma.png "Toshiba Tecra Z50")
![Toshiba Tecra Z50 SystemInfo](/Assets/Sonoma-SystemInfo.png "Toshiba Tecra Z50")
![Toshiba Tecra Z50 SystemSettings](/Assets/Sonoma-SystemSettings.png "Toshiba Tecra Z50")
![Toshiba Tecra Z50 OCAuxiliaryTools](/Assets/Sonoma-FinalCut.png "Toshiba Tecra Z50")
  
### macOS Ventura 13.6.4  
Upgrade from Monterey to Ventura
![Toshiba Tecra Z50 Monterey](/Assets/Ventura.png "Toshiba Tecra Z50")
![Toshiba Tecra Z50 SystemInfo](/Assets/Ventura-SystemInfo.png "Toshiba Tecra Z50")
![Toshiba Tecra Z50 SystemSettings](/Assets/Ventura-SystemSettings.png "Toshiba Tecra Z50")
![Toshiba Tecra Z50 OCAuxiliaryTools](/Assets/Ventura-Launchpad.png "Toshiba Tecra Z50")
  
### macOS Monterey 12.7.1  
Last OS with native HD4400 support (no root patch)  
![Toshiba Tecra Z50 Monterey](/Assets/Monterey.png "Toshiba Tecra Z50")
![Toshiba Tecra Z50 SystemInfo](/Assets/SystemInfo.png "Toshiba Tecra Z50")
![Toshiba Tecra Z50 SystemSettings](/Assets/SystemSettings.png "Toshiba Tecra Z50")
![Toshiba Tecra Z50 OCAuxiliaryTools](/Assets/OCAuxiliaryTools.png "Toshiba Tecra Z50")
  
## Work to do

Improve HDMI support  
Improve ALPS Touchpad support  
Try to upgrade Monterey to Ventura or Sonoma : works (but need OpenCore Legacy Patcher)  

## About Boot Shime
I added boot shime. It can be disable by turning "AudioSupport" OFF in config.plist (section UEFI/Audio).  

## Credit

EFI Base folder : https://github.com/yanpol199/toshiba_z50_hackintosh  
Bluetooth fix : https://github.com/yusufklncc/Toshiba-Portege-Z30-Hackintosh  
BLEUnlock : https://github.com/ts1/BLEUnlock  
