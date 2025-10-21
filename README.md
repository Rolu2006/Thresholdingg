# THRESHOLDING
## Developed by : SOMALARAJU ROHINI
## Reg no : 212224240156
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
Load the necessary packages.
### Step2:
Read the Image and convert to grayscale.

### Step3:

Use Global thresholding to segment the image.
### Step4:
Use Adaptive thresholding to segment the image.
### Step5:

Use Otsu's method to segment the image and display the results.

## Program

```python
# Load the necessary packages

import cv2
import numpy as np
import matplotlib.pyplot as plt



# Read the Image and convert to grayscale


image = cv2.imread("Shinchan.webp")  # Replace with your image file path
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)  # Convert to grayscale
plt.subplot(2, 2, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert from BGR to RGB for display
plt.title("Original Image")
plt.axis('off')

# Use Global thresholding to segment the image


_, global_thresholded = cv2.threshold(gray_image, 127, 255, cv2.THRESH_BINARY)

# Use Adaptive thresholding to segment the image

adaptive_thresholded = cv2.adaptiveThreshold(gray_image, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C, cv2.THRESH_BINARY, 11, 2)


# Use Otsu's method to segment the image 


_, otsu_thresholded = cv2.threshold(gray_image, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)


# Display the results

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
## Output

### Original Image
<img width="309" height="214" alt="Screenshot 2025-10-21 154902" src="https://github.com/user-attachments/assets/ad4e9890-e1b4-41b0-bbd4-0a008ca652e4" />





### Global Thresholding




<img width="309" height="216" alt="Screenshot 2025-10-21 154907" src="https://github.com/user-attachments/assets/1972bcfb-f639-49f8-838f-80d03b36a911" />




### Adaptive Thresholding





<img width="306" height="214" alt="Screenshot 2025-10-21 154913" src="https://github.com/user-attachments/assets/452d50b4-f9e3-47bf-b531-6059310c6cf3" />


### Optimum Global Thesholding using Otsu's Method




<img width="307" height="214" alt="Screenshot 2025-10-21 154918" src="https://github.com/user-attachments/assets/dce50916-8699-449d-b2aa-a047523f40f3" />




## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
