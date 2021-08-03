# Voron 2.4 Electronics

![Image of Voron 2.4](http://vorondesign.com/images/voron2.4.jpg)

** Note: Also refer to https://github.com/VoronDesign/Voron-2/raw/Voron2.4/Docs/2.4_Assembly_Manual.pdf for more information. (Start on Page 118) **

Step 1: Preparing the board
- Remove the jumpers indicated in the red boxes.
- Add jumpers indicated in the green boxes.

![Image of BTT Octopus board](https://github.com/j3thewebdev/agrioprint/blob/main/PV300%20Build/AGR-PV300-Octopus-MCU-Wiring.pdf)

Step 2: Preparing the drivers and placing them onto the board
- Snip the correct pin from each driver with flesh cutters.
- Place TMC 2209's on each driver. Place them 4x3, 4 fins on the length of the driver, 3 fins on the width of the driver. This allows proper airflow for the direction of cooling fans placed.
![Image of TMC 2209]()
- Place drivers on the BTT Octopus from Motor 0-6. Orientation of placing the drivers is red to red and black to black. Make sure they are properly pressed down and flush with the board.
![Image of BTT Octopus drivers]()

Step 3: Prepare orientation of electronics and mount onto din rails.
![Image of din rail orientation]()

Step 4: Label each electronic with a sharpie/sticker
- 24V PSU, 5V PSU, SSR, Raspberry Pi 4, BTT Octopus.
- Example: pvX(X = #), pv1,pv2,etc.

Step 5: Plug in the USB to USB-C cable from Raspberry Pi4 to BTT Octopus
- Plug the USB into the Raspberry Pi 4 and wire it under the BTT Octopus and plug in the USB-C into the BTT Octopus.
![Image of plugging in the USB cable to each end]()

Step 6: Wire USB-C cable for 5V PSU
- Measure and cut 400mm of a USB-C cable with flesh cutters.
- Strip the wire with wire strippers. You will be left with 4 colors of wire, red, gray, blue, and white
- Cut off the blue and white wire.
- Measure 3mm of the gray and red wire and remove the silicone on the wire with your fingers nails.
- Solder a male spade connector on each wire. (Total of 2 spade connectors)
- Wire the red wire into +V and the grey wire into -V on the 5V PSU.
- Wire the USB-C under the BTT Octopus and plug it into the Raspberry Pi 4.

Step 7: Wire connectors into Mains inlet
- Measure and cut 2x40mm and 3x220mm 20 gauge red wire with flesh cutters.
- Strip each end of the wire about 3mm with wire strippers.
- Prepare the 2x40mm with 2 female spade connectors, 2 silicone covers for each wire. (Total of 4 female spade connectors and 4 silicone covers)
![Image of mains inlet wiring diagram]()
- Crimp one side of the wire with a female connector. Insert a silicone cover over the connector and insert another silicone cover backward over the wire so you can easily have the cover ready when crimping the other side.
- Crimp the other side with a female spade connector and slide the silicone cover over the connector.
- Repeat for 2nd wire but, have 10mm yellow shrink wrap on each end to indicate it is the N wire.
- Using pliers, insert the red wire into the L-L on the back of the mains inlet.
- Insert the red wire with green shrink tube into the N-N on the back of the mains inlet.
- Prepare the 3x220mm with 1 female spade connector, 1 male spade connector, 1 silicone covers for each wire. (Total of 3 female spade connectors, 3 female spade connectors, and 3 silicone covers)
- Crimp one side of the wire with a female connector. Insert a silicone cover over the connector and solder a male spade connector on the other side.
- Repeat for 2nd wire but, have 10mm green shrink wrap on each end of the wire to indicate it is the GND wire.
- Repeat for 3rd wire but, have 10mm yellow shrink wrap on each end of the wire to indicate it is the N wire.
- Measure and cut 160mm cable sleeves and put the 3x220mm wire through them.
- Using pliers, insert the red wire, female spade connector into the PSU-L on the back of the mains inlet.
- Insert the red wire with yellow shrink, female connector side into the PSU-N on the back of the mains inlet.
- Insert the red wire with green shrink, female connector side into the PSU-GND on the back of the mains inlet.

Step 8: Wire connectors for 24V PSU to 5V PSU
- Measure and cut 3x120mm 20 gauge red wire
![Image of 24V PSU to 5V PSU wiring diagram]()

Step 9: Wire connectors for BTT Octopus to 24V PSU
- Measure and cut 6x280mm 20 gauge wire. If you have a red and black 20 gauge wire, measure and cut 3x280mm for red and black. (Red = +, Black = -, red male spade connector = +, blue male spade connector = -)
- Strip each end of the wire about 3mm with wire strippers.
- Prepare the 3x220mm with 2 red male spade connectors. (Total of 6 red male spade connectors)
- Prepare the 3x220mm with 2 blue male spade connectors. (Total of 6 blue male spade connectors)
- Solder male spade connectors on each end for every wire.
- Measure and cut 240mm cable sleeve and put all of the wires through the cable sleeve.
![Image of BTT Octopus to 24V PSU wiring diagram]()
- Wire all the spade connectors from the BTT Octopus to 24V PSU.

Step 10: Wire connectors for BTT Octopus to SSR
- Measure and cut 2x300mm 20 gauge wire. If you have a red and black 20 gauge wire, measure and cut 1x300mm for red and black. (Red = +, Black = -, red male spade connector = +, blue male spade connector = -)
- Strip each end of the wire about 3mm with wire strippers.
- Prepare the 1x300mm with 1 red male spade connector. (Total of 2 red male spade connectors)
- Prepare the 1x300mm with 1 red male spade connector. (Total of 2 red male spade connectors)
- Solder male spade connectors on each end for every wire.
- Measure and cut 260mm cable sleeve and put all of the wires through the cable sleeve.
![Image of BTT Octopus to SSR wiring diagram]()
- Wire all the spade connectors from the BTT Octopus to SSR.

Step 10: Test Electronics
- Perform a tug/wiggle test on all of the wires to make sure they are tight in place. If not, tighten them.
- Connect the power cord into the mains inlet.
- Turn on the power switch
- Check lights for each electronic:
    - 24V PSU = Green
    - 5V PSU = Green
    - Pi = Green, Red
    - BTT Octopus = Green, Red, Red, Red
