# ASUS-UX430UN-OPENCORE

## Description 
The name explains everyting, btw this is my opencore setup for MacOS Catalina 10.15.4.
The Config, Kexts, Drivers and SSDTs are all made by hieplpvip.
I've used ndk-opencore fork cause my windows partition won't boot with the master fork. 
Anyway I've only changed some little things 

## Details
The main thing that is really different is the ndk-opencore and the AppleALC Layout-id, mine is 21 the original hieplpvip
layaout-id for this pc is 13, but I've found that with 21 is better cause it can handle with external microphones too.
I have noticed a really nice thing, for me both 13 and 21 layouts are inject-ing audio at 44.100 Hz and that gives me a crackling sound, so i've managed it with SoundSource by changing it at 48000 Hz, better. I don't know if there's another option for solving this problem, for me is ok.

### SSDT 
The SSDTs that I'm using are the same as hieplpvip, and one made by me for injecting USBs so I can turn off ELAN fingerprint sensor (YES, it will not work).
### KEXTS
##### Lilu, WhateverGreen, AsusSMC, VirtualSMC, AppleALC, ACPIPoller, VoodooI2C, VoodooI2CHID, VoodooPS2Controller, VoodooTCSSync
All for the hardware, pretty sure these are needed in every configuration.
##### AirportBrcmFixup 
I'm not sure this is working for me cause I'm using the Intel Bluetooth and an ArcherT2U Nano for wifi.
##### BT4LEContinuityFixup
Same
##### NullEthernet 
I'm using a wifi dongle, oh yes iMessage and Facetime "can" work.
##### NoTouchID 
This is only for booting speedup, so the OS can't ask for something like a TouchID.
##### IntelBluetoothFirmware and IntelBluetoothInjector 
The kexts provided by hieplpvip for bluetooth didn't work for me, somethimes the bluetooth stopped working, sometimes did not work at all and for make it work i had to reboot in windows and then in MacOS.
