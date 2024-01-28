# Image Capture Mediums
#COLO1070
## Monochrome Film
- similar physical structure to other film types
- photographic emulsion coated into substrate (Cellulose acetate / PET)
- In early Days the emulsion was only sensitive to UV and violet / blue light
- final product is panchromatic - sensitive to all colours in the visible spectrum
### Structure:
Gelatin binder | Sliver halide in suspension
Celluloid base
Physical Handling protective back
### Image Capture
- camera shutter opening exposes AgX crystals on the film to light
- AgX crystals change to the Mattalic Ag but cannot be seen by the naked eye
- the invisible image is referred to as the latent image
#### Latent Image Formation
- defects in the crystal structure act as traps for the electrons
- these are released when bromide ions revert to bromine atoms as a result of light striking the crystal
- the electrons build up around the fault forming a negative charge
- htis attracts positivley charged silver ions - combine with electrons to firm pure silver 
- the remaining bromine atoms diffuse out
### Film development Process
- Reduction Process
- Silver halidde crystals exposed to light are now fully reduced to metallic silver (dark specks form on the exposed crystals & grow until each crystal has turned black)
- Development process increases the minor levels of silver halide present by a factor of over 1mil
### Film Fixation Stage
- Removes non exposed AgX material in gelatin layer
- to stop whole image darkening on exposure to light
- insoluble Agx is transformed onto soluble compounds and removed by washing
![[Images/Pasted image 20230428171546.png]]

## Colour Film
### Colour Negative Film
- The most popular film recording medium for both amateur and professional photographers
- The photo finishing industry is set-up for mass processing and printing of colour negative film
- The photographic emulsion layers are assembled as follows:
	1. The top emulsion layer is sensitive to blue light
	2. The second layer is a yellow filter layer which is present to prevent blue light reaching the two other emulsion layers
	3. The next emulsion layer is sensitive to green light
	4. The final emulsion layer is sensitive to red light
- During image capture a Latent Image will be formed in all three emulsion layers
#### Exposure
- Blue regions of the image will register in the upper emulsion layer (Yellow Dye)
- Green areas of the image will register in the second emulsion layer (Magenta Dye)
- Red areas of the image will register in the third emulsion layer (Cyan Dye)
- Orange areas (a mixture of red + green light) will register in both the second & third emulsion layers
#### Development
- A silver (Ag) image is produced in the emulsion layers of the film where light of the appropriate colours fall
- Oxidation products react with the colour couplers to form coloured dyes
#### Bleaching
- The bleach bath converts the metallic silver (Ag) back into silver halides (AgX)and also removes the yellow filter
#### Fixation
- Silver halide (AgX) is removed from the film in the fixing bath, leaving only the dye image in each layer in the complementary colours of the light that struck the film
### Overview
- The negative coloured dye images formed during the colour development stage are perfect replicas of the monochrome silver images originally formed following the first development stage
- The final bleach/fix stages remove the three negative silver images together with the filter layer and the unexposed silver halide crystals
- Following the washing stage the only material left is the layered dye images
- The colour printing stage reverses the negative image back to a positive image
- The chemicals and paper which reverse the image, together with its colours and tone, are very similar to the film and chemicals used to create the initial negative image

## Colour Transparency Film
- Often referred to as slide or positive film
- Superior image quality to colour negative film– has finer grain structure, with the image dyes having brighter and cleaner colours
- Prints can be obtained direct using Ilford Ilfochrome Classic materials
### Image Capture Process
- Colour transparency film is very similar to colour negative film with respect to construction
- Colour negative film has coloured couplers whereas those in transparency film are colourless
- Exposure response is similar, with a latent image being formed within each of the emulsion layers
- Upper emulsion blue sensitive, middle –green sensitive & lower red sensitive
- Blue light is recorded by the top layer
- Green light is recorded by the middle layer
- Red light is recorded by the bottom layer
#### Image Development
- Development stages different to those for colour negative film
- Initial development similar to that used for monochrome and colour negative film development i.e. negative silver image formed within each of the emulsion layers
- Followed by chemical fogging of the film – creates a positive image in each of the emulsion layers
- During the colour development stage chemicals react with the couplers to produce a positive dye image (cyan, magenta yellow)
- The final bleach/fix stage removes both positive and negative silver images leaving only the positive layered dye images
-  It is the grains of silver initially unexposed that act as the template for the production of the positive dye image that ultimately forms the final image
- As the larger AgX grains are the most sensitive to the incoming light, it follows that these will be the first to be exposed
- Thus the unexposed grains will be the finer grains - It is these that form the template for the final dye image
- Transparency film has limited exposure latitude meaning that only half an f-stop can mean the difference between a successful image and an ordinary image
- Transparency film is also sensitive to the vagaries of light and often requires added filtration

## CCD / CMOS Image Capture Technology
A digital camera will contain either a CCD(Charge Coupled Device) or CMOS(Complemantary Metal Oxide Semiconductor) device as the light sensitive image sensor
- instead of silver halide crystals these use pixels and convert the photons to electric signals
### CCD - Principle
1. On pressing the camera release button the semiconductor material responds to the incoming light(photons)
2. Each pixel accumulates electrons in proportion to the level of light received. The photo diode converts the light into an accumulated electrical charge
3. The charge is moved off the sensor (with all the other charges from other photo sites) through transfer channels to an amplifier
4. The amplifier charge is moved down the full array of electrodes to the ADC (analogue-to-digital converter)
5. The signal is processed by the analogue-to-digital converter (ADC) into digital data (0’s & 1’s)
6. The imaging engine processes the image in a number of ways, including applying user settings,compression and noise reduction

### CMOS 
- These sensors have photo sites that are independent of their neighbour i.e. this means that there is random access to each pixel via an X-Y address
- Pixel reading is non-destructive with the charge remaining after the initial reading
#### Key Factors
- Manufacturing ~90% identical to that of a computer chip
- Therefore relatively cheap mass production
- Direct charge conversion without requirement for transfer
- Each pixel has its own amplifier and transistors – so no shift register (Active Pixel sensor)
- Each pixel can be individually addressed 
- No complex time clocks required
- Low energy consumption (~100x less than a CCD sensor)
- High reading rate

### Digital Camera Sensors
- For DSLR’s there are currently only Full-frame sensors or APS-C crop sensors
- It should be noted that a crop sensor does not change the focal length of the lens, just how much of the area is captured
- APS is cheaper but full frame is preferred
- There are 3 key advantages associated with full-frame sensors over crop sensors:
	1. More light sensitivity – more space for light to hit the sensor & larger pixels collect more photons.
	2. Less noise – by having larger pixels to capture the light, the camera does not have to amplify them in order to match the same ISO from a smaller sensor. Thus, the larger the sensor you start with, the less noise present in your final image.
	3. Depth of Field – the ability to have a shallow depth of field can be a key factor

### Problems with CCD / CMOS Sensors
#### Aliasing & Moire fringing
- When patterns on a subject interfere with the shape of the light sensor
- Low pass filters are fitted to alleviate this problem
#### Infrared Sensitivity
- Sensors tend to be inherently sensitive to IR radiation particularly NIR
- Thus an IR filter (hot mirror) is fitted to alleviate this problem and help minimise colour casts
#### Digital Noise
- Inherent thermal effects in the sensor material results in‘rogue’ electrons contributing to the final pixel data
- Under low light conditions at a high ISO rating these ‘rogue’electrons form an increased proportion of the total amount of electrons
- The result is coloured spots – especially in the darker regions of the image
#### Sensor Microlense
- not all the lens can be used to capture light
- direct the light onto the pixilated areas
- avoid busses and other electronics

### Colour Reproduction
#### Filter Masks
- most systems integrate a bayer filter mask onto the sensor
- only one colour is recorded at each pixel - software interpolation used to create the other two
#### Other Filter Masks
![[Images/Pasted image 20230313155200.png]]
(a) Standard Bayer Filter
(b) Used in some video [cameras](Cameras.md)
(c) Used in some Sony cameras for improved colour
(d) Bayer type with additional transparent elements for better light detection

#### Storage
- To create a digital image the analogue undergoes quantisation whereby each step is assigned a binary number representing atone / grey level (A/D converter)
- Maximum number of grey levels supported by image handling applications on a PC = 256 & 8 Bits is required to enumerate 256 grey levels
- Thus for RGB colour reproduction we require 256 x 256 x 256 = 16.7 million colours
- Most A/D converters produce 10, 12, 14 or 16 grey levels =‘Supersampling’