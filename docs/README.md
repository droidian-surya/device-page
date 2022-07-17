## Features & Usability

|                               	|    	|                                  	|    	|                      	|   	|
|-------------------------------	|----	|----------------------------------	|----	|----------------------	|---	|
| Manual brightnes              	|  ✅ 	| Battery lifetime > 24h from 100% 	|  ✅ 	| Automatic brightness  |  ✅ 	|
| No reboot needed for 1 week      	|  ❔	| Fingerprint reader  	                |  ✖️ 	| Waydroid		|  ✖️	|
| Torchlight                    	|  ✖️ 	| Boot into UI                     	|  ✅ 	| GPS                 	|  ✅ 	|
| Vibration                     	|  ✅ 	| Hardware video playback          	|  ✅ 	| Proximity          	|  ❔ 	|
| Flashlight                    	|  ✖️ 	| Anbox patches                    	|  ✅ 	| Rotation            	|  ✅ 	|
| Photo                         	|  ✖️ 	| AppArmor patches                 	|  ✅ 	| Touchscreen          	|  ✅ 	|
| Video                         	|  ✖️ 	| Battery percentage               	|  ✅ 	| Earphones           	|  ✖️ 	|
| Switching between cameras     	|  ✖️ 	| Offline charging                 	|  ❔	| Loudspeaker          	|  ✖️ 	|
| Dual SIM functionality        	|  ✖️ 	| Online charging                  	|  ✅ 	| Microphone          	|  ✖️ 	|
| Carrier info, signal strength 	|  ✅ 	| SD card detection and access     	|  ✅ 	| Volume control       	|  ✅ 	|
| Data connection               	|  ✅ 	| RTC time                         	|  ✅ 	| Pin unlock           	|  ✅ 	|
| Incoming, outgoing calls      	|  ✅ 	| Shutdown / Reboot                	|  ✅ 	| ADB access          	|  ✖️ 	|
| MMS in, out                   	|  ❔ 	| Wireless External monitor        	|  ✅✖️ 	| MTP access           	|  ✖️ 	|
| SMS in, out                    	|  ✅ 	| Bluetooth                        	|  ✅ 	| WiFi			|  ✅	|
| Change audio routings          	|  ❔	| Flight mode                      	|  ✅ 	| Hotspot		|  ❔	|
| Voice in calls                	|  ❔ 	|
| surya                           |  ✅  | karna                            | ❔ |

- **✅** *Confirmed working.*
- **✅✖️** *Working to some extent but with issues.*
- **✖️** *Not Working.*
- **❔** *Not tested.*

## Requirements

- Android 10 firmware for your device:
  - Poco X3 NFC ( Global ): https://xiaomifirmwareupdater.com/miui/surya/stable/V12.0.9.0.QJGMIXM/
  - Poco X3 ( India ): ?

## surya
- Download the latest rootfs:  [droidian-rootfs-api29gsi-arm64-xxxxxxxx.zip](https://github.com/droidian-images/rootfs-api29gsi-all/releases).
- Download the adaptation package: [droidian-adaptation-surya.zip](https://bardia.tech/droidian/droidian-adaptation-surya.zip).
- Download [boot.img](https://bardia.tech/droidian/boot-surya.img), [dtbo.img](https://bardia.tech/droidian/dtbo-surya.img), [vbmeta.img](https://bardia.tech/droidian/vbmeta-surya.img).

## karna
- not yet

## Installation
- Flash boot.img: `fastboot flash boot boot.img`.
- Flash dtbo.img: `fastboot flash dtbo dtbo.img`.
- Flash vbmeta.img: `fastboot --disable-verity --disable-verification flash vbmeta vbmeta.img`.
- Flash your favorite recovery ( TWRP Recommended ).
- Format userdata as ext4 from inside the recovery or via fastboot: `fastboot format:ext4 userdata`.

- Sideload droidian-rootfs-api29gsi-arm64-xxxxxxxx.zip.
- Sideload droidian-adaptation-surya.zip
- Now boot into your device.
- *The first boot will take a while.*

## Notes
- The default password is `1234`.
- If you see a black screen, don't worry it takes a long time to boot.
- **Droidian GSIs are experimental! Bugs and missing features are expected.**

## Bugs
- Mobile data needs an APN to be set up from Settings -> Mobile -> Acess Point Names.
- Mobile data might stop working after making or recieving phone calls. Toggle Mobile Data from the settins off/on.
- Booting times are currently within 5-10 minutes. 
- Anything related to cameras do not work it is a global issue across all devices, it does however work in Waydroid which is currently not available on surya.
- Dual SIM functionality is currently not implemented in Phosh so only one SIM works at the moment.
- I'm not responsible for bricked devices, dead SD cards, thermonuclear war, or you getting fired because the alarm app failed.
- Please do some research if you have any concerns about features included in the products you find here before flashing it!
- YOU are choosing to make these modifications, and if you point the finger at me for messing up your device, I will laugh at you.

# Support
- Device specific telegram group: [@droidian_surya](https://t.me/droidian_surya).
- Droidian telegram group: [@DroidianLinux](https://t.me/DroidianLinux).

