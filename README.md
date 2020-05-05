# ASUS-UX430UNR-OPENCORE
**Simply an opencore EFI for macos**
## DISCLAIMER 
This is not an incentive to hackintoshing! It's still not a good thing, buy a Mac if you need MacOS. But if you want to try the apple experience in order to determine if you are ready for buying a Mac... it's "ok".

## Description 
The name explains everyting, btw this is my opencore setup for MacOS Catalina 10.15.4 with OpenCore 0.5.7.
The Config, Kexts, Drivers and SSDTs are all made by hieplpvip.
I've used ndk-opencore fork cause my windows partition won't boot with the master fork. 
Anyway I've only changed some little things. 

## Details
The main thing that is really different is the ndk-opencore and the AppleALC Layout-id, mine is 21 the original hieplpvip
layaout-id for this pc is 13, but I've found that with 21 is better cause it can handle with external microphones too.
I have noticed a really nice thing, for me both 13 and 21 layouts are inject-ing audio at 44.100 Hz and that gives me a crackling sound, so i've managed it with SoundSource by changing it at 48000 Hz, better. I don't know if there's another option for solving this problem, for me is ok.

#### What's working? 
Everything, except als, fingerprint and original wifi (waiting for @zxystd), if you want you can change it with a compatible one. I don't like this solution.

##### SSDTs
The SSDTs that I'm using are the same as hieplpvip, and one made by me for injecting USBs so I can turn off ELAN fingerprint sensor (YES, it will not work).
##### KEXTS
  * **_Lilu, WhateverGreen, AsusSMC, VirtualSMC, AppleALC, ACPIPoller, VoodooI2C, VoodooI2CHID, VoodooPS2Controller, VoodooTCSSync, SMCProcessor, SMCBatteryManager_** All for the hardware, pretty sure these are needed in every configuration.
  * **_AirportBrcmFixup_** I'm not sure this is working for me cause I'm using the Intel Bluetooth and an ArcherT2U Nano for wifi.
  * **_BT4LEContinuityFixup_** Same.
  * **_NullEthernet_** I'm using a wifi dongle, oh yes iMessage and Facetime "can" work.
  * **_NoTouchID_** This is only for booting speedup, so the OS can't ask for something like a TouchID.
  * **_IntelBluetoothFirmware and IntelBluetoothInjector_** The kexts provided by hieplpvip for bluetooth didn't work for me, somethimes the bluetooth stopped working, sometimes did not work at all and for make it work i had to reboot in windows and then in MacOS.These solved everything.

##### Drivers
Only these : ApfsDriverLoader, AudioDxe, HFSPlus, OpenRuntime, OpenCanopy(Apple style visual bootloader)

### Conclusion
If you are familiar with hardware and pc warranty you can change your wifi (and bluetooth) adapter with a compatible one, and in this case you will need to delete NullEthernet kext and change the bluetooth kext with che original provided by hieplpvip (for the moment I don't like the idea of changing my hardware). In order to use everything you will need to create a good SMBIOS, I've used GenSMBIOS. I suggest you to edit the config only with a plist editor like Xcode or ProperTree, do not open this thing with CloverConfigurator it will "break" it.

### Credit
[hieplpvip -> ASUS-ZENBOOK-HACKINTOSH](https://github.com/hieplpvip/ASUS-ZENBOOK-HACKINTOSH) 
And all credits by hieplpvip in this [Reference](https://github.com/hieplpvip/ASUS-ZENBOOK-HACKINTOSH/wiki/References).

[zxystd -> IntelBluetoothFirmware](https://github.com/zxystd/IntelBluetoothFirmware)

[al3xtjames -> NoTouchID](https://github.com/al3xtjames/NoTouchID)

[n-d-k -> OpenCore Fork](https://github.com/n-d-k/OpenCorePkg)
