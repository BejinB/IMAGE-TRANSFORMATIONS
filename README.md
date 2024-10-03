# IMAGE-TRANSFORMATIONS


## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:

Import necessary libraries such as OpenCV, NumPy, and Matplotlib for image processing and visualization.

### Step2:

Read the input image using cv2.imread() and store it in a variable for further processing.


### Step3:

Apply various transformations like translation, scaling, shearing, reflection, rotation, and cropping by defining corresponding functions:

1.Translation moves the image along the x or y-axis.
2.Scaling resizes the image by scaling factors.
3.Shearing distorts the image along one axis.
4.Reflection flips the image horizontally or vertically.
5.Rotation rotates the image by a given angle.

### Step4:
Display the transformed images using Matplotlib for visualization. Convert the BGR image to RGB format to ensure proper color representation.

### Step5:
Save or display the final transformed images for analysis and use plt.show() to display them inline in Jupyter or compatible environments.

## Program:
### Developed by: Bejin.B
### Reg no: 212222230021

```python

import cv2
import numpy as np
import matplotlib.pyplot as plt

# Load the image
image = cv2.imread('img2.jpeg')
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)


plt.imshow(image_rgb)
plt.title("Original Image")
plt.axis('off')
```
![image](https://github.com/user-attachments/assets/42c0ca8d-18bc-41a7-8fd9-7f4936a946e9)

```python
# 1. Translation
rows, cols, _ = image.shape
M_translate = np.float32([[1, 0, 50], [0, 1, 100]]) 
translated_image = cv2.warpAffine(image_rgb, M_translate, (cols, rows))


plt.imshow(translated_image)
plt.title("Translated Image")
plt.axis('off')
```
![image](https://github.com/user-attachments/assets/d707d756-e209-41ff-8ce7-d3c5f0105982)

```python
# 2. Scaling
scaled_image = cv2.resize(image_rgb, None, fx=1.5, fy=1.5, interpolation=cv2.INTER_LINEAR)


 plt.imshow(scaled_image)
 plt.title("Scaled Image")
 plt.axis('off')
```
![image](https://github.com/user-attachments/assets/a3739b8a-31ec-49f4-b6e0-d313cef55654)

```python
# 3. Shearing
M_shear = np.float32([[1, 0.5, 0], [0.5, 1, 0]])  
sheared_image = cv2.warpAffine(image_rgb, M_shear, (int(cols * 1.5), int(rows * 1.5)))



plt.imshow(sheared_image)
plt.title("Sheared Image")
plt.axis('off')
```
![image](https://github.com/user-attachments/assets/a11a9685-855b-41b3-9e88-f51959854335)

```python
# 4. Reflection (Flip)
reflected_image = cv2.flip(image_rgb, 1)


plt.imshow(reflected_image)
plt.title("Reflected Image")
plt.axis('off') 
```
![image](https://github.com/user-attachments/assets/fe29a331-3c3e-4887-9942-3398323857fe)

```python
# 5. Rotation
M_rotate = cv2.getRotationMatrix2D((cols / 2, rows / 2), 45, 1)  
rotated_image = cv2.warpAffine(image_rgb, M_rotate, (cols, rows))


plt.imshow(rotated_image)
plt.title("Rotated Image")
plt.axis('off')
```
![image](https://github.com/user-attachments/assets/f4cad551-f0eb-4ec9-919f-d8f41a5e5d6b)

```python
# 6. Cropping
cropped_image = image_rgb[50:300, 100:400]


plt.imshow(cropped_image)
plt.title("Cropped Image")
plt.axis('off')
plt.show()  

# Plot the original and transformed images
plt.figure(figsize=(12, 8))

```
![image](https://github.com/user-attachments/assets/8de19b7f-1b5b-4e84-8657-32c068a77993)


## Output:






## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
