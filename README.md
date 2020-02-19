# OT-2 3D Designs

The OT-2 is an affordable and extremely versatile robotic liquid handler. Unfortunately we cannot sustain by using the official tips and racks so we created in-house 3D designs as low-end (but functional) substitutes. By no means these objects out-compete the official ones in performance, but they do the job. Personally I cannot see why labs should be deterred from getting the OT-2 just because the racks / tips are relatively more expensive, and these objects were shared here with the hope that it will encourage more labs to embrace the robot.

Every file comes in two formats - the original design that was drawn using DesignSpark Mechanical (.rsdoc) and the output file (.stl) which should be ready for print without any tweaks. Verified objects were tested on the OT-2 owned by Prof. Chris French's group.

I have uploaded [a short demo video](https://youtu.be/5dVj4VwHN3Q) that shows the Tip Rack and Tube Rack in action.

### TipRackExterior

Relevant items:
|Design         |        Status |
|-------------------|------------------------|
|OT-2 10 uL TipRackExterior 2.0|To be verified|
|OT-2 200 uL TipRackExterior 2.0|To be verified|
|OT-2 300 uL TipRackExterior 2.2|Verified with GEN1 P300S|
|OT-2 300 uL TipRackExterior 3.0|To be verified, but design is improved upon 2.2 and should work flawlessly|

**Note: OT-2 P10 8-channel pipettes can pick up TipOne tips but do not form air-tight vacuum seals. Official Opentrons/GEB 10 µL tips are indispensible.**

Support bases that permit OT-2 to use tips from TipOne more reliably. 
Opentrons has a [3D design of TipOne tip box adaptor](https://github.com/Opentrons/otone_hardware/blob/master/models/TipOne%20tip%20rack.stl). We tried printing and using one but the performance was unsatisfactory. The P50M had difficulty in picking up all the tips from a single column reliably. This led us to develop our in-house solutions.

The labware tiprack-200uL and tiprack-10ul can be used together with these object.

It should be noted that if two different kinds of tips are used together (e.g. 20 µL  and 300 µL), separate labwares ("tiprack-10ul" **&** "tiprack-300uL-custom") must be employed in the API, because calibration data of the two objects need to be stored separately for proper tip pick up.

The labware objects "tiprack-200uL" and "tiprack-10ul" at the moment are still available. However, customized labware could be installed via the scripts below.
The current API does not contain the function of offset and therefore users must first perform a dummy run to properly install these new labwares into the machine.
During this dummy run, the custom tip rack must be not placed in slots 1, 4, 7, 10 or else the robot arm will move beyond its properly functioning x-range.

```python
tip_rack_name = 'tiprack-300ul-custom'
if tip_rack_name not in labware.list():
    custom_plate = labware.create(
        tip_rack_name,                    # name of you labware
        grid=(12, 8),                    # specify amount of (columns, rows)
        spacing=(9, 9),               # distances (mm) between each (column, row)
        diameter=3,                     # diameter (mm) of each well on the plate
        depth=10,                       # depth (mm) of each well on the plate
        volume=10
        )
tip_rack_name = 'tiprack-200ul-custom'
if tip_rack_name not in labware.list():
    custom_plate = labware.create(
        tip_rack_name,                    # name of you labware
        grid=(12, 8),                    # specify amount of (columns, rows)
        spacing=(9, 9),               # distances (mm) between each (column, row)
        diameter=3,                     # diameter (mm) of each well on the plate
        depth=10,                       # depth (mm) of each well on the plate
        volume=10
        )
tip_rack_name = 'tiprack-10ul-custom'
if tip_rack_name not in labware.list():
    custom_plate = labware.create(
        tip_rack_name,                    # name of you labware
        grid=(12, 8),                    # specify amount of (columns, rows)
        spacing=(9, 9),               # distances (mm) between each (column, row)
        diameter=3,                     # diameter (mm) of each well on the plate
        depth=10,                       # depth (mm) of each well on the plate
        volume=10
        )
```

Recommended print setting: 40% infill, Cubic, Brim

### Reverse-engineered 4-in-1 tube rack set

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

All the top plates used their corresponding labwares in the OT-2 API.
 The exception is OT-2 0.75 mL Rack_TopPlate 2.0, which requires a new labware object to be created since the height of the tube is different.
 We will post the Json file for creating the object when we have time.

For the top plates that hold 15 mL and/or 50 mL tubes, I noticed that the dimensions provided by Opentrons were way too tight for our tubes.
 This is likely due to subtle differences between brands. It might be necessary to adjust the "well" diameter for a proper fit.

Recommended print settings

Top Plate: 10 - 20% infill, Triangle, Brim

Base: 40% infill, Cubic, Brim

**The holes for the M4 screws may have to be drilled bigger to allow the screws to pass through without resistance. The frequency of such needs depends on the positional accuracy and the robustness of the 3D printer you are using. For us it is common that 3 out of 4 holes need such drilling.**

### Ice Block
A horrendously low-end substitute for the official Temperature Module, designed to keep enzymes / reactions cold during a run. This object holds a metallic block (N2400-4021, N2400-4022, N2400-4023, or N2400-4024) that is compatible with the StarLab Mini Dry Bath (N2400-4021). 

The envisioned usage is to insert the metallic block into the middle slot of the object, fill the rest of the space with water / plastic-compatible coolants, and then freeze it at -20 °C overnight before use.
This object has an associated JSON file, written by Felipe Aguilera Millacura, for object creation through the OT-2 API. The file is available through a [repository](https://github.com/chris-french-lab/OT2_Objects) from the French lab.

Status: Fits metallic block and slots on OT-2 well but not functionally verified. Concerns with possible water leak through PLA plastics and potential increase in object fragility due to repeated freeze-thaw cycles need to be empirically tested.

### OT-2 50 mL FalconTubeRack 1.8
**Deprecated**

A prototype before Substitutes for 4-in-1 tube rack set were designed. This holds 6 x 50 mL Falcon tubes. Object was deprecated because of redundancy and the inability to see depth of pipette tip at eye level.

Recommended print setting: 40% infill, Triangle, Brim

### Questions/Issues/Suggestions
Please contact me through email since I do not actively or passively monitor my Github. Thank you.
