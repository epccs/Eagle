# Status

```
        ^5  Done: Design, Layout, BOM, Review*, Order Boards, Assembly, 
            WIP: Testing,
            Todo: Evaluation.
            *during review the Design may change without changing the revision.
            # remove arduino headers
            # add header with 40 pin R-Pi pinout
            # swap MCU to ATmega328pb
            # swap ftdi with a dual UART port version Silabs CP2105
            # connect serial0 to RX/TX/nRTS/nCTS on R-Pi header
            # connect sierial1 to MCU's serial0
            # connect MCU's I2C0 to I2C on R-Pi header
            # connect MCU's I2C1 to the ID port on R-Pi header
            # connect MCU's SPI to SPI on R-Pi header
            # power with 3V3 from LDO and power the LDO from the USB header through the P-CH soft start. 

        ^4 Done: Design, Layout, BOM, Review*, Order Boards, Assembly, Testing, Evaluation.
           WIP: 
           Todo:  
           *during review the Design may change without changing the revision.
           location: 2017-3-17 Test Bench /w an OSEPP Uno R3

        ^3 location: 2016-10-1 Test Bench /w an OSEPP Uno R3, used to connect by CAT5 to outside parts and to bench parts as needed.
                     2017-1-5 ICP1 hacked open.
                     2017-3-17 scraped
```

This will give a desktop a way to interface to the RPUbus controlers (though I2C and SPI will be very different).