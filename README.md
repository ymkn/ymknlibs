# ymknlib KiCAD library

KiCAD symbol and footprint libraries for my keyboard designs.

## Collections

### MCU

#### ymknlib_Waveshare_RP2040-Zero

For RP2040-Zero and RP2040-Tiny boards by [Waveshare](https://www.waveshare.com/). Some libs are created based on [crides/kleeb](https://github.com/crides/kleeb).

##### Symbols

|Name|Description|
|---|---|
|Waveshare_RP2040-Zero|for Zero and Tiny. Pad pins (GPIO17-25 and GND) are NOT included.|

##### Footprints

|Name|Description|
|---|---|
|Waveshare_RP2040-Tiny-DB|Mounting holes for Tiny's adapter board|
|Waveshare_RP2040-Zero_SMD|Larger pads for easier soldering. Compatible with Zero and Tiny's mainboard|
|Waveshare_RP2040-Zero_SMD_CO|with cutout ver.|
|Waveshare_RP2040-Zero_THT|Through-hole pads for Zero and Tiny's mainboard|
|Waveshare_RP2040-Zero_THT_CO|with cutuot ver.|

### Switch

#### ymknlib_Switch_ChocV2

Footprints for Kailh Choc V2 switches. Supports the 5-pin type (known for Lofree Flow. Does not support the earlier 6-pin type)

##### Footprints

|Name|Description|
|---|---|
|Plate_MP_Choc_v2_1u|Switch plate cutout (14.0 × 14.0 mm, R0.5 corners) with decorative copper on both sides|
|STAB_choc_2u_Plate|for stabilizers on switchplate|
|STAB_choc_2u|for stablizers on PCB |
|SW_choc_v2_1.5u|for 1.5u keyswitches on PCB|
|SW_choc_v2_1.25u|for 1.25u keyswitches on PCB|
|SW_choc_v2_1.75u|for 1.75u keyswitches on PCB|
|SW_choc_v2_1u|for 1u keyswitches on PCB|

`Plate_MP_Choc_v2_1u` uses a 14.0 × 14.0 mm cutout (previously 14.2 × 14.0 mm). The decorative copper on `F.Cu` and `B.Cu` is 1.0 mm wide and set back 0.3 mm from the cutout edge, including the rounded corners. Matching 1.1 mm wide openings on `F.Mask` and `B.Mask` expose the copper with a 0.05 mm margin on each side. These dimensions apply to both the standard and 17 mm pitch libraries. Fit depends on the switch model, plate thickness, and manufacturing tolerances; check physical fit before production.

#### ymknlib_Switch_ChocV2_17mm

17 mm pitch variants of all seven footprints in `ymknlib_Switch_ChocV2`, with the same footprint names. Compared with the standard library, only the positioning outlines differ, using 1u = 17 mm:

|Key size|Positioning outline (width × height)|
|---|---|
|1u|17 × 17 mm|
|1.25u|21.25 × 17 mm|
|1.5u|25.5 × 17 mm|
|1.75u|29.75 × 17 mm|
|2u|34 × 17 mm|

The outlines retain their original layers (`Dwgs.User` / User.Drawings for `Plate_MP_Choc_v2_1u`, `Eco1.User` / User.Eco1 for the others). Pads, holes, cutouts, decorative copper, and stabilizer spacing match the standard library. These outlines are positioning guides, not a guarantee of switch or keycap clearance at 17 mm pitch. The switch socket pads extend beyond the 1u outline, so allow additional clearance near board and enclosure edges.

The library is registered in this project's `fp-lib-table`. To use it in another project, add `Switch/ymknlib_Switch_ChocV2_17mm.pretty` to that project's footprint library table or to the global table. Already placed footprints must be updated from the library to receive these changes.

#### ymknlib_Switch_MX_GLP3

Footprints for Gateron Low-Profile 3.0 switches (containing "MX" in their names are compatible with MX switches). 

##### Footprints

|Name|Description|
|---|---|
|PlateHole_PlateStab_GLP3_2.25u|Mounting holes for Gateron Low Profile Plate Mounted Stabilizer with a 2.25u placeholder for switch plates|
|PlateHole_PlateStab_GLP3_2.75u|for 2.75u|
|PlateHole_PlateStab_GLP3_2u|for 2.0u|
|PlateHole_PlateStab_MX_2u|Mounting holes for MX Compatible PCB Mounted Stabilizer with a 2.0u placeholder for switch plates|
|PlateHole_SW_LP_1u|Mounting holes for Low Profile switch plates (1u). Renamed from `PlateHole_SW_MX_GLP3_1u`|
|PlateHole_SW_MX_1u|Mounting holes for MX-compatible switch plates (1u)|
|PlateStab_GLP3_2.25u|Through holes for Gateron Low Profile Plate Mounted Stabilizer with a 2.25u placeholder for PCB|
|PlateStab_GLP3_2.75u|for 2.75u|
|PlateStab_GLP3_2u|for 2.0u|
|PlateStab_GLP3_ISOEnter|for ISOEnter|
|SW_MX_GLP3_1.5u|Footprint for Gateron Low Profile 3.0 switches with a 1.5u placeholder for PCB|
|SW_MX_GLP3_1.25u|for 1.25u|
|SW_MX_GLP3_1.75u|for 1.75u|
|SW_MX_GLP3_1u|for 1u|

### PCBFoam

#### ymknlibs_PCBFoam

Footprints for laser cutting PCB foams. Edge.Cuts layer shapes for protecting PCB components.

##### Footprints

|Name|Description|
|---|---|
|PCBFoam_ChocV2_Socket|Hole for Choc V2 switch socket (Kailh CPG135001S01)|
|PCBFoam_D_SOD-123|Hole for SOD-123 diode|

### SwitchFoam

#### ymknlib_SwitchFoam_MX

Footprints for laser cutting switch foams. Designed for MX switches.

##### Footprints

|Name|Description|
|---|---|
|SwitchFoam_MX_1.0u|Hole of 1.0u MX-compatible key switches.|

### SwitchPad

#### ymknlib_SwitchPad_MX

Footprints for laser cutting switch pads. Designed for MX switches.

##### Footprints

|Name|Description|
|---|---|
|SwitchPad_MountingHole|Mounting holes used in GH60-compatible PCBs|
|SwitchPad_MX_1.0u|Holes for the three feets of 1.0u MX-compatible key switches. Does NOT include holes for contact pins|
|SwitchPad_MX_1.5u|for 1.5u|
|SwitchPad_MX_1.25u|for 1.25u|
|SwitchPad_MX_1.75u|for 1.75u|
|SwitchPad_Stab_MX_2.0u|Holes for 2.0u MX-compatible PCB-mounting keyboard stabilizer|
|SwitchPad_Stab_MX_2.25u|for 2.25u|
|SwitchPad_Stab_MX_2.75u|for 2.75u|
|SwitchPad_Stab_MX_3.0u|for 3.0u|
|SwitchPad_Stab_MX_3.0u|for 7.0u|
|SwitchPad_Stab_MX_ISO|for ISOEnter|

### Various

#### ymknlib_Various

Various footprints for keyboard designs.

##### Footprints

|Name|Description|
|---|---|
|D_SOD-123|Diode, SOD-123 package|
|MountingHole_M2_TrayMount|M2 mounting hole with plated through-hole for tray mount keyboards (PCB)|
|MountingHole_M2_TrayMount_NPTH|M2 mounting hole with non-plated through-hole for tray mount keyboards (PCB)|
|PlateHole_M2_TrayMount_NPTH|M2 mounting hole with non-plated through-hole for tray mount keyboards (switch plates)|

## License

This project is licensed under the MIT License, see the [LICENSE file](LICENSE) for details.
