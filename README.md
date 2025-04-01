This tree contains BLHeli code for sensorless brushless motor electronic speed control (ESC) boards.  
  
To view and use the files, click the "Clone or download" button on this page,  
and then select "Download ZIP" to download the repository to your computer.  
  
For flashing, configuration and documentation, download the BLHeliSuite PC software:  
From [here](https://www.mediafire.com/folder/dx6kfaasyo24l/BLHeliSuite).  
Or for BLHeliSuite32 [here](https://github.com/bitdump/BLHeli/releases).  
Or the BLHeli_32 app [here](https://github.com/bitdump/BLHeli/tree/master/BLHeli_32%20ARM/BLHeli_32%20Android%20APP) or from Google Play.  
  
BLHeli was the first code developed, written in assembly for Atmel and Silabs 8bit MCUs.  
Three versions of the code were made, for heli main motor, tail motor and for multirotor.  
The code is open sourced under GPLv3.  

BLHeli_S was the second code developed, written in assembly for Silabs 8bit MCUs.  
BLHeli_S only supports multirotor applications, although it can also be used for planes.  
For BLHeli_S, focus was on making throttle response smooth.  
The code is open sourced under GPLv3.  

BLHeli_32 was the third code developed, written for 32bit MCUs.  
BLHeli_32 also only supports multirotor applications, although it can also be used for planes.  
The code is closed source.  

Documentation can be found here:  
[BLHeli Atmel](https://github.com/bitdump/BLHeli/blob/master/Atmel/BLHeli%20manual%20Atmel%20Rev14.x.pdf)  
[BLHeli Silabs](https://github.com/bitdump/BLHeli/blob/master/SiLabs/BLHeli%20manual%20SiLabs%20Rev14.x.pdf)  
[BLHeli_S](https://github.com/bitdump/BLHeli/blob/master/BLHeli_S%20SiLabs/BLHeli_S%20manual%20SiLabs%20Rev16.x.pdf)  
[BLHeli_32](https://github.com/bitdump/BLHeli/blob/master/BLHeli_32%20ARM/BLHeli_32%20manual%20ARM%20Rev32.x.pdf)  

For more information, check out these threads on RCG:  
[BLHeli](http://www.rcgroups.com/forums/showthread.php?t=2136895)  
[BLHeli_S](https://www.rcgroups.com/forums/showthread.php?2640796)  
[BLHeli_32](https://www.rcgroups.com/forums/showthread.php?2864611)  


适配我们使用的电调固件主要修改点：
ESCNO EQU J_ ;去除注释  
;**** **** **** **** ****  
; Select the MCU type (or unselect for use with external batch compile file)  
MCU_48MHZ EQU	1  
  
;**** **** **** **** ****  
; Select the fet deadtime (or unselect for use with external batch compile file)  
FETON_DELAY EQU 30	; 20.4ns per step  
  
;**** **** **** **** ****  
; Programming defaults  
;  
DEFAULT_PGM_STARTUP_PWR 				EQU 13 	; 1=0.031 2=0.047 3=0.063 4=0.094 5=0.125 6=0.188	7=0.25  8=0.38  9=0.50  10=0.75 11=1.00 12=1.25 13=1.50  
DEFAULT_PGM_DIRECTION				EQU 2 	; 1=Normal 	2=Reversed	3=Bidir		4=Bidir rev  
DEFAULT_PGM_BEEP_STRENGTH			EQU 1	; Beep strength  
  
; COMMON  
DEFAULT_PGM_MIN_THROTTLE				EQU 27	; 4*37+1000=1148  
DEFAULT_PGM_MAX_THROTTLE				EQU 250	; 4*208+1000=1832  
