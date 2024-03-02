# MKS-DLC32-FIRMWARE

The original software is based on the MKS DLC2 port of grbl32.   I'm only interested in the base hardware & screen code, so I'm forking this to extract these pieces.  My plan is to use this as a platform for any project that requires stepper motors/servos/solenoid, etc.  It's quite a nice board (you can get the DLC32 board, 3 tmc2209 stepper drivers and the 480x320 TS-R screen for $33.   There isn't as much documentation for the screen as I would like, so I'm starting with this code.  There also seems to be general conflics on the ESP32 between the SD card and the screen when both are on SPI busses (even if they're completely separate/  

Project goals:

-Extract screen support & create a standalone module I can integrate into any ESP32 project  (by module, I'm looking for only a single interface header file/c++ file with API calls easily accessed from C++ or C (no class hierarchy).  If TS32R_SCREEN is not defined, ts35_api.cpp & ts35_api.h should provide stub code.  I'm not familiar enough with Visual Studio environment to make the build conditional (or to prevent extra builds - would mostly like to treat this as a .a library file.

-Include some starter LVGL code.

-Include SD as module.

Include Webserver & Bluetooth as modules

## Environment construction:

- vscode

- platformIO

PlatformIOc needs to be installed on vscode.

Open Firmware with vscode, and platformIO will be started, In the platform.ini file，

`default_envs = mks_dlc32_v2_1` 

Note:We will make a pin suitable for V1.0，Settings corresponding to the selection of coreXY.

Then compile and download.

