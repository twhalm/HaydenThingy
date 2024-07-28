# Readme
- I am not a pro so I am sure things are a bit messy
- This uses KiCad 8.x
- The initial production and assembly quote was through JLCPCB
## Overview
If you want to get started and just view things in KiCad:
- Clone the repo
- Download KiCad
- Open the haydenThingy project

There will be a lot of stuff in the folder but there are really only two things to look at: the HaydenThingy schematic and pcb.  You can view those by opening the Schematic editor and the PCB editor.

## Initial version of the board
The first version of the board just combines the connections of the original three boards onto one PCB.  The ESP-32 and the LTE board attach via headers and the RS-485 breakout board was just incorporated into the PCB.

The larger board is a pretty simple board, all of the components are one once side, it is a large rectangle, and there are M3 holes for mounting on each corner.

## Next Steps
- Probably the first thing to do with this board is to order a low-volume run as a prototype to ensure everything fits/works as intended.

### Easy improvements to make
These are obvious and easy things that could be changed.
- The positioning of all of the components can be changed to make things slightly more compact or better
- You can make it more compact by mouting components on both sides (you can probably mount the LTE and ESP-32 boards on the front and back)
- Mounting holes can be changed and more can be added.

### Medium improvements to make?
- Put the battery connector on the PCB if it makes things easier
- Get rid of the screw terminal and put downstream components on the board directly (jst connectors for sensors, etc)

### Hard improvements
- Incorporate the ESP-32 and USB-C directly into the PCB
- Do the same for the LTE Board

## How do?
### Very brief KiCad workflow
1. Create a schematic. The Schematic has all of the components on a drawing and represents the various connections. To make a schematic you add **SYMBOLS**, which are essentially generic representations of various components. Once you have symbols you add connections between the various symbols.  You can draw wires on a schematic, but usually you use labels to keep things clean.
2. Associate your symbols with **FOOTPRINTS** a footprint is literally the physical footprint your component has on the PCB.  It is the size, pad, locations, etc.  For example you could have a generic symbol for a resistor in your schematic but you specify the physical shape of the resistor using a footprint.  For items like resistors there are a standard set of symbols and footprints that KiCad has in its builtin library.
3. Once you have a schematic and footprints you can create a PCB by laying out the footprints and drawing traces.

### Specifics to this board
- It is not normal for things to connect via headers since EEs know what they are doing.  The ESP-32 board had a footprint available from sparkfun since it fits one of their standard board layouts, but the LTE one did not and I had to make one.

- The 
