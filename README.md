# Hackintosh-z50

EFI boot folder based on OpenCore for Toshiba Z50  
Last update: January 12th 2024. 

## Description

EFI files based on OpenCore  
OpenCore version: 0.9.7  
MacOS version: __Monterey 12.7.1__

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

### Working with issue

Sleep/Wake : partially (randomly not enter in sleep mode)  
HDMI : ok but sometimes it doesn't respond  
Touchpad : partially (need improvements / broken gestures)  
Bluetooth : partially (not pairing iPhone / maybe missing UnlockFeatures kext)  

### Not-Working
 
NumLock : nok  

## Screenshots
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
