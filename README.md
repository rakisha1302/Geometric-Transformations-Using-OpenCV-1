# Geometric-Transformations-Using-OpenCV-1
---

## Aim

To write a Python program using OpenCV to perform various geometric transformations on an image.

The program performs the following operations:

- Image Translation  
- Image Scaling (Resizing)  
- Image Shearing  
- Image Reflection (Flipping)  
- Image Rotation  

---

##  Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (`cv2`)  
- NumPy  
- Matplotlib  

---

##  Algorithm

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the input image in color mode.

### Step 3: Image Translation
- Create a translation matrix to shift the image  
- Move the image 50 pixels to the right and 80 pixels down  
- Apply transformation using `cv2.warpAffine()`  
- Display original and translated images  

### Step 4: Image Scaling
- Resize the image to 0.5× (downscale)  
- Resize the image to 2× (upscale)  
- Use `cv2.resize()`  
- Display original, downscaled, and upscaled images  

### Step 5: Image Shearing
- Create transformation matrices for:
  - Horizontal shearing  
  - Vertical shearing  
- Apply transformations using `cv2.warpAffine()`  
- Display original and sheared images  

### Step 6: Image Reflection
- Perform flipping using `cv2.flip()`:
  - Horizontal reflection  
  - Vertical reflection  
  - Both axes  
- Display all reflected images  

### Step 7: Image Rotation
- Create rotation matrices for:
  - 45° rotation  
  - 90° rotation  
- Use `cv2.getRotationMatrix2D()` and `cv2.warpAffine()`  
- Display original and rotated images  

---

##  Program

### Developed By:
**Name:** Rakisha R
### Register No:212225230223


---

##  Output
```
import cv2
import matplotlib.pyplot as plt
# Step 1: Load the image
image = cv2.imread('EX4.jpg')  # Load the image from file
# Display the original image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB for correct display
plt.title("Original Image")  
plt.axis('off') 
```

<Figure size 640x480 with 1 Axes><img width="516" height="319" alt="image" src="https://github.com/user-attachments/assets/423197bc-84cb-4e97-8886-f5e46870a75a" />
  
```
  import cv2
import numpy as np
rows, cols = image.shape[:2]
M = np.float32([[1, 0, 100],
                [0, 1, 50]])
translated_image = cv2.warpAffine(image, M, (cols, rows))
import matplotlib.pyplot as plt
plt.imshow(cv2.cvtColor(translated_image, cv2.COLOR_BGR2RGB))
plt.title("Translated Image")
plt.axis("off")
plt.show()
```
  
<Figure size 640x480 with 1 Axes><img width="516" height="319" alt="image" src="https://github.com/user-attachments/assets/7a9137a8-7fb1-4ce2-8c3d-fa6d95ec2a22" />
  
```
fx, fy = 5.0, 2.0  # Scaling factors (1.5x scaling for both width and height)
scaled_image = cv2.resize(image, None, fx=fx, fy=fy, interpolation=cv2.INTER_LINEAR)
# resize: Resize the image by scaling factors fx, fy
# INTER_LINEAR: Uses bilinear interpolation for resizing
plt.imshow(cv2.cvtColor(scaled_image, cv2.COLOR_BGR2RGB))  # Display the scaled image
plt.title("Scaled Image")  # Set title
plt.axis('off')
```

<Figure size 640x480 with 1 Axes><img width="516" height="152" alt="image" src="https://github.com/user-attachments/assets/ec27643a-1854-4089-884b-a959bb454bef" />
  
```
import cv2
import numpy as np
rows, cols = image.shape[:2]
M = np.float32([
    [1, 0.5, 0],
    [0, 1, 0]
])
sheared_image = cv2.warpAffine(image, M, (int(cols * 1.5), rows))
import matplotlib.pyplot as plt
plt.imshow(cv2.cvtColor(sheared_image, cv2.COLOR_BGR2RGB))
plt.title("Sheared Image")
plt.axis("off")
plt.show()
```

<Figure size 640x480 with 1 Axes><img width="516" height="226" alt="image" src="https://github.com/user-attachments/assets/b8426545-09dd-4cc4-a8dc-8183f94258a1" />
  
```
import matplotlib.pyplot as plt
image = cv2.imread("EX4.jpg")
reflected_image = cv2.flip(image, 1)
plt.imshow(cv2.cvtColor(reflected_image, cv2.COLOR_BGR2RGB))
plt.title("Reflected Building Image")
plt.axis("off")
plt.show()
```

<Figure size 640x480 with 1 Axes><img width="516" height="319" alt="image" src="https://github.com/user-attachments/assets/bc4e80ce-3783-445f-b064-4b1e1c19c341" />
  
```
(height, width) = image.shape[:2]  # Get the image height and width
angle = 45  # Rotation angle in degrees (rotate by 45 degrees)
center = (width // 2, height // 2)  # Set the center of rotation to the image center
M_rotation = cv2.getRotationMatrix2D(center, angle, 1)  # Get the rotation matrix
rotated_image = cv2.warpAffine(image, M_rotation, (width, height))  # Apply rotation
plt.imshow(cv2.cvtColor(rotated_image, cv2.COLOR_BGR2RGB))  # Display the rotated image
plt.title("Rotated Image")  # Set title
plt.axis('off')
```

<Figure size 640x480 with 1 Axes><img width="516" height="319" alt="image" src="https://github.com/user-attachments/assets/7f74e59a-dec8-4d3f-a973-1cda7ed93fef" />
  
```
x, y, w, h = 100, 100, 200, 150  # Define the top-left corner (x, y) and the width (w) and height (h) of the crop
cropped_image = image[y:y+h, x:x+w]
plt.imshow(cv2.cvtColor(cropped_image, cv2.COLOR_BGR2RGB))  # Display the cropped image
plt.title("Cropped Image")  # Set title
plt.axis('off')
```
<Figure size 640x480 with 1 Axes><img width="512" height="410" alt="image" src="https://github.com/user-attachments/assets/09422803-44ad-4ffe-b730-a39c964cf692" />

---

##  Result

Thus, various geometric transformations such as translation, scaling, shearing, reflection, and rotation are successfully performed using OpenCV. These transformations demonstrate how images can be spatially manipulated for different computer vision applications.
