### Methodology:
To separate objects from the background in images where global thresholding methods like Otsu's thresholding fail due to similar intensity distributions, adaptive thresholding was applied. Specifically, the Gaussian adaptive thresholding method was used, which calculates local thresholds for small neighborhoods within the image, enabling better distinction between objects and background in uneven lighting or low contrast conditions.

![adaptive thresholding](https://github.com/user-attachments/assets/6101ac6d-c43a-4b08-937f-721204f4aa5a)

### The steps followed were:

Convert the input image to grayscale.

Apply adaptive Gaussian thresholding with a block size of 11 and a constant subtraction of 2.

Perform contour detection on the thresholded binary image to identify object boundaries.

Draw contours on the original frame to visualize detected objects.

### Results:
Adaptive thresholding was applied to segment objects from the background in images with complex scenes. While this method provided some improvement in separating objects, it struggled to consistently differentiate objects from the background. The effectiveness of adaptive thresholding heavily depended on factors such as lighting intensity, shadows, surface reflections, and texture variations. These environmental variations caused inconsistencies in segmentation, leading to unreliable contour detection in certain scenarios.
During real-time video processing, the system achieved approximately 13 frames per second (FPS) for a 10s window. Although this allows visualization in real time, the frame rate may not be adequate for industrial bin picking applications where faster and more robust object detection is required. 

### Conclusion:
Adaptive thresholding and contour analysis can be useful for object segmentation under controlled lighting and simple backgrounds. However, due to its sensitivity to lighting conditions, shadows, reflections, and surface textures, it may not reliably separate objects from backgrounds in complex real-world settings.

For high-speed and reliable object detection in bin picking robots, deep learning-based methods such as convolutional neural networks (e.g., YOLO, Mask R-CNN) are preferred. These models are more robust to environmental variations and can deliver higher accuracy and faster processing speeds, meeting the stringent requirements of real-time industrial applications.
