Example application using mynewt with a wyres w_basev2 card BSP and app-core central operation.

Clone this to use as a base for a specific application using the Wyres W_BaseV2 card.

To build the project, ensure that you have:
 - 'newt' build tool version 1.8 or later (from the apache mynewt project)
 - 'gcc' tool set for cross-compile to arm (gcc-arm-none-eabi package, version 2.35 or later : eg the gcc-arm-none-eabi-9-2019-q4-major-win32.zip package)
The easiest way to run the build is just to use the hex_maker.bat at the command line (with mingw64 or MSys2 shell) eg:
> hex_maker.bat wbasev2_test_eu868_none_dev

This will produce in the 'built' directory:
 - <targetname>.elf
 - <targetname>.hex
 - current.elf
 - current.hex
(The individual commands in this batch file can be executed directly at the command line if you want.)
The .hex contains the bootloader and the app, ready to load directly in the STM32. 
The .elfs contain the debug info neccessary for GDB type debugging - the 'current.elf' is the last build done so that your debugger run script can just 
reference this rather than explicit target names (in the case where you have multiple different targets in the same project)

To flash the w_basev2 cards, use a ST-LinkV2 with either OpenOCD (using the flash_stm32_stlink.bat) or the ST Loader tool directly with the .hex.

To debug OpenOCD is recommended, used with VisualStudio Code and an ST-Link v2 SWD adapter.

