# Status


```
        ^3  Done: 
            WIP: 
            Todo: Design, Layout, BOM, Review* (#= done), Order Boards, Assembly, Testing, Evaluation.
            *during review the Design may change without changing the revision.
            J9 J10 renumber to J8 J9
            TO_RPU_TX has two pullup (R19 and R104), remove R104. 
            Connect Manager Debug UART (MCU_IO_RX1 and MCU_IO_TX1) to test points.
            Add test point to 0V and PI3V3 for level shifting the debug uart test points.
            R104 is an extra pull-up on TO_RPU_TX; use it to pull-up FROM_RPU_TX instead.
            Rename PC2 and PC3 nodes MVIO_SDA0 and MVIO_SCL0 (used for R-Pi SMBus)
            Rename PF2 and PF3 nodes MGR_SDA1 and MGR_SCL1 (used between manager and applicaion)
            Rename PF4 and PF5 nodes MGR_SETAPP4_UART and MGR_SETAPP4_UPDI
            

        ^2  Done: Design, Layout, BOM, Review* (#= done), Order Boards, Assembly,
            WIP: Testing,
            Todo: Evaluation.
            *during review the Design may change without changing the revision.
            # LVT12R0100FER smd 1206 metal current sense element 0.01 Ohm 1W (e.g. 10A max)
            # change name on board to MacGyver
            # AVR128DB has two power domains, but its logistics is a mystery to me at this time.
            # Use 10k Ohm to discharge the UPDI mode controled with BCM24
            # Use 10k Ohm to discharge the UART mode controled with BCM23
            # Remove SPI between R-Pi and App MCU; it should be available (e.g., sdcard, psram...)
            # Rename DTR pair to OOB (Out Of Band).
            # Remove RTS/CTS, without a bootloader they will not be needed

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