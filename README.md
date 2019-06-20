# OT-2 3D Designs

The OT-2 is an affordable and extremely versatile robotic liquid handler. Unfortunately we cannot sustain by using the official tips and racks so we created in-house 3D designs as low-end (but functional) substitutes. By no means these objects out-compete the official ones in performance, but they do the job. Personally I just cannot see why labs should be deterred from getting the OT-2 just because the racks / tips are relatively more expensive. 

Every file comes in two formats - the original design that was drawn using DesignSpark Mechanical (.rsdoc) and the output file (.stl) which should be ready for print without any tweaks. Verified objects were tested on the OT-2 owned by Prof. Chris French's group.

I have uploaded [a short demo video](https://youtu.be/5dVj4VwHN3Q) that shows the Tip Rack and Tube Rack in action.

### 200 uL TipRackExterior
A support base that permits OT-2 to use tips from TipOne more reliably. We tried copying the 3D design of TipOne tip box adaptor # 10uL  200uL  300uL suggested by Opentrons but the P50M had difficulty in picking up all the tips from a single column reliably.

This object was designed to work with TipOne 300 µL tips. It also works well with TipOne 200 µL or TipOne 10 µL tips albeit imperfect fit due to its design.

Status: Functionally verified
Recommended print setting: 40% infill, Brim, Cubic

### Substitutes for 4-in-1 tube rack set
Relevant items
- OT-2 Rack_Base 3.0
- OT-2 1.5 mL Rack_TopPlate 2.0 
- OT-2 0.75 mL Rack_TopPlate 2.0

These designs are low-end substitutes for the official 4-in-1 tube rack set. Similar to the official design the objects are separated into the Top Plate and the Tube Rack Stand (which I named as Base for convenience) and the Base can be used interchangeably with different Top Plates. To assemble each rack, 4 x M4 x 25 mm Machine Screws and Nuts (we used FA141P) are needed to lock the Top Plate and the Base together.

All the top plates used their corresponding labwares in the OT-2 API. The exception is OT-2 0.75 mL Rack_TopPlate 2.0, which requires a new labware object to be created since the height of the tube is different. We will post the Json file for creating the object when we have time.

Recommended print settings
Top Plate: 10 - 20% infill, Brim, Triangle
Base: 40% infill, Brim, Cubic

|Design         |        Status |
|-------------------|------------------------|
|OT-2 Rack_Base 3.0|Verified|
|OT-2 1.5 mL Rack_TopPlate 2.0|Verified|
|OT-2 0.75 mL Rack_TopPlate 2.0|To be verified, but holds tubes properly|

### Ice Block
A horrendously low-end substitute for the official Temperature Module, designed to keep enzymes / reactions cold during a run. This object holds a metallic block (N2400-4021, N2400-4022, N2400-4023, or N2400-4024) that is compatible with the StarLab Mini Dry Bath (N2400-4021). 

The envisioned usage is to insert the metallic block into the middle slot of the object, fill the rest of the space with water / plastic-compatible coolants, and then freeze it at -20 °C overnight before use.

Status: Fits metallic block and slots on OT-2 well but not functionally verified. Concerns with possible water leak through PLA plastics and potential increase in object fragility due to repeated freeze-thaw cycles need to be empirically tested.

### OT-2 50 mL FalconTubeRack 1.8
**Deprecated**

A prototype before Substitutes for 4-in-1 tube rack set were designed. This holds 6 x 50 mL Falcon tubes. Object was deprecated because of redundancy and the inability to see depth of pipette tip at eye level.

This object has an associated JSON file, written by Felipe Aguilera Millacura, for object creation through the OT-2 API. The file is available through a [repository](httpsgithub.comchris-french-labOT2_Objects) from the French lab.

Recommended print setting: 40% infill, Brim, Triangle

### Questions/Issues/Suggestions
Please contact me through email since I do not actively or passively monitor my Github. Thank you.