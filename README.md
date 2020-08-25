# FlyingBear Ghost 3D v3.1 Marlin v2 Firmware

This is the configuration.h and configuration\_adv.h files for stock FlyingBear Ghost 3D v3.1 for [Marlin](http://marlinfw.org) v2 firmware

Flyingbear has been busy with their new printers and forgets about the old ones. This was my attempt to upgrade the printer firmware. 

### why ?
Well, I wanted to upgrade the hardware in the printer and because of that, it's necessary to compile a new firmware with the new hardware support. 
Fortunatly, Flyingbear did sent me a Zip file with the Marlin v1.1.8 (or older) code when they sent me the new upgrades for the Ghost so I could flash the firmware (has well the firmware for the new LCD). 
This version went well and everything worked. 
Using this old version, I then tried to compile a new version, with mixed success. The major problem was the Y endstop didn't work. 
After searching, I discover that they also changed the (usual) pin assigment on the board - BOARD_MKS_GEN_L - pins_RAMPS.h was changed.
The next image shows the pinout for the board. 
![MKS GEN L Board PINOUT](https://github.com/feiticeir0/Flyingbear_Ghost_v3.1_Marlin_2_Firmware/blob/master/images/mks-gen-l-pinout.jpg)

**What did they change ?**

Well, because they wired the Y endstop to the X+ pins (on the board), the Y- endstop pin had to be changed for the correct PIN. 
Has you can see, Y- should be 14, but is 2 . 
![Flyingbear Y endstop wired in X+](https://github.com/feiticeir0/Flyingbear_Ghost_v3.1_Marlin_2_Firmware/images/Flyingbear_board.jpg)
This worked well for Marlin v1 and the Y endstop started working.... But not for Marlin v2 .
So, I removed the Y endstop wiring from X+ and wired it in Y-, thus, keeping untouched the pins_RAMPS.h file. 
This worked for Marlin v2. 
## How to use them

Just copy the files configuration.h and configuration\_adv.h to your downloaded Marlin firmware directory:
 - Marlin-2.0.x/Marlin

And compile the firmware for the Arduino MEGA 2560


## Disclosure

This files use the stock configurations for the FlyingBear Ghost 3D v3.1
They work for me - the Printer is working perfectly fine. 
Still, USE IT AT YOUR OWN RISK
 
