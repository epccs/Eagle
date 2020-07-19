# Status


```
        ^1  Done: 
            WIP: Design,
            Todo: Layout, BOM, Review*, Order Boards, Assembly, Testing, Evaluation.
            *during review the Design may change without changing the revision.
            swap the m4809 for a AVR128DA28

            ^0  Done: Design, Layout, BOM, Review*, Order Boards,
            WIP: Assembly (will not do),
            Todo: Testing, Evaluation.
            *during review the Design may change without changing the revision.
            # use Python https://github.com/mraardvark/pyupdi to upload AVR from R-Pi Zero
```

Devl board to try pyupdi on an R-Pi with a AVR128DA28 target. 

Unified Program and Debug Interface ([UPDI]) for AVR provides programming and debugging through a 1-wire UART-based half-duplex interface using a single dedicated pin for data reception and transmission.

[UPDI]: https://microchipdeveloper.com/mplabx:avr-updi

hmm... if it is UART-based then...

https://github.com/mraardvark/pyupdi

```
                        Vcc                     Vcc
                        +-+                     +-+
                         |                       |
 +---------------------+ |                       | +--------------------+
 | Serial port         +-+                       +-+  AVR device        |
 |                     |      +----------+         |                    |
 |                  TX +------+   4k7    +---------+ UPDI               |
 |                     |      +----------+    |    |                    |
 |                     |                      |    |                    |
 |                  RX +----------------------+    |                    |
 |                     |                           |                    |
 |                     +--+                     +--+                    |
 +---------------------+  |                     |  +--------------------+
                         +-+                   +-+
                         GND                   GND
```

An IOFF buffer can turn the interface off when it is not used for programing and then we can use it as a normal serial interface to one of the target UARTS. 

```
piupdi [options] [[--] args]
-h, --help            show this help message and exit
-d, --device=<str>    Target device
-c, --comport=<str>   Com port to use (Windows: COMx | *nix: /dev/ttyX)
-b, --baudrate=<int>  Baud rate, default=115200
-f, --file=<str>      Intel HEX file: to program, save or verification 
-u, --unlock          Perform a chip unlock
-e, --erase           Perform a chip erase (implied with --flash)
-p, --program         Program Intel HEX file to flash
-k, --check           Compare Intel HEX file with flash content
-s, --save            Save flash to a Intel HEX file
-u, --fuses=<str>     Fuse to set (syntax: fuse_nr:0xvalue)
-r, --read=<str>      Direct read from memory [addr];[n]
-w, --write=<str>     Direct write to memory [addr];[dat0];[dat1];[dat2]...
-v, --verbose=<int>   Set verbose mode (SILENCE|UPDI|NVM|APP|LINK|PHY|SER): [0~6], default 0, suggest 2 for status information
-t, --test            Test UPDI device

# Write memory
piupdi -c /dev/ttyAMA0 -d tiny817 -v 2 -u -w 3f00;01;02;03;04;05
# Read memory
piupdi -c /dev/ttyAMA0 -d tiny817 -v 2 -u -r 3f00;5
# Erase Flash
piupdi -c /dev/ttyAMA0 -d tiny817 -v 2 -e
# Program
piupdi -c /dev/ttyAMA0 -d tiny817 -v 2 -f tiny817.hex    
# or if no other operation for file, default programming
piupdi -c /dev/ttyAMA0 -d tiny817 -v 2 -p -f tiny817.hex
# Verify Flash
piupdi -c /dev/ttyAMA0 -d tiny817 -v 2 -k -f tiny817.hex
# Save Flash content to tiny817.hex.out
piupdi -c /dev/ttyAMA0 -d tiny817 -v 2 -s -f tiny817.hex
```