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

Developed By: SANTHANA LEKSHMI K

Register Number: 212222240091

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

![2024-09-25 (12)](https://github.com/user-attachments/assets/2a42bb3f-fc57-411d-becc-24afe49e8377)


### ii)Image Translation


![2024-09-25 (13)](https://github.com/user-attachments/assets/b13edfb6-5353-43ab-a9ae-3256a3f2d7f2)


### iii) Image Scaling 


![2024-09-25 (14)](https://github.com/user-attachments/assets/51bc7388-ad97-49db-aaac-5c2b0bd00f0f)



### iv)Image shearing


![2024-09-25 (15)](https://github.com/user-attachments/assets/b6c7eab0-9143-4de4-96c7-4a6f7bdc6920)


### v)Image Reflection


![2024-09-25 (16)](https://github.com/user-attachments/assets/7360e5a1-79ac-466b-a159-b0a22d7b6a06)


### vi)Image Rotation


![2024-09-25 (17)](https://github.com/user-attachments/assets/1fa49594-4c55-4162-8b01-713c4432ced6)


### vii)Image Cropping


![2024-09-25 (18)](https://github.com/user-attachments/assets/7519c5d7-dacb-4ca2-8cdd-ba8164ea94d4)



## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
