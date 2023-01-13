# Instant NGP Thin

Using the ![Instant NGP work] (https://github.com/NVlabs/instant-ngp) as baseline, modifications were made to better render thin objects. In particular, the following changes were implemented:

# TODO: Add in what changes you made.


To render a 3D object, e.g., potato chip, the following flow was used....
To render a potato chip:
A hole was made in the chip and a string was attached through the hole such that the chip may be hung vertically. The chip was then hung from a lamp such that the light from the lamp would shine directly down onto the chip parallel to the thread attached. Other sources of light in the room were dimmed such that the lamp served as the main source of light. The chip was slowly spun via the thread and a video was taken from all angles. 

Image preprocessing: After the video was taken it was split into images and the backgrounds of all images were removed. The resulting image set had approximately 100 images and was used to train an intant ngp model. As is standard it was first fed into the COLMAP program to get the transforms file. 

The main reason for having to do the setup with the lamp and the thread is because the model only works well at rendering when the light and background are consistent throughout all the shots. This is most likely a limitation of COLMAP but as it requires consistency between frames to create a correct mapping. Thus when the sole source of light shines down on the chip from above it does not matter whether the chip is rotated as the direction of light remains the same similar to how there are no directional shadows when the sun is directly above. This allows for images/video of the chip to be captured from all direction. If the chip were not suspended, it would not be possible to capture the bottom of the chip without changing the way that light hits on the chip. 



As per the Instant NGP work, this work is made available under the Nvidia Source Code License-NC. Click [here](LICENSE.txt) to view a copy of this license.
