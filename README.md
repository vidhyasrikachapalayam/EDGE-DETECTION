# EDGE-DETECTION
## Aim:
To perform edge detection using Sobel, Laplacian, and Canny edge detectors.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import all the necessary modules for the program.

### Step2:
Load a image using imread() from cv2 module.

### Step3:
Convert the image to grayscale

### Step4:
Using Sobel operator from cv2,detect the edges of the image.

### Step5:

Using Laplacian operator from cv2,detect the edges of the image and Using Canny operator from cv2,detect the edges of the image.
## Program:
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('tiger.jpg')
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

sobel_x = cv2.Sobel(gray_image, cv2.CV_64F, 1, 0, ksize=5)  
sobel_y = cv2.Sobel(gray_image, cv2.CV_64F, 0, 1, ksize=5)  
sobel_combined = cv2.magnitude(sobel_x, sobel_y)

laplacian = cv2.Laplacian(gray_image, cv2.CV_64F)

canny_edges = cv2.Canny(gray_image, 50, 150)

plt.figure(figsize=(12, 12))

plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Original Image')
plt.axis('off')

plt.imshow(sobel_combined, cmap='gray')
plt.title('Sobel Edge Detection')
plt.axis('off')

plt.imshow(laplacian, cmap='gray')
plt.title('Laplacian Edge Detection')
plt.axis('off')

plt.imshow(canny_edges, cmap='gray')
plt.title('Canny Edge Detection')
plt.axis('off')

plt.tight_layout()
plt.show()
```

## Output:
### SOBEL EDGE DETECTOR
![image](https://github.com/user-attachments/assets/9599b416-314d-4c3d-8d9b-00cb8c56edf8)

### LAPLACIAN EDGE DETECTOR
![image](https://github.com/user-attachments/assets/93c1e2ee-0565-4299-80da-b96401cf5a31)

### CANNY EDGE DETECTOR
![image](https://github.com/user-attachments/assets/6632570e-789d-464a-9f86-776613b9c275)

## Result:
Thus the edges are detected using Sobel, Laplacian, and Canny edge detectors.
