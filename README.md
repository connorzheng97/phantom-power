# What is this
This is a 3-AA-battery powered phantom power supply. It was intended for use with wireless microphone beltpacks to provide high quality 48V phantom power to large condenser microphones and enable them to be used wirelessly, or as a standalone unit. It's also suitable for DI boxes, small condenser microphones and anything requiring phantom power.

This is a complete design with schematic, PCB and enclosure. Files are production-ready, with BOM. Design of this project begun in 2019 and final test was done on December of 2021. Batch production was planned but hasn't been carried out, as newer wireless microphone beltpacks has begun to incorporate built-in phantom power circuits (although usually not at full 48V), and COVID has had a major impact on touring industry.

# The Specs
- Power Source: 3x AA Batteries, alkaline is recommended. Ni-Mh rechargeable can also be used.
- Power Output: IEC 61938 48V
- Phantom Resistor: 6.81K
- Current: up to 14mA at short-circuit
- Noise: < 100uVpp
- EMI: not tested

# The Design
## Overall Design
A simple power supply box with XLR-in (connects to device requiring phantom power), XLR-out (no DC bias, connect to audio input of next stage), a power switch and a battery voltage indicator. The switch is partly recessed to avoid accidental operation. The colors of the battery indicator are ice-blue and orange, which are color-blind friendly. On the side of the box are 2 ears where you can thread in a hook-and-loop nylon cable tie to form a loop and strap the box to wireless beltpack and microphone stand or other fixation points.

## Schematic and PCB
Schematic and PCB were done with KiCAD 5. A PDF version of the schematic is available for view under the `docs` folder.

Circuit consists of a simple boost converter with added 3-stage diode voltage multiplier, a high voltage LDO, and a 2-stage Darlington capacitance multiplier for lowest noise possible. Protection circuitry and battery voltage indication were also added. A P-MOS blocks reverse battery, followed by a PPTC resettable fuse and transient suppression.

PCB is a normal 1.6mm 2-layer PCB.

## Mechanical Design
Enclosure design was done with Solidworks 2018. STEP and STL files are also provided in the `mech` folder. The design is mostly complete, and should be injection-molding ready, with no draft angle in design file. 

The PCB is held down to the base part by boss from top part, which are held together by self-tapping screws. The holes in the bosses are through, which are also used to mount the battery holder. The front panel is held in place by groves on both large parts. The battery holder is an off-the-shelf one which can be bought on Taobao or AliExpress. XLR connectors are fixed to front panel with self-tapping screws.

# Make Your Own
You can fabricate the PCB and have it partly assembled by a PCB fab such as PCBWay(JDB PCB) or JLC-PCB. Solder only the common SMT parts at the fab, which I found to be the most cost-saving. A gerber file set is included in the `output` folder in the hardware design files. Other parts can be sourced from LCSC or another distributor. Hand soldering is mostly easy except the VSSOP LDO may be a little bit annoying. Alternative part number may be found in schematic.

Enclosure can be 3D-printed either at home or by a professional service. For FDM 3D-printing, remove small details that are not printable. Print top part upside down with support.

A BOM for assembling can be found under the `docs` folder. A interactive BOM for the pcb can be found in the `ibom` folder under the `docs` folder.

## Assembling
1. Push light pipe onto PCB
2. Mount front panel to XLR connectors with 4 ST2.9x8 screws
3. Solder XH2.54 pigtail to battery holder
4. Mount battery holder onto top part of box with 4 ST3x10 screws
5. Place PCB and front panel into base part
6. Plug in battery XH2.54 plug
7. Screw top and base part together with 4 ST3x12 screws
8. Thread in hook-and-loop nylon cable tie

# Use of This Repo
This repo is licensed under CERN-OHL-W v2. In addition, consider buying me a drink if you like this design. You can credit back to this repo or my personal website if you wish.

Copyright Ryan Zheng 2022. 

This source describes Open Hardware and is licensed under the CERN-OHLW v2 

You may redistribute and modify this documentation and make products using it under the terms of the CERN-OHL-W v2 (https:/cern.ch/cern-ohl). 

This documentation is distributed WITHOUT ANY EXPRESS OR IMPLIED WARRANTY, INCLUDING OF MERCHANTABILITY, SATISFACTORY QUALITY AND FITNESS FOR A PARTICULAR PURPOSE. 
Please see the CERN-OHL-W v2 for applicable conditions. 

As per CERN-OHL-W v2 section 4.1, should You produce hardware based on these sources, You must maintain the Source Location visible on the external case of the phantom power supply or other product you make using this documentation.
