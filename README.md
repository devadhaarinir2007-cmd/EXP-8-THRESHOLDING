# EXP-8-THRESHOLDING

## Aim
To segment an image using Global Thresholding, Adaptive Thresholding, and Otsu's Thresholding techniques using Python and OpenCV.

#### The program performs the following operations:

Global Thresholding.
Adaptive Thresholding.
Otsu's Thresholding.

## Software Used:
Anaconda – Python 3.7
Jupyter Notebook / VS Code
OpenCV (cv2)
NumPy
Matplotlib

## Algorithm:
Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

Step 2:
Load the input image using OpenCV.

Step 3:
Convert the input image into grayscale format.

Step 4: Global Thresholding
Select a fixed threshold value.
Apply thresholding to separate foreground and background pixels.
Display the thresholded image.

Step 5: Adaptive Thresholding
Compute threshold values for small regions of the image.
Apply Adaptive Mean Thresholding.
Apply Adaptive Gaussian Thresholding.
Display the segmented images.

Step 6: Otsu's Thresholding
Automatically determine the optimal threshold value.
Apply Otsu's thresholding technique.
Display the segmented image.

Step 7:
Compare the results obtained from Global, Adaptive, and Otsu's thresholding methods.

## Program:
Developed By
Name: DEVADHAARINI.R
Register No: 212225040061.
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
# Step 2: Read the image and convert to grayscale
image = cv2.imread('photo.png')  # Replace with your image file path
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)  # Convert to grayscale
# Original Image
plt.subplot(2, 2, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert from BGR to RGB for display
plt.title("Original Image")
plt.axis('off')
# Step 3: Use Global Thresholding to segment the image
# Apply global thresholding with a threshold value of 127
_, global_thresholded = cv2.threshold(gray_image, 127, 255, cv2.THRESH_BINARY)
# Step 4: Use Adaptive Thresholding to segment the image
# Apply adaptive thresholding using Gaussian method
adaptive_thresholded = cv2.adaptiveThreshold(gray_image, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C, cv2.THRESH_BINARY, 11, 2)
# Step 5: Use Otsu's method to segment the image
# Apply Otsu's method for optimal thresholding
_, otsu_thresholded = cv2.threshold(gray_image, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)

# Global Thresholding
plt.subplot(2, 2, 2)
plt.imshow(global_thresholded, cmap='gray')
plt.title("Global Thresholding")
plt.axis('off')
# Adaptive Thresholding
plt.subplot(2, 2, 3)
plt.imshow(adaptive_thresholded, cmap='gray')
plt.title("Adaptive Thresholding")
plt.axis('off')
# Otsu's Method
plt.subplot(2, 2, 4)
plt.imshow(otsu_thresholded, cmap='gray')
plt.title("Otsu's Method")
plt.axis('off')
```
## Output:
Original Grayscale Image:
<img width="332" height="247" alt="image" src="https://github.com/user-attachments/assets/961dbd92-ba9c-4d37-952a-5924e43844b9" />

Global Thresholding
<img width="322" height="258" alt="image" src="https://github.com/user-attachments/assets/338983b0-607d-43af-8c3d-b0b3fc4da6f5" />

Adaptive Thresholding
<img width="312" height="235" alt="image" src="https://github.com/user-attachments/assets/12cf34ba-86fe-4a6c-8b28-238243b6ecee" />

Otsu's Thresholding
<img width="302" height="247" alt="image" src="https://github.com/user-attachments/assets/9185d609-378f-4470-829c-ac8a6ec369ac" />

## Result:
Thus, image segmentation is successfully performed using Global Thresholding, Adaptive Thresholding, and Otsu's Thresholding techniques in OpenCV.
