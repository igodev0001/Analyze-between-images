# differences-between-two-images (or multiple images)
Detect and visualize differences between images with `OpenCV` and the SSIM method. The images are compared with the first provided image.

### Example

    python ./main.py image-1.jpg image-2.jpg image-3.jpg

`image-2.jpg` and `image-3.jpg` will be compared to `image-1.jpg`.

## Back-end logic explained

Let's take the following images:

![](sprites/image-1.jpg)

and:

![](sprites/image-2.jpg)

The first step to do is to compute the ssim difference after having had converted the images from colorized to gray-scaled:

![](sprites/ssim.jpg)

Then, we isolate the differences by binarizing the image:

![](sprites/differences.jpg)

Then, we remove the noise by applying a mask and removing the outliers i.e. the freckles for which the surface is inferior to an arbitrary number:

![](sprites/mask.jpg)

Finally, we compute the bouding box for each surface and superpose it to the image:

![](sprites/boxed.jpg)
