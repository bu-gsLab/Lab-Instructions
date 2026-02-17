# TFPX-102 Spacer Installation

`Introduction Placeholder`

<summary>General Comments</summary>

  - [ ] Add pictures of all required materials

</details>

## References

  - Purdue spacer installation SOP: https://github.com/bu-etl/Lab-Instructions/blob/main/SOPs/TFPX-102-materials/TFPX%20Spacer%20SOP.pdf

## Required Materials

- Glued module
- Spacer
- Gluing materials
    - Glue
    - Mixing nozzle
    - Stencil
    - Glue spreader (e.g. plastic card)

|Glue|Mixing nozzle|Stencil|Glue spreader (e.g. plastic card)|
|-|-|-|-|
|![glue_gun](./TFPX-102-materials/images/glue_gun.jpg)|![mixing_nozzle](./TFPX-102-materials/images/mixing_nozzle.jpg)|![spacer_stencil](./TFPX-102-materials/images/spacer_stencil.jpg)|![glue_spreader](./TFPX-102-materials/images/glue_spreader.jpg)|

## Procedure

### Step 0: Calibrate gantry

You should make sure that the relevant calibrations for this procedure have already been done. If you are unsure, you should ask an advisor or you can do a dry run of the script and see if the spacer gets placed where you expect it to. For a dry run, you should use a bare HDI in place of a glued module and you should not actually use any glue (hence 'dry') in step 2.

In the event the calibrations need to be done or redone, you should follow the instructions in [this calibration SOP](./TFPX-102-materials/TFPX%20Spacer%20SOP.pdf) made by the team at Purdue (linked above as well). Particularly, you should make sure the SSCO (Spacer Sucker Camera Offset) vector is calibrated. This gives the displacement vector between the camera focal point and the center vacuum hole in the spacer sucker tool. Additionally, you should check that our site config file contains the correct values for each variable that the document lists out. Note that those values in the document are particular for Purdue, and that ours will be different, so do not just copy them over. The site config file containing the all the variables with site-specific values can be found at this path: `./gantry-config-bu/Config/TFPX/CROC1x2_Site_Config.txt`. If you need to measure any new values (e.g. the SSCO vector or the pin location of one of the chucks), you should put the new value in this file and save it. The format for the variable definitions can be seen in the below examples:

```
focus_1x2_hdi_launch: 77.382407
small_ssco: {0.680517,105.374218,-5.563789}
```

Note that you CANNOT put a space before or after commas for vectors in gScript.


### Step 1: Stage parts

Place the module carrier on which the glued module is screwed in onto the desired chuck. Make sure the screws are on the right side of the chuck. 
1. Next, place the brass fixture with the pegs in the top left and bottom right corners on the HDI launch chuck. Place the spacer kapton tape side down in the desired slot (0, 1, 2, 3).

|Step 1|
|-|
|![Step 1](./TFPX-102-materials/images/spacer_step1.jpg)|

2. Then, place the stencil over the spacer, ensuring the orientation of the stencil is correct (horizontal line on top and larger vertical line on right). Put a mixing nozzle on the glue gun and deposit a line of glue below only the spacer you wish to glue. Do not put glue below empty holes. Then, slowly spread the glue upwards with the glue spreader.

|Step 2|
|-|
|![Step 2](./TFPX-102-materials/images/spacer_step2.jpg)|

3. Lift the stencil off the spacer, being careful that the spacer is not lifted with the stencil. If it is, carefully place it back in the desired location. Then, place the other brass fixture over the spacer, ensuring the orientation is correct (holes should be oriented the same as the stencil).

|Step 3|
|-|
|![Step 3](./TFPX-102-materials/images/spacer_step3.jpg)|

4. Pick up the brass sandwich and flip it about its long edge.

|Step 4|
|-|
|![Step 4](./TFPX-102-materials/images/spacer_step4.jpg)|

5. Remove the top brass piece, being careful that the spacer is not lifted with it. If the spacer is lifted, carefully place it back where it was.

|Step 5|
|-|
|![Step 5](./TFPX-102-materials/images/spacer_step5.jpg)|

### Step 2: Run installation script

You can now load the spacer installation script into the gScript Interpreter, which can be found at:

`./gantry-config-bu/Scripts/TFPXModules/Pre-production Scripts/Spacer_1x2_sensor.gscript`

Run the script and follow the prompts in the pop-ups. The spacer locations are labeled on the brass fixture (0, 1, 2, 3). See below for what the HDI fiducial markers should look like.

|HDI Fiducial Marker|
|-|
|![HDI Fiducial](./TFPX-102-materials/images/hdi_fiducial.png)|


Once the gantry places the spacer and completes the script, save the generated log file in the Logs directory (`./gantry-config-bu/Logs/`).



### Step 3: Cure spacer

Let the spacer cure for at least 8 hours. Place a note saying "DO NOT TOUCH, GLUE CURING" next to the module so no one unknowingly interferes with this process.

### Next steps

After the glue is cured, you can now screw the module into the assembly carrier it's on using two M2.5 screws in the two locations circled in red below.

|Assembly Carrier Screws|
|-|
|![Screw locations](./TFPX-102-materials/images/spacer_screws.png)|

At this point, you can now begin the wirebonding process immediately, or put the module/assembly carrier into the dry air cabinet to continue it at a later time.