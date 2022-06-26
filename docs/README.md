## Features & Usability

|                               	|    	|                                  	|    	|                      	|   	|
|-------------------------------	|----	|----------------------------------	|----	|----------------------	|---	|
| Manual brightnes              	|  + 	| Battery lifetime > 24h from 100% 	|  + 	| Automatic brightness  |  - 	|
| No reboot needed for 1 week      	|  - 	| Fingerprint reader  	                |  - 	| Waydroid		|  -	|
| Torchlight                    	|  - 	| Boot into UI                     	|  + 	| GPS                 	|  - 	|
| Vibration                     	|  + 	| Hardware video playback          	|  + 	| Proximity          	|  - 	|
| Flashlight                    	|  - 	| Anbox patches                    	|  + 	| Rotation            	|  + 	|
| Photo                         	|  - 	| AppArmor patches                 	|  + 	| Touchscreen          	|  + 	|
| Video                         	|  - 	| Battery percentage               	|  + 	| Earphones           	|  + 	|
| Switching between cameras     	|  - 	| Offline charging                 	|  - 	| Loudspeaker          	|  + 	|
| Dual SIM functionality        	|  - 	| Online charging                  	|  + 	| Microphone          	|  + 	|
| Carrier info, signal strength 	|  +- 	| SD card detection and access     	|  + 	| Volume control       	|  + 	|
| Data connection               	|  +- 	| RTC time                         	|  + 	| Pin unlock           	|  + 	|
| Incoming, outgoing calls      	|  + 	| Shutdown / Reboot                	|  + 	| ADB access          	|  - 	|
| MMS in, out                   	|  ? 	| Wireless External monitor        	|  - 	| MTP access           	|  - 	|
| SMS in, out                    	|  + 	| Bluetooth                        	|  +- 	| WiFi			|  +	|
| Change audio routings          	|  +-	| Flight mode                      	|  + 	| Hotspot		|  -	|
| Voice in calls                	|  + 	|

- **+** *Confirmed working.*
- **+-** *Working to some extent but with issues.*
- **-** *Not Working.*
- **?** *Not tested.*

## Requirements

- Android 10 firmware for your device:
  - Redmi 9A dandelion: [LINK](https://xiaomifirmwareupdater.com/archive/miui/dandelion/).
  - Redmi 9C angelica: [LINK](https://xiaomifirmwareupdater.com/archive/miui/angelica/).

## dandelion
- Download the latest rootfs:  [droidian-rootfs-api29gsi-arm64-xxxxxxxx.zip](https://github.com/droidian-images/rootfs-api29gsi-all/releases).
- Download the adaptation for dandelion: [droidian-adaptation-dandelion.zip](https://bardia.tech/droidian/droidian-adaptation-dandelion.zip).
- Download [boot.img](https://bardia.tech/droidian/boot-dandelion.img), [dtbo.img](https://bardia.tech/droidian/dtbo-dandelion.img), [vbmeta.img](https://bardia.tech/droidian/vbmeta-dandelion.img).

## angelica
- Download the latest rootfs:  [droidian-rootfs-api29gsi-arm64-xxxxxxxx.zip](https://github.com/droidian-images/rootfs-api29gsi-all/releases).
- Download the adaptation for dandelion: [droidian-adaptation-angelica.zip](https://bardia.tech/droidian/droidian-adaptation-angelica.zip).
- Download [boot.img](https://bardia.tech/droidian/boot-angelica.img), [dtbo.img](https://bardia.tech/droidian/dtbo-angelica.img), [vbmeta.img](https://bardia.tech/droidian/vbmeta-angelica.img).

## Installation
- Flash boot.img: `fastboot flash boot boot.img`.
- Flash dtbo.img: `fastboot flash dtbo dtbo.img`.
- Flash vbmeta.img: `fastboot --disable-verity --disable-verification flash vbmeta vbmeta.img`.
- Flash your favorite recovery.
- Format userdata as ext4 from inside the recovery or via fastboot: `fastboot format:ext4 userdata`.

- Sideload droidian-rootfs-api29gsi-arm64-xxxxxxxx.zip.
- Now boot into your device.
- *The first boot will take a while*.

## Notes
- The default password is `1234`.
- Not every app will work as they might need aditional packages (eg: Telegram Desktop needs qtwayland5 to be installed to run). Google or [@Droidian](https://t.me/DroidianLinux) is your best friend in this case.
- Automatic app scaling [per app](https://forums.puri.sm/t/librem-5-scale-to-fit/11399/3) or globally: `gsettings set sm.puri.phoc scale-to-fit true`.
- [Tweaks](https://wiki.mobian-project.org/doku.php?id=tweaks).
- [Theming](https://wiki.mobian-project.org/doku.php?id=themes).
- **Droidian GSIs are experimental! Bugs and missing features are expected.**

## Bugs
- Mobile data needs an APN to be set up from Settings -> Mobile -> Acess Point Names.
- RIL gets broken after switching airplane mode or modem off/on.
- Mobile data might stop working after making or recieving phone calls. Toggle Mobile Data from the settins off/on.
- Mobile data quick toggle doesn't work.
- Bluetooth can be used via the termianl using bluetoothctl command but does not work via the settings app.
- Signal strengh is reported at 1% but Mobile data and calls work just fine.
- Anything related to cameras do not work it is a global issue across all devices, it does however work in Waydroid which is currently not available on angelica and dandelion.
- Changing audio to speaker in calls does not work on dandelion but works on angelica.
- earbuds or earphones do not work on dandelion but work on angelica.
- Dual sim functionality is currently not implemented in phosh so only one sim works at the moment.

# Support
- Device specific telegram group: [@ut_angelica](https://t.me/ut_angelica).
- Droidian telegram group: [@DroidianLinux](https://t.me/DroidianLinux).
