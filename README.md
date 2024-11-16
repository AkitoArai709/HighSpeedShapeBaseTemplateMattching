# HighSpeedShapeBaseTemplateMattching

This application performs template matching at high speed. It is a template matching that extracts shape-based features from a template image and searches for similar objects from a test image.
 
When extracting features from a template image, rotate the image within a set angle range to learn the features. Only the direction of the gradient is used for the feature values. Therefore, as long as the shape of the object does not change, it is robust to changes in luminance and more robust than template matching by gradient.

In searching the template image, a coarse search is performed using pyramid image compression, followed by a detailed search using the original image. Care should be taken because if the pyramid level is set too high, the feature values will be crushed and the search will not be successful. The direction of the gradient is quantized in eight directions, and the amount of computation is greatly reduced by creating a response map using a look-up table.

![app](https://github.com/user-attachments/assets/2f7d8703-2a8e-4a01-841e-dbbe6818c81c)


## Technology features
* Feature extraction of gradient intensity and gradient angle
* Computation reduction by feature quantization
* Pyramid image compression
* SIMD acceleration
* Memory access optimization
