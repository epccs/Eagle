# Status

```
        ^3  Done: 
            WIP: 
            Todo: Design, Layout (#=done), BOM, Review*, Order Boards, Assembly, Testing, Evaluation.
            *during review the Design may change without changing the revision.
            long term goal is to switch to the new AVR DA's
            after devl and testing serial and I2C lib's for the DA's start this update
            change m324pb to AVR128DA48 
            change m328pb to AVR128DA32

        ^2  Done: Design, Layout (#=done), BOM,
            WIP: Review*, 
            Todo: Order Boards, Assembly, Testing, Evaluation.
            *during review the Design may change without changing the revision.
            # Q105 and Q118 need to go into cut off (or hi-z) when the MOSFET gate is low.
            # Add note on schem near *manager* ISP port "remove alternat power befor programing with ISP"
            # Add test points on I2C0 nodes.
            # Shutdown switch resistor needs moved so manager can overide switch while host is doing power UP.
            This version may not be ordered and built, but the layout will be done.

        ^1  Done: Design, Layout (#=done), BOM, Review*, Order Boards, Assembly,
            WIP: Testing,
            Todo: Evaluation.
            *during review the Design may change without changing the revision.
            # add gap between RJ45 headers
            # Power Protection
            # Alternat power diode replaced with a P-CH MOSFET
            # HOST_nCTS: on manager should move from PC0 to PD2
            # keep I2C like ^0: TWI0 goes to the manager as I2C master, the other port TWI1 can be slave or master I2C.
            # connect R1 (ALT_V divider to ADC4) directly to ALT input
            # add second K38 under Q9 with its gate controled from ADC4 voltage, so 5..15V is needed to turn on ALT power.
            # move MGR_STATUS LED to MGR_SCK.
            # ALT_EN, PIPWR_EN: can go to the manager PB3, PB1
            # connect PIPWR_EN to PB1 on bus manager
            # connect ALT_EN to PB3 (MOSI) on bus manager (and do not ICSP program the manager with alt power applied). 
            # ALT_I, ALT_V, PWR_I, PWR_V: can go to the manager ADC 0, 1, 6,7
            # connect ADC4..ADC7 to test points
            # connect PB3 and PB1 to test points
            # change pin numbers so PA0 (with ADC0) is pin 0 for both digital and analog functions
```