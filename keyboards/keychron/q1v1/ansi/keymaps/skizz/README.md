
The keycap is defined in

keyboards/keychron/q1v1/ansi/keymaps/skizz/keymap.c

It changes the function keys to be F keys and requires the Fn key for the macOS behaviors.


```
qmk config user.keyboard=keychron/q1v1/ansi

qmk compile -kb keychron/q1v1/ansi -km skizz

qmk flash -kb keychron/q1v1/ansi -km skizz
```

## Full process:

Lever off the space bar, press the reset button for 3 seconds, 
then plug in the power cord.

The keyboard should be in DFU mode:

```
(base) [  4:02PM ]  [ chris@Terpsichore:~/qmk_firmware(master✗) ]
 $ qmk console
Looking for devices...
Ψ Bootloader Connected: atmel-dfu: ATmega32U4
^C%                                                                             (base) [  4:02PM ]  [ chris@Terpsichore:~/qmk_firmware(master✗) ]
 $ qmk flash -kb keychron/q1v1/ansi -km skizz
Ψ Compiling keymap with gmake -r -R -f builddefs/build_keyboard.mk -s flash KEYBOARD=keychron/q1v1/ansi KEYMAP=skizz KEYBOARD_FILESAFE=keychron_q1v1_ansi TARGET=keychron_q1v1_ansi_skizz VERBOSE=false COLOR=true SILENT=false QMK_BIN="qmk"


avr-gcc (Homebrew AVR GCC 8.5.0_2) 8.5.0
Copyright (C) 2018 Free Software Foundation, Inc.
This is free software; see the source for copying conditions.  There is NO
warranty; not even for MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.

Size before:
   text	   data	    bss	    dec	    hex	filename
      0	  23404	      0	  23404	   5b6c	keychron_q1v1_ansi_skizz.hex

Copying keychron_q1v1_ansi_skizz.hex to qmk_firmware folder                                         [OK]
Checking file size of keychron_q1v1_ansi_skizz.hex                                                  [OK]
 * The firmware size is fine - 23404/28672 (81%, 5268 bytes free)
Flashing for bootloader: atmel-dfu
Bootloader Version: 0x00 (0)
Checking memory from 0x0 to 0x6FFF...  Not blank at 0x1.
Erasing flash...  Success
Checking memory from 0x0 to 0x6FFF...  Empty.
Checking memory from 0x0 to 0x5B7F...  Empty.
0%                            100%  Programming 0x5B80 bytes...
[>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>]  Success
0%                            100%  Reading 0x7000 bytes...
[>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>]  Success
Validating...  Success
0x5B80 bytes written into 0x7000 bytes memory (81.70%).
```
