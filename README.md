# IMAGE-TRANSFORMATIONS


## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import the necessary libraries and read the original image and save it as a image variable.

### Step2:
Translate the image using a function warpPerpective()


### Step3:
Scale the image by multiplying the rows and columns with a float value.



### Step4:
Shear the image in both the rows and columns.



### Step5:
Find the reflection of the image.

### step 6:
Rotate the image using angle function

## Program:

Developed By: HARITHA SHREE

Register Number: 212222230046

i)Original Image:

```
import numpy as np
import cv2
import matplotlib.pyplot as plt
input_img = cv2.imread("image.jpeg")
# cv2.imshow("image webp",input_img)
input_img = cv2.cvtColor(input_img, cv2.COLOR_BGR2RGB)
plt.axis('off')
plt.imshow(input_img)
plt.show()

```

ii)Image Translation

```
rows,cols,dim=input_img.shape
M=np.float32([[1,0,50],  [0,1,100],  [0,0,1]])
translated_image=cv2.warpPerspective(input_img,M,(cols,rows))
plt.axis('off')
plt.imshow(translated_image)
plt.show()

```

iii) Image Scaling

```
scale_factor = 1.5
M_scale = np.float32([[scale_factor, 0, 0],
                      [0, scale_factor, 0],
                      [0, 0, 1]])

scaled_img = cv2.warpAffine(input_img, M[:2], (int(cols*scale_factor), int(rows*scale_factor)))
plt.axis('off')
plt.imshow(scaled_img)
plt.show()

```

iv)Image shearing

```
M_x = np.float32([[1, 0.2, 0],
                  [0, 1, 0],
                  [0, 0, 1]])

sheared_img_xaxis = cv2.warpAffine(input_img, M_x[:2], (cols, rows))
plt.axis('off')
plt.imshow(sheared_img_xaxis)
plt.show()
M_y = np.float32([[1, 0, 0],
                  [0.2, 1, 0],
                  [0, 0, 1]])

sheared_img_yaxis = cv2.warpAffine(input_img, M_y[:2], (cols, rows))
plt.axis('off')
plt.imshow(sheared_img_yaxis)
plt.show()

```

v)Image Reflection

```
M_x = np.float32([[-1, 0, cols],
                  [0, 1, 0],
                  [0, 0, 1]])

reflected_img_xaxis = cv2.warpAffine(input_img, M_x[:2], (cols, rows))

plt.axis("off")
plt.imshow(reflected_img_xaxis)
plt.show()

M_y = np.float32([[1, 0, 0],
                  [0, -1, rows],
                  [0, 0, 1]])

reflected_img_yaxis = cv2.warpAffine(input_img, M_y[:2], (cols, rows))

plt.axis("off")
plt.imshow(reflected_img_yaxis)
plt.show()

```

vi)Image Rotation

```
angle = np.radians(-60)
M = np.float32([[np.cos(angle), -np.sin(angle), 0],
                [np.sin(angle), np.cos(angle), 0]])
center = (cols // 2, rows // 2)
M = cv2.getRotationMatrix2D(center, -60, 1.0)
rotated_img = cv2.warpAffine(input_img, M, (cols, rows))

plt.axis('off')
plt.imshow(rotated_img)
plt.show()

```

vii)Image Cropping

```
cropped_img = input_img[50:200, 200:400]
plt.axis('off')
plt.imshow(cropped_img)
plt.show()

```
## Output:
### i)Original Image

![2024-10-01](https://github.com/user-attachments/assets/7aa31955-b12e-43a5-8b08-6980d749c4c4)


### ii)Image Translation


![2024-10-01 (3)](https://github.com/user-attachments/assets/5f8dfafa-d1ba-4772-8017-230712fdfe4a)


### iii) Image Scaling 


![2024-10-01 (4)](https://github.com/user-attachments/assets/96115b70-0640-4de9-8f14-d11a3a6eb871)



### iv)Image shearing


![2024-10-01 (5)](https://github.com/user-attachments/assets/7fc2e9b2-7ff0-4d06-b445-11ae68eb63b7)


### v)Image Reflection


![2024-10-01 (11)](https://github.com/user-attachments/assets/281da8ce-6e4c-4dbc-ad76-5d54c43a787c)


### vi)Image Rotation

![2024-10-01 (12)](https://github.com/user-attachments/assets/3e0e02aa-ac9b-4e86-8dbd-f2acd73c7db7)



### vii)Image Cropping


![2024-10-01 (13)](https://github.com/user-attachments/assets/4782532b-eb1f-4d41-9cc1-22e0822cf58b)



## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
