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
|Plate_MP_Choc_v2_1u|for keyswitches on switchplate|
|STAB_choc_2u_Plate|for stabilizers on switchplate|
|STAB_choc_2u|for stablizers on PCB |
|SW_choc_v2_1.5u|for 1.5u keyswitches on PCB|
|SW_choc_v2_1.25u|for 1.25u keyswitches on PCB|
|SW_choc_v2_1.75u|for 1.75u keyswitches on PCB|
|SW_choc_v2_1u|for 1u keyswitches on PCB|

#### ymknlib_Switch_MX_GLP3

Footprints for Gateron Low-Profile 3.0 switches and Full-Profile MX switches. 

##### Footprints

|Name|Description|
|---|---|
|Plate_MP_MX_GLP3_1u|for keyswitches on switchplate|
|SW_MX_GLP3_1.5u|for 1.5u keyswitches on PCB|
|SW_MX_GLP3_1.25u|for 1.25u keyswitches on PCB|
|SW_MX_GLP3_1.75u|for 1.75u keyswitches on PCB|
|SW_MX_GLP3_1u|for 1u keyswitches on PCB|

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

## License

This project is licensed under the MIT License, see the [LICENSE file](LICENSE) for details.
