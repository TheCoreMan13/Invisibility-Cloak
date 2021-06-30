# Invisibility-Cloak

As the name suggests, It’s a cloak that makes you invisible but for the web camera.

How it works:
1. Capture and store the background frame into a loop
2. Detect the defined color using a color-detection and segmentation algorithm.
3. Segment out the defined colored part by generating a mask.
4. Generate the final augmented output to create the effect of invisibility (Optional).

Recording and caching the background for each frame:

We are replacing the blue and cyan-colored pixels with the background pixels to create
the invisible effect in the video. For doing this, we have to store the background image
for each frame.

Detecting the defined color portion In each frame:

In this step, we will put our focus on detecting the red part in the image. We will convert
the RGB (red-blue-green) to HSV(hue-saturation-value) because RGB values are highly
sensitive to illumination. After the conversion of RGB to HSV, it is time to specify the
range of colors to detect selected colors in the video.

Replacing the blue portion with a mask image in each frame:

Now, we have a blue-cyan part of the video in the ‘mask’ image, we will segment the
mask part from the frames. We will do a morphology open and dilation for that and add
a filter mask to reduce noise
