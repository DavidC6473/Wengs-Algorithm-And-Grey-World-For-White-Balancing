# White Balance Algorithms for Image Processing

This project implements two white balance algorithms for automatic color correction of images: Grey World and Weng's algorithm.

## Grey World Algorithm

The Grey World algorithm assumes that the average color of a properly balanced image is gray or achromatic. It works by estimating the average color of an image and adjusting the individual color channels to make the average color appear as a shade of gray.

To use the Grey World algorithm, you can use the `gw(img)` function provided in the code. Here's an example of how to use the function:

```python
import matplotlib.pyplot as plt
from skimage.io import imread, imsave
from grey_world import gw

# Load an image using skimage.io.imread
image = imread('path/to/image.jpg')

# Apply Grey World white balancing
balanced_image = gw(image)

# Display the original and balanced images
plt.figure(figsize=(10, 5))
plt.subplot(1, 2, 1)
plt.title('Original Image')
plt.imshow(image)
plt.subplot(1, 2, 2)
plt.title('White Balanced Image (Grey World)')
plt.imshow(balanced_image)
plt.show()

# Save the balanced image using skimage.io.imsave
imsave('path/to/save/balanced_image_grey_world.jpg', balanced_image)
Make sure to replace `'path/to/image.jpg'` and `'path/to/save/balanced_image_grey_world.jpg'` with the appropriate file paths.

## Weng's Algorithm

Weng's algorithm is another white balance algorithm that aims to correct color casts in images. It classifies near-white pixels based on the average absolute differences of the chrominance components (Cb and Cr) from their mean values. It then adjusts the color channels of the identified near-white pixels.

To use Weng's algorithm, you can use the `Weng(img)` function provided in the code. Here's an example of how to use the function:

```python
import matplotlib.pyplot as plt
from skimage.io import imread, imsave
from weng import Weng

# Load an image using skimage.io.imread
image = imread('path/to/image.jpg')

# Apply Weng's white balancing
balanced_image = Weng(image)

# Display the original and balanced images
plt.figure(figsize=(10, 5))
plt.subplot(1, 2, 1)
plt.title('Original Image')
plt.imshow(image)
plt.subplot(1, 2, 2)
plt.title('White Balanced Image (Weng\'s Algorithm)')
plt.imshow(balanced_image)
plt.show()

# Save the balanced image using skimage.io.imsave
imsave('path/to/save/balanced_image_weng.jpg', balanced_image)

Make sure to replace 'path/to/image.jpg' and 'path/to/save/balanced_image_weng.jpg' with the appropriate file paths.
## Dependencies

The following dependencies are required to run the code:

- NumPy
- Matplotlib
- scikit-image (skimage)

You can install the dependencies using pip:

```bash
pip install numpy matplotlib scikit-image
