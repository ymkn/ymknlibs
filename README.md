# ymknlib KiCAD library

KiCAD symbol and footprint libraries for my keyboard designs.


### USB-C connector copy

`ymknlib_Various:USB_C_Receptacle_HRO_TYPE-C-31-M-12` is a copy of KiCad's
stock HRO footprint with the `USB_C_Receptacle_GCT_USB4105-xx-A_16P_TopMnt_Horizontal`
3D model assigned, because KiCad ships no model for the HRO part. The pads and
outline are unchanged; only the model reference and descriptive text differ.
The substitute was used in a user's CAD inspection; physical HRO/GCT interchangeability
has not been established. This copied footprint remains under KiCad's CC-BY-SA-4.0
library license with its electronic-design exception; see `licenses/NOTICE-KiCad.md`.

## Bundled 3D models and model paths

The Choc V2 and MX/GLP3 switch footprints reference socket models stored in
`Switch/3dmodels/` using `${KIPRJMOD}/../lib/external/ymknlibs/Switch/3dmodels/...`.
They resolve in any project that keeps this repository at
`KiCAD/lib/external/ymknlibs`, which is how generator projects pin it. In other
layouts the 3D reference stays unresolved; the 2D footprint is unaffected.

- `HS_CPG135001S30_Choc.step`, `HS_CPG151101S11_MX.step` — from
  [ebastler/marbastlib](https://github.com/ebastler/marbastlib) commit
  `6b0a9a73f579e377816d60b58eac2b3252de7868`, licensed CERN-OHL-P 2.0
  (see `licenses/marbastlib-LICENSE.txt`). Notices are retained as required.
- `Various/3dmodels/DampingBall-Body.step` — user-provided simplified
  reference body (4.4 mm body diameter, 3.0 mm neck, 6.6 mm tall, origin on
  the bottom axis). The central through-hole is not modeled. The footprint
  places it with a -4.6 mm Z offset, which assumes a 1.6 mm board and the
  nominal 3 mm lower contact; adjust per design if those differ.
- Other footprints keep KiCad's stock model references (`Diode_SMD` etc.)
  using KiCad 10's `${KICAD10_3DMODEL_DIR}` and its shipped `.step` models.

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
|Plate_MP_Choc_v2_1u_NoCopper|Same switch plate cutout without decorative copper or solder mask openings|
|STAB_choc_2u_Plate|for stabilizers on switchplate|
|STAB_choc_2u|for stablizers on PCB |
|SW_choc_v2_1.5u|for 1.5u keyswitches on PCB|
|SW_choc_v2_1.25u|for 1.25u keyswitches on PCB|
|SW_choc_v2_1.75u|for 1.75u keyswitches on PCB|
|SW_choc_v2_1u|for 1u keyswitches on PCB|

The four `SW_choc_v2_*` switch footprints also have additive `_MXAligned` variants (for example, `SW_choc_v2_1u_MXAligned`). Compared with the original Choc V2 footprints, all socket pads, contact holes, socket outlines, and the 3D model are rotated 180 degrees about the switch center, and pad numbers 1 and 2 are exchanged. Viewed from `F.Cu` at footprint rotation 0 degrees, the socket is on the negative-Y side, pad 1 is on the right, and pad 2 is on the left, following the left/right numbering of `SW_MX_GLP3_*`. The center hole, pad sizes, drills, copper/mask/paste layers, and positioning outlines are unchanged. The existing footprints retain their original orientation and numbering.

These variants simplify exchanging footprints in a PCB design; they are not combined MX/Choc footprints and do not make the two sockets physically interchangeable on an already manufactured PCB. Contact-hole and solder-pad positions still differ from MX/GLP, so tracks must be adjusted and clearances rechecked. Keep the same footprint center, rotation, and board side when replacing an MX/GLP footprint with an `_MXAligned` Choc V2 footprint. Replacing an original Choc V2 footprint with this variant also moves the contacts and exchanges their numbers; review the pad-to-net mapping and reroute as needed. The Choc V2 plate and stabilizer footprints are unchanged.

`Plate_MP_Choc_v2_1u` uses a 14.0 × 14.0 mm cutout (previously 14.2 × 14.0 mm). The decorative copper on `F.Cu` and `B.Cu` is 0.8 mm wide and set back 0.5 mm from the cutout edge, including the rounded corners. Matching 0.9 mm wide openings on `F.Mask` and `B.Mask` expose the copper with a 0.05 mm margin on each side. These dimensions apply to both the standard and 17 mm pitch libraries. At 17 mm pitch, adjacent copper rings have a 0.4 mm gap; their mask openings have a 0.3 mm gap. Fit depends on the switch model, plate thickness, and manufacturing tolerances; check physical fit before production.

The 0.5 mm copper setback follows the conservative hole clearance guidance in JLCPCB's [PCB design recommendations](https://jlcpcb.com/blog/how-to-avoid-pitfalls-in-pcb-design). Their [rigid PCB manufacturing capabilities](https://jlcpcb.com/capabilities/pcb-capabilities) list a lower manufacturing minimum of 0.2 mm for routed edges and slots; the 0.5 mm value here is a design choice, not a universal manufacturing minimum. This project's minimum copper-to-edge clearance is set to 0.5 mm. When using these footprints in another project, set its copper-to-edge clearance to at least 0.5 mm as well; library footprints do not transfer project DRC settings.

#### ymknlib_Switch_ChocV2_17mm

17 mm pitch variants of all twelve footprints in `ymknlib_Switch_ChocV2`, including the four `_MXAligned` switch variants, with the same footprint names. Compared with the standard library, only the positioning outlines differ, using 1u = 17 mm:

|Key size|Positioning outline (width × height)|
|---|---|
|1u|17 × 17 mm|
|1.25u|21.25 × 17 mm|
|1.5u|25.5 × 17 mm|
|1.75u|29.75 × 17 mm|
|2u|34 × 17 mm|

The outlines retain their original layers (`Dwgs.User` / User.Drawings for `Plate_MP_Choc_v2_1u` and `Plate_MP_Choc_v2_1u_NoCopper`, `Eco1.User` / User.Eco1 for the others). Pads, holes, cutouts, decorative copper, and stabilizer spacing match the standard library. These outlines are positioning guides, not a guarantee of switch or keycap clearance at 17 mm pitch. The switch socket pads extend beyond the 1u outline, so allow additional clearance near board and enclosure edges.

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

`PlateHole_PlateStab_MX_2u` includes rectangular `F.Cu` copper-pour keepouts extending at least 0.5 mm beyond each cutout. The cutout dimensions are unchanged. These keepouts apply only to front copper pours, not rear copper, tracks, vias, or pads; enforce their edge clearance with board-level DRC settings.

#### ymknlib_Switch_MX_GLP3_17mm

17 mm pitch variants of all fourteen footprints in `ymknlib_Switch_MX_GLP3`, with the same footprint names. Compared with the standard library, only the positioning outlines on `Dwgs.User` / User.Drawings differ, using 1u = 17 mm:

|Key size|Positioning outline (width × height)|
|---|---|
|1u|17 × 17 mm|
|1.25u|21.25 × 17 mm|
|1.5u|25.5 × 17 mm|
|1.75u|29.75 × 17 mm|
|2u|34 × 17 mm|
|2.25u|38.25 × 17 mm|
|2.75u|46.75 × 17 mm|
|ISO Enter|25.5 × 34 mm overall L-shaped outline; 21.25 mm wide lower half|

Pads, holes, cutouts, copper-pour keepouts, courtyards, 3D models, and stabilizer spacing match the standard library. The ISO Enter outline retains its original origin and orientation; its 14 mm switch corner marks are unchanged. These outlines are positioning guides, not a guarantee of switch, keycap, or stabilizer clearance at 17 mm pitch. The switch socket pads and some stabilizer cutouts and keepouts extend beyond the positioning outlines, so check adjacent keys and allow additional clearance near board and enclosure edges.

The library is registered in this project's `fp-lib-table`. To use it in another project, add `Switch/ymknlib_Switch_MX_GLP3_17mm.pretty` to that project's footprint library table or to the global table. Already placed footprints are not automatically switched to this library.

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
|MountingHole_DampingBall_D3.2mm|Damping ball mounting hole: 3.2 mm NPTH, 4.4 mm body outline on User.Comments, and 4.9 mm courtyards on both sides|
|MountingHole_M2_TrayMount|M2 mounting hole with plated through-hole for tray mount keyboards (PCB)|
|MountingHole_M2_TrayMount_NPTH|M2 mounting hole with non-plated through-hole for tray mount keyboards (PCB)|
|PlateHole_M2_TrayMount_NPTH|M2 mounting hole with non-plated through-hole for tray mount keyboards (switch plates)|

`MountingHole_DampingBall_D3.2mm` uses the same 3.2 mm hole diameter as KiCad's standard `MountingHole_3.2mm_M3`. The supplied `DampingBall-Body.step` has a 3.0 mm neck diameter, a 1.6 mm neck height, and 4.4 mm diameters for both the upper and lower bodies. Their coincident physical outlines are represented by a single circle on `Cmts.User` (User.Comments). Both `F.CrtYd` and `B.CrtYd` have a 4.9 mm diameter circle, allowing a 0.25 mm radial margin around the body for front- and back-side courtyard overlap checks. These outlines are not board cutouts or copper keepouts.

## License

This project is licensed under the MIT License, see the [LICENSE file](LICENSE) for details.
