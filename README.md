# Implementation-of-Erosion-and-Dilation
## Aim
To implement Erosion and Dilation using Python and OpenCV.
## Software Required
1. Anaconda - Python 3.7
2. OpenCV
## Algorithm:
### Step1:
Import necessary packages

### Step2:
Create an empty window and add text to it

### Step3:
create a structuring element

### Step4:
Do the operation

### Step5:
Print the output images




 
## Program:

``` Python
import cv2
import numpy as np
from matplotlib import pyplot as plt

# Read the color image
input_image_path = 'img.jpg'
color_image = cv2.imread(input_image_path)

# Convert the color image to grayscale
gray_image = cv2.cvtColor(color_image, cv2.COLOR_BGR2GRAY)

# Perform edge detection using Canny
edges = cv2.Canny(gray_image, 100, 200) # You can adjust the thresholds as needed

# Define the kernel size for erosion and dilation
kernel_size = 5
kernel = np.ones((kernel_size, kernel_size), np.uint8)

# Perform erosion
erosion = cv2.erode(edges, kernel, iterations=1)

# Perform dilation
dilation = cv2.dilate(edges, kernel, iterations=1)

# Display all images
plt.figure(figsize=(15, 10))

plt.subplot(2, 3, 1)
plt.imshow(cv2.cvtColor(color_image, cv2.COLOR_BGR2RGB))
plt.title('Original Color Image')
plt.axis('on')

plt.subplot(2, 3, 2)
plt.imshow(gray_image, cmap='gray')
plt.title('Black and White Image')
plt.axis('on')

plt.subplot(2, 3, 3)
plt.imshow(edges, cmap='gray')
plt.title('Edge Segmentation')
plt.axis('on')

plt.subplot(2, 3, 4)
plt.imshow(erosion, cmap='gray')
plt.title('Erosion')
plt.axis('on')

plt.subplot(2, 3, 5)
plt.imshow(dilation, cmap='gray')
plt.title('Dilation')
plt.axis('on')

plt.show()





```
## Output:

### Display the input Image
![image](https://github.com/Gokulanbazhagan/erosion-dilation/assets/119518996/368e851a-1fa5-4d08-8b36-2bd12f9d63b9)


![image](https://github.com/Gokulanbazhagan/erosion-dilation/assets/119518996/4d6f252d-6297-4728-b107-caf8ba0c7a76)


## Result
Thus the generated text image is eroded and dilated using python and OpenCV.
