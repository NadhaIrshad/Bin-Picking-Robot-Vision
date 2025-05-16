Methodology:
To separate objects from the background in images where global thresholding methods like Otsu's thresholding fail due to similar intensity distributions, adaptive thresholding was applied. Specifically, the Gaussian adaptive thresholding method was used, which calculates local thresholds for small neighborhoods within the image, enabling better distinction between objects and background in uneven lighting or low contrast conditions.

The steps followed were:

Convert the input image to grayscale.

Apply adaptive Gaussian thresholding with a block size of 11 and a constant subtraction of 2.

Perform contour detection on the thresholded binary image to identify object boundaries.

Draw contours on the original frame to visualize detected objects.

Results:
Adaptive thresholding significantly improved the segmentation quality compared to Otsu's method by effectively separating objects from a complex background. Contours were clearly identified around individual objects, demonstrating the method’s ability to delineate object boundaries accurately.

However, when tested in a real-time setup with live video input, the processing speed achieved was approximately 13 frames per second (FPS). Although this frame rate allows for real-time visualization, it may be insufficient for high-speed industrial applications such as bin picking robots, where faster frame rates are critical for timely object detection and manipulation.

Conclusion:
Adaptive thresholding combined with contour analysis is an effective approach for segmenting objects in challenging backgrounds. Nonetheless, due to the moderate processing speed (around 13 FPS), it may not be the most suitable choice for real-time high-speed bin picking systems. For such applications, more efficient algorithms or hardware acceleration, or deep learning-based methods might be preferred to meet real-time performance requirements.
