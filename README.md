# Hackintosh-z50

EFI boot folder based on OpenCore for Toshiba Z50  
Last update: February 2nd 2024. 

## Description

EFI files based on OpenCore  
OpenCore version: 0.9.7  
Actual compatible macOS version: __Sonoma 14.3__  
Tested with: __Monterey 12.7.3__ & __Ventura 13.6.4__  

## How to use

1/ Download a release corresponding to your macOS version  
2/ Extract it on USB stick (GPT disk with FAT32 primary partition) or EFI partition  
3/ Generate a new "SystemSerialNumber" and "SystemUUID" using OCAuxiliaryTools for example  
4/ Save and reboot  

### macOS Ventura and Sonoma

Required to patch root with OpenCore Legacy Patcher (actual version 1.3.0)  to enable GPU acceleration.  
To root patch, I edit boot-args and csr-active-config inside config.plist file :  
- amfi_get_out_of_my_way=1 to disable AMFI  
- car-active-confi = EF0F0000 to disable SIP  
Some apps cannot work with this inc. Steam or Shadow.tech  

## Hardware

__Laptop Toshiba Tecra Z50-A__  
![Toshiba Tecra Z50](/Assets/TecraZ50.jpeg "Toshiba Tecra Z50")


| Type	| Name                   |
|:------|:-----------------------|
| CPU	| Intel i5 4200U	 |
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

### Working with issue

Sleep/Wake : partially (randomly not enter in sleep mode)  
HDMI : ok but sometimes it doesn't respond  
Touchpad : partially (need improvements / broken gestures)    
Audio quality : not good

### Not-Working
 
NumLock : nok  

## Screenshots

### macOS Sonoma 14.3  
Upload soon  

### macOS Ventura 13.6.4  
Upload soon  

### macOS Monterey 12.7.1  
![Toshiba Tecra Z50 Monterey](/Assets/Monterey.png "Toshiba Tecra Z50")
![Toshiba Tecra Z50 SystemInfo](/Assets/SystemInfo.png "Toshiba Tecra Z50")
![Toshiba Tecra Z50 SystemSettings](/Assets/SystemSettings.png "Toshiba Tecra Z50")
![Toshiba Tecra Z50 OCAuxiliaryTools](/Assets/OCAuxiliaryTools.png "Toshiba Tecra Z50")

## Work to do

Improve HDMI support  
Improve ALPS Touchpad support  
Try to upgrade Monterey to Ventura or Sonoma  

## Credit

EFI Base folder : https://github.com/yanpol199/toshiba_z50_hackintosh  
Bluetooth fix : https://github.com/yusufklncc/Toshiba-Portege-Z30-Hackintosh  
https://github.com/ts1/BLEUnlock  
