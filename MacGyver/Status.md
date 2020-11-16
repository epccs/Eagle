# Status


```
        ^2  Done: 
            WIP: 
            Todo: Design, Layout, BOM, Review* (#= done), Order Boards, Assembly, Testing, Evaluation.
            *during review the Design may change without changing the revision.
            LVT12R0100FER smd 1206 metal current sense element 0.01 Ohm 1W (e.g. 10A max)
            AT30TSE758A eeprom/temperature-alert on i2c bus between mngr and app
            change name on board to MacGyver
            AVR128DB has two power domains, but the logistics is a mystery to me at this time.
            Add 10k Ohm to discharge the UPDI mode which is controled with BCM24
            Remove Q4 so UART mode can not get power from 3V3
            Use BCM23 to power UART mode
            Remove SPI between R-Pi and App MCU; it should be available (e.g., sdcard, psram...)
            Rename DTR pair to OOB (Out Of Band).

        ^1  Done: Design, Layout, BOM, Review* (#= done), Order Boards,
            WIP: Assembly, 
            Todo: Testing, Evaluation.
            *during review the Design may change without changing the revision.
            # swap the m4809 for a AVR128DA28
            # UART0 crossover connection to R-Pi
 
            ^0  Done: Design, Layout, BOM, Review*, Order Boards,
            WIP: Assembly (will not do),
            Todo: Testing, Evaluation.
            *during review the Design may change without changing the revision.
            note this was not tested, and an error has been found with serial.
            # use Python https://github.com/mraardvark/pyupdi to upload AVR from R-Pi Zero
```

This board allows a Raspberry Pi serial hardware port (or [adaptor] board) to interface with a multi-drop, including a local AVR128DA28. Programing is done through the serial interface when a target (e.g., the local AVR128DA28) is is set by the manager for UPDI mode (the preferred method for all new AVRs).

[adaptor]: https://github.com/epccs/RPUusb