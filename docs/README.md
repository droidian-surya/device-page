## Features & Usability

|                               	|    	|                                  	|    	|                      	|   	|
|-------------------------------	|----	|----------------------------------	|----	|----------------------	|---	|
| Manual brightnes              	|  ✅ 	| Battery lifetime > 24h from 100% 	|  ✅ 	| Automatic brightness  |  ✅ 	|
| No reboot needed for 1 week      	|  ❔	| Fingerprint reader  	                |  ✖️✖️   | Waydroid		|  ✅	|
| Torchlight                    	| ✅✖️ 	| Boot into UI                     	|  ✅ 	| GPS                 	|  ✅ 	|
| Vibration                     	|  ✅ 	| Hardware video playback          	|  ✅ 	| Proximity          	|  ✅ 	|
| Flashlight                    	| ✅✖️ 	| Anbox patches                    	|  ✅ 	| Rotation            	|  ✅ 	|
| Photo                         	| ✅✖️ 	| AppArmor patches                 	|  ✅ 	| Touchscreen          	|  ✅ 	|
| Video                         	| ✅✖️ 	| Battery percentage               	|  ✅ 	| Earphones           	|  ✅	|
| Switching between cameras     	| ✅✖️ 	| Offline charging                 	|  ❔	| Loudspeaker          	|  ✖️ 	|
| Dual SIM functionality        	| ✖️ ✖️  	| Online charging                  	|  ✅ 	| Microphone          	|  ✖️ 	|
| Carrier info, signal strength 	|  ✅ 	| SD card detection and access     	|  ✅ 	| Volume control       	|  ✅ 	|
| Data connection               	|  ✅ 	| RTC time                         	|  ✅ 	| Pin unlock           	|  ✅ 	|
| Incoming, outgoing calls      	|  ✅ 	| Shutdown / Reboot                	|  ✅ 	| ADB access          	|  ✖️✖️  	|
| MMS in, out                   	|  ❔ 	| Wireless External monitor        	|  ✖️✖️	| MTP access           	|  ✖️✖️  	|
| SMS in, out                    	|  ✅ 	| Bluetooth                        	|  ✅ 	| WiFi			|  ✅	|
| Change audio routings          	|  ❔	| Flight mode                      	|  ✅ 	| Hotspot		|  ✅	|
| Voice in calls                	|  ❔ 	|

- **✅** *Confirmed working.*
- **✅✖️** *Working to some extent but with issues.*
- **✖️** *Not Working.*
- **❔** *Not tested.*
- **✖️✖️** *Global issue.*

## Requirements
- Android 10 firmware for your device:
  - Poco X3 NFC ( Global ): https://xiaomifirmwareupdater.com/miui/surya/stable/V12.0.9.0.QJGMIXM/
  - Poco X3 ( India ): https://xiaomifirmwareupdater.com/miui/surya/stable/V12.0.9.0.QJGMIXM/

## Surya
- Download the latest rootfs:  [droidian-rootfs-api29gsi-arm64-xxxxxxxx.zip](https://github.com/droidian-images/rootfs-api29gsi-all/releases).
- Download the adaptation script: [adaptation-surya-script.zip](https://surya.bardia.tech/adaptation-surya-script.zip).
- Download [boot-surya.img](https://surya.bardia.tech/boot-surya.img), [dtbo-surya.img](https://surya.bardia.tech/dtbo-surya.img), [vbmeta-surya.img](https://surya.bardia.tech/vbmeta-surya.img).

## Karna
- Download the latest rootfs:  [droidian-rootfs-api29gsi-arm64-xxxxxxxx.zip](https://github.com/droidian-images/rootfs-api29gsi-all/releases).
- Download the adaptation script: [adaptation-surya-script.zip](https://surya.bardia.tech/adaptation-surya-script.zip).
- Download [boot-karna.img](https://surya.bardia.tech/boot-karna.img), [dtbo-karna.img](https://surya.bardia.tech/dtbo-karna.img), [vbmeta-karna.img](https://surya.bardia.tech/vbmeta-karna.img).

## Surya istallation
- Flash boot.img: `fastboot flash boot boot-surya.img`.
- Flash dtbo.img: `fastboot flash dtbo dtbo-surya.img`.
- Flash vbmeta.img: `fastboot --disable-verity --disable-verification flash vbmeta vbmeta-surya.img`.
- Flash your favorite recovery ( TWRP Recommended ).
- Format userdata as ext4 from inside the recovery or via fastboot: `fastboot format:ext4 userdata`.
- Now boot into recovery.
- Go into sideload mode and sideload droidian-rootfs-api29gsi-arm64-xxxxxxxx.zip: `adb sideload droidian-rootfs-api29gsi-arm64-xxxxxxxx.zip`
- Now extract adaptation-surya-script.zip on your PC/Laptop and push it to your device: `adb push adaptation-surya-script /tmp`
- Get a shell into your device: `adb shell`
- Change directory to /tmp and run the script: `cd /tmp/adaptation-surya-script && chmod +x install.sh && ./install.sh`
- Now boot into your device.
- *The first boot will take a while.*

## Karna installation
- Flash boot.img: `fastboot flash boot boot-karna.img`.
- Flash dtbo.img: `fastboot flash dtbo dtbo-karna.img`.
- Flash vbmeta.img: `fastboot --disable-verity --disable-verification flash vbmeta vbmeta-karna.img`.
- Flash your favorite recovery ( TWRP Recommended ).
- Format userdata as ext4 from inside the recovery or via fastboot: `fastboot format:ext4 userdata`.
- Now boot into recovery.
- Go into sideload mode and sideload droidian-rootfs-api29gsi-arm64-xxxxxxxx.zip: `adb sideload droidian-rootfs-api29gsi-arm64-xxxxxxxx.zip`
- Now extract adaptation-surya-script.zip on your PC/Laptop and push it to your device: `adb push adaptation-surya-script /tmp`
- Get a shell into your device: `adb shell`
- Change directory to /tmp and run the script: `cd /tmp/adaptation-surya-script && chmod +x install.sh && ./install.sh`
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
- Anything related to camera only works inside Waydroid.
- Dual SIM functionality is currently not implemented in Phosh so only one SIM works at the moment.
- Currently the sideloadable zip file is broken and results in a very long bootloop, so to install Droidian the adaptation script must be used.

## Final notes
- I'm not responsible for bricked devices, dead SD cards, thermonuclear war, or you getting fired because the alarm app failed.
- Please do some research if you have any concerns about features included in the products you find here before flashing it!
- YOU are choosing to make these modifications, and if you point the finger at me for messing up your device, I will laugh at you.

# Support
- Device specific telegram group: [@droidian_surya](https://t.me/droidian_surya).
- Droidian telegram group: [@DroidianLinux](https://t.me/DroidianLinux).
