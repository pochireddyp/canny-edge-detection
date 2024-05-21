## Canny Edge Detection using Python
i)Implementation of the Canny edge detection algorithm on a sample image to obtain the edges.
## Developed By : POCHIREDDY.P
## Register Number : 212223240115
Code :
```
import cv2
import numpy as np
image = cv2.imread('flower.jpg', 0)  # Reading the image in grayscale mode
blurred = cv2.GaussianBlur(image, (5, 5), 0)  # 5x5 kernel size, sigma = 0
edges = cv2.Canny(blurred, 100, 200)
cv2.imshow('Original Image', image)
cv2.imshow('Canny Edges', edges)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
# OUTPUT :
![image](https://github.com/pochireddyp/canny-edge-detection/assets/150232043/cd156226-2281-4c39-b60b-757610b30730)

![image](https://github.com/pochireddyp/canny-edge-detection/assets/150232043/b3a72c85-d57f-45e7-90e3-3fd53604ab72)



ii)How do different parameter settings impact the result?
The Canny edge detector works by detecting areas of high gradient (i.e., rapid intensity changes) in the image. It involves several steps, including smoothing with a Gaussian filter to reduce noise, computing gradients, and applying non-maximum suppression to thin the edges, followed by edge linking with hysteresis.

Different parameter settings can significantly impact the result:
Thresholds (low and high):
These thresholds determine which edges are considered strong, weak, or non-edges. Lower values lead to more edges being detected, while higher values filter out weaker edges. Adjusting these thresholds can impact the sensitivity of edge detection.

Gaussian blur kernel size:
The size of the Gaussian blur kernel affects the amount of smoothing applied to the image. Larger kernels result in more smoothing, which can reduce noise but may also blur edges.

Sigma (standard deviation) for Gaussian blur:
Sigma controls the spread of the Gaussian kernel. Higher values result in more smoothing, while lower values preserve finer details. However, too much smoothing can cause edges to be lost.
