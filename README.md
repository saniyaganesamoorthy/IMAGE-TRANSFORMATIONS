# IMAGE-TRANSFORMATIONS


## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
# Step1:
Import necessary libraries such as OpenCV, NumPy, and Matplotlib for image processing and visualization.

# Step2:
Read the input image using cv2.imread() and store it in a variable for further processing.

# Step3:
Apply various transformations like translation, scaling, shearing, reflection, rotation, and cropping by defining corresponding functions:

1.Translation moves the image along the x or y-axis.

2.Scaling resizes the image by scaling factors.

3.Shearing distorts the image along one axis.

4.Reflection flips the image horizontally or vertically.

5.Rotation rotates the image by a given angle.

# Step4:
Display the transformed images using Matplotlib for visualization. Convert the BGR image to RGB format to ensure proper color representation.

# Step5:
Save or display the final transformed images for analysis and use plt.show() to display them inline in Jupyter or compatible environments.
## Program:

Developed By: AMRUTHA S A

Register Number:212222110004
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Load the image
image = cv2.imread('flower.jpg')
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)  # Convert BGR to RGB for Matplotlib

# 1. Translation
rows, cols, _ = image.shape
M_translate = np.float32([[1, 0, 50], [0, 1, 100]])  # Translate by (50, 100) pixels
translated_image = cv2.warpAffine(image_rgb, M_translate, (cols, rows))

# 2. Scaling
scaled_image = cv2.resize(image_rgb, None, fx=1.5, fy=1.5, interpolation=cv2.INTER_LINEAR)  # Scale by 1.5x

# 3. Shearing
M_shear = np.float32([[1, 0.5, 0], [0.5, 1, 0]])  # Shear with factor 0.5
sheared_image = cv2.warpAffine(image_rgb, M_shear, (int(cols * 1.5), int(rows * 1.5)))

# 4. Reflection (Flip)
reflected_image = cv2.flip(image_rgb, 1)  # Horizontal reflection (flip along y-axis)

# 5. Rotation
M_rotate = cv2.getRotationMatrix2D((cols / 2, rows / 2), 45, 1)  # Rotate by 45 degrees
rotated_image = cv2.warpAffine(image_rgb, M_rotate, (cols, rows))

# 6. Cropping
cropped_image = image_rgb[50:300, 100:400]  # Crop a portion of the image

# Plot the original and transformed images
plt.figure(figsize=(12, 8))

plt.subplot(2, 3, 1)
plt.imshow(image_rgb)
plt.title("Original Image")
plt.axis('off')
```
```

plt.imshow(translated_image)
plt.title("Translated Image")
plt.axis('off')
```
### i)Image Translation
![Screenshot 2024-10-03 111012](https://github.com/user-attachments/assets/87be2fdc-63df-4003-b153-b13e3b52db34)


```
plt.imshow(scaled_image)
plt.title("Scaled Image")
plt.axis('off')
```
### ii) Image Scaling
![Screenshot 2024-10-03 111045](https://github.com/user-attachments/assets/31aba4a9-ffde-46c7-b59f-befbb38cf3f2)

```
plt.imshow(sheared_image)
plt.title("Sheared Image")
plt.axis('off')
```
### iii)Image shearing

![Screenshot 2024-10-03 111118](https://github.com/user-attachments/assets/5f294ec5-be27-4b5c-beb5-f7a4a947161f)


```
plt.imshow(reflected_image)
plt.title("Reflected Image")
plt.axis('off')
```
### iv)Image Reflection

![Screenshot 2024-10-03 111138](https://github.com/user-attachments/assets/4515f932-f67e-416d-89af-55de932b8f6b)

```
plt.imshow(rotated_image)
plt.title("Rotated Image")
plt.axis('off')

plt.tight_layout()
plt.show()
```
### v)Image Rotated
![Screenshot 2024-10-03 111315](https://github.com/user-attachments/assets/380dea39-157a-473d-80f2-da2cf8316b60)


```
# Plot cropped image separately as its aspect ratio may be different
plt.figure(figsize=(4, 4))
plt.imshow(cropped_image)
plt.title("Cropped Image")
plt.axis('off')
plt.show()

```
### vi)Image Cropping

![Screenshot 2024-10-03 111338](https://github.com/user-attachments/assets/318332ab-d8b8-4766-b438-c58786339a2c)

## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
