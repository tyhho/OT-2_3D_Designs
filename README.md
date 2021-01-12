# OT-2 3D Designs

The OT-2 is an affordable and extremely versatile robotic liquid handler. Unfortunately we cannot sustain by using the official tips and racks so we created in-house 3D designs as low-end (but functional) substitutes. By no means these objects emulate the official ones in performance, but they do the job. Personally I cannot see why labs should be deterred from getting the OT-2 just because the racks / tips are relatively more expensive, and these objects were shared here with the hope that it will encourage more labs to embrace the robot.

Every file comes in two formats - the original design that was drawn using DesignSpark Mechanical (.rsdoc) and the output file (.stl) which should be ready for print without any tweaks. Verified objects were tested on the OT-2 owned by Prof. Chris French's group.

I have uploaded [a short demo video](https://youtu.be/O2pek04nZW8) that shows the tip Rack (old version) and Tube Rack in action.

## 300 uL TipRackExterior 4.0 for TipOne tips

**Before you read on: Official Opentrons tips and tip racks are superior in reliability. These custom tip racks will suffice for short protocols if you supervise the robot and intervene before things go horribly wrong. It is understood that many seek to cut costs by using 3rd-party tips, but even a single missed tip pick up could ruin an entire experiment and waste batch reagents. OT-2 users who wish to the overwork the robot without supervising it should stick with official Opentrons tips and tip racks.**  

<!--
-->
<img src="https://github.com/tyhho/OT-2_3D_Designs/blob/master/images/300uL_TipRackExterior_v4_1.jpg" alt="TipRackExterior v4.0 With Tips" width="600">  

A support rack that permits OT-2 to use 10 µL (S1111-3700) and 300 µL (S1110-9700) TipOne tips. This version was designed to mimick the official TipOne tip boxes and has a reverse-engineered snap lock mechanism to hold the top rack in place. Please watch the [demo video](https://youtu.be/NoVUIB_1YB4) for its performance and loading instructions.

Opentrons has a [3D design of TipOne tip box adaptor](https://github.com/Opentrons/otone_hardware/blob/master/models/TipOne%20tip%20rack.stl). We tried printing and using one but the performance was unsatisfactory for us in using the P50M GEN1. This led us to develop our in-house solutions.

Pipette-tip sets:
|Pipette |Tip    |Performance|Custom labware file|
|-------------------|------------------------|-------------|------|
|P10S (GEN1)|10 µL tips (S1111-3700)|Reliable. See [demo video](https://youtu.be/NoVUIB_1YB4)|tipone_96_diytiprack_10ul.json|
|P10M (GEN1)|10 µL tips (S1111-3700)|**Picked up tips do not form air-tight vacuum seals. Official Opentrons/GEB 10 µL tips are indispensible.**|NA|
|P50M (GEN1)|200 µL tips (S1111-1700)|Tips do not fit |NA|
|P50M (GEN1)|300 µL tips (S1110-9700)|Reliable except 1st column. See [demo video](https://youtu.be/NoVUIB_1YB4)| tipone_96_diytiprack_300ul.json|
|P300S (GEN1)|300 µL tips (S1110-9700)|Reliable | tipone_96_diytiprack_300ul.json|

Recommended print setting: 20% infill, Triangle, Brim

Currently, the materials for printing is PLA. Switching to PP (Polypropylene) or Nylon may yield sterilizable tip racks through autoclave, but I do not have the material to test that.

## Reverse-engineered 4-in-1 tube rack set

<img src="https://github.com/tyhho/OT-2_3D_Designs/blob/master/images/4-in-1_rack_1.jpg" alt="50 mL and 1.5 mL Tube Rack" width="600">  

Relevant items:
|Design         |        Status |
|-------------------|------------------------|
|OT-2 Rack_Base 4.0|Verified|
|OT-2 1.5 mL Rack_TopPlate 2.0|Verified|
|OT-2 0.75 mL Rack_TopPlate 2.0|To be verified, but holds tubes properly|
|OT-2 15 & 50 mL Rack_TopPlate 1.2|Verified|
|OT-2 15 mL Rack_TopPlate 1.0|Design only, but dimensions follow that of 15 & 50 mL and so should work|
|OT-2 50 mL Rack_TopPlate 1.0|Verified|

These designs are low-end substitutes reverse-engineered from the official 4-in-1 tube rack set.
Similar to the official design the objects are separated into the Top Plate and the Tube Rack Stand (which I named as Base for convenience) and the Base can be used interchangeably with different Top Plates.
To assemble each rack, 4 x M4 x 25 mm Machine Screws and Nuts (we used FA141P) are needed to lock the Top Plate and the Base together.

All the top plates can use their corresponding official labware API names, e.g. "OT-2 50 mL Rack_TopPlate 1.0" can use "opentrons_24_tuberack_eppendorf_1.5ml_safelock_snapcap" and "opentrons_6_tuberack_falcon_50ml_conical". The xy coordinates are usually close enough, but you must **calibrate the z coordinate prior to your first protocol run**.  
The exception is OT-2 0.75 mL Rack_TopPlate 2.0, which requires the custom labware file eppendorf_24_tuberack_500ul.json.

For the top plates that hold 15 mL and/or 50 mL tubes, the dimensions provided by Opentrons were way too tight for our tubes. Note that different brands have subtle differences in diameter sizes for 15 mL and 50 mL tubes. It might be necessary to adjust the "well" diameter for a proper fit.

Recommended print settings:  
Top Plate: 10 - 20% infill, Triangle, Brim  
Base: 20 % infill, Triangle, Brim

**The holes for the M4 screws may have to be drilled bigger to allow the screws to pass through without resistance. The frequency of such needs depends on the positional accuracy and the robustness of the 3D printer you are using. For us it is common that 3 out of 4 holes need such drilling.**

## Custom labware .json files for existing labwares

<img src="https://github.com/tyhho/OT-2_3D_Designs/blob/master/images/GBO_one_well_agar_plate_1.jpg" alt="Agar plate" width="300"><img src="https://github.com/tyhho/OT-2_3D_Designs/blob/master/images/PCR_plate_on_WS.jpg" alt="PCR Plate on WS" width="300"><img src="https://github.com/tyhho/OT-2_3D_Designs/blob/master/images/PCR_stripe_on_WS.jpg" alt="PCR stripe on WS" width="300">  

Relevant files:
|File         |Labware Object(s)|Remarks|
|-------------------|------------------------|------------------------|
|gbocellstaronewellagarplate_96_wellplate_10ul.json|Greiner Bio-One CELLSTAR® OneWell Plate™ (670180)|Filled with 15 mL LB agar for colony spotting|
|starlabpcrplateonws_96_wellplate_350ul.json|StarLab 96-well PCR plate (E1403-0100) on StarLab PCR Workstation (E2396-1641)|Align Workstation to top left of labware slot on deck|
|starlabpcrwsstrips_96_wellplate_200ul.json|StarLab 0.2 ml 8-Strip PCR Tubes (I1402-3500) on StarLab PCR Workstation (E2396-1641)|Align Workstation to top left of labware slot on deck|

**The API name is the file name with the suffix ".json" removed.** 

## Ice Block

<img src="https://github.com/tyhho/OT-2_3D_Designs/blob/master/images/DIY_iceblock_1.jpg" alt="Ice Block" width="600">  

A horrendously low-end substitute for the official Temperature Module, designed to keep enzymes / reactions cold during a run. This object holds a metallic block (N2400-4021, N2400-4022, N2400-4023, or N2400-4024) that is compatible with the StarLab Mini Dry Bath (N2400-4021).  

Usage: insert the metallic block into the middle slot of the object, fill the rest of the space with water / plastic-compatible coolants, and then freeze it at -20 °C overnight before use. Once taken out, the metallic block will remain at around -10 °C for the first 30 mins and at around 0 °C within for another 1 hour.  

This object has an associated JSON file, written by Felipe Aguilera Millacura, for object creation through the OT-2 API. The file is available through a [repository](https://github.com/chris-french-lab/OT2_Objects) from the French lab.  

Status: Fits metallic block and slots on OT-2 well but not functionally verified. Concerns with possible water leak through PLA plastics and potential increase in object fragility due to repeated freeze-thaw cycles need to be empirically tested.

## Questions/Issues/Suggestions
Please contact me through email since I do not actively or passively monitor my Github. Thank you.

## Acknowledgement
I thank Dr. Logan Mackay (Mass Spectrometry Facility, University of Edinburgh) for providing access to a 3D printer, [Felipe A. Millacura](https://github.com/millacurafa) and the French group for access to the robot and for inducting me into the OT-2 community, and the Wang group for purchasing the additional OT-2 pipettes.  

## License
Licensed under the TAPR Open Hardware License (www.tapr.org/OHL)