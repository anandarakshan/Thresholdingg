# THRESHOLDING
## Name: Ananda Rakshan K V
## Reg.No: 212223230014
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
# Step 2: Read the image and convert to grayscale
image = cv2.imread('a.jpg')  # Replace with your image file path
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)  # Convert to grayscale
# Original Image
plt.subplot(2, 2, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert from BGR to RGB for display
plt.title("Original Image")
plt.axis('off')

# Use Global thresholding to segment the image
# Step 3: Use Global Thresholding to segment the image
# Apply global thresholding with a threshold value of 127
_, global_thresholded = cv2.threshold(gray_image, 127, 255, cv2.THRESH_BINARY)

# Use Adaptive thresholding to segment the image
# Step 4: Use Adaptive Thresholding to segment the image
# Apply adaptive thresholding using Gaussian method
adaptive_thresholded = cv2.adaptiveThreshold(gray_image, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C, cv2.THRESH_BINARY, 11, 2)

# Use Otsu's method to segment the image 
# Step 5: Use Otsu's method to segment the image
# Apply Otsu's method for optimal thresholding
_, otsu_thresholded = cv2.threshold(gray_image, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)

# Display the results
# Global Thresholding
plt.subplot(2, 2, 2)
plt.imshow(global_thresholded, cmap='gray')
plt.title("Global Thresholding")
plt.axis('off')
# Show the plot
plt.tight_layout()
plt.show()
# Adaptive Thresholding
plt.subplot(2, 2, 3)
plt.imshow(adaptive_thresholded, cmap='gray')
plt.title("Adaptive Thresholding")
plt.axis('off')
# Show the plot
plt.tight_layout()
plt.show()
# Otsu's Method
plt.subplot(2, 2, 4)
plt.imshow(otsu_thresholded, cmap='gray')
plt.title("Otsu's Method")
plt.axis('off')
# Show the plot
plt.tight_layout()
plt.show()
```
## Output

### Original Image
<img width="245" height="261" alt="image" src="https://github.com/user-attachments/assets/2f0287e1-e38c-40bc-849f-dc6618767f4b" />


### Global Thresholding
<img width="309" height="308" alt="image" src="https://github.com/user-attachments/assets/a4fe47ee-35f5-493f-aa46-49a3e36214b4" />

### Adaptive Thresholding
<img width="291" height="314" alt="image" src="https://github.com/user-attachments/assets/64d1fd21-42f4-4adf-9741-add211958fd7" />

### Optimum Global Thesholding using Otsu's Method
<img width="296" height="322" alt="image" src="https://github.com/user-attachments/assets/7dd26f1d-aed7-4437-b9f6-9ac4546ce901" />

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
