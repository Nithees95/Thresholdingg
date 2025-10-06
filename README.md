# THRESHOLDING
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
#Name:  NITHEESH YEGAVINTI
#Reg No: 212224040370
# Load the necessary packages

import numpy as np
import matplotlib.pyplot as plt
import cv2

# Read the Image and convert to grayscale

image = cv2.imread('cheetah.jpeg',1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread('cheetah.jpeg',0)

# Use Global thresholding to segment the image

ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)

# Use Adaptive thresholding to segment the image

thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)

# Use Otsu's method to segment the image 

ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)

# Display the results

titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_img1,thresh_img2,thresh_img3,thresh_img4,thresh_img5,thresh_img6,thresh_img7,thresh_img8]
for i in range(0,9):
    plt.figure(figsize=(10,10))
    plt.subplot(1,2,1)
    plt.title("Original Image")
    plt.imshow(image)
    plt.axis("off")
    plt.subplot(1,2,2)
    plt.title(titles[i])
    plt.imshow(cv2.cvtColor(images[i],cv2.COLOR_BGR2RGB))
    plt.axis("off")
    plt.show()

```
## Output

### Original Image

<img width="893" height="741" alt="image" src="https://github.com/user-attachments/assets/d8e5bcef-8b5f-42db-9be2-accbebe5df42" />


### Global Thresholding

<img width="432" height="370" alt="image" src="https://github.com/user-attachments/assets/f772bd5e-2e15-440b-ad2f-aefc09967231" />
<img width="431" height="371" alt="image" src="https://github.com/user-attachments/assets/73bfe5f1-f4ce-4025-aee6-c97be9612feb" />
<img width="432" height="363" alt="image" src="https://github.com/user-attachments/assets/2f8cae02-05ac-4cb7-b8b3-71cd0e98f7d8" />
<img width="440" height="365" alt="image" src="https://github.com/user-attachments/assets/7409015e-cc8e-4669-919a-fbca9ada0ed1" />
<img width="433" height="368" alt="image" src="https://github.com/user-attachments/assets/9d927dc9-bc17-4df9-b184-d9adeb264509" />
<img width="432" height="368" alt="image" src="https://github.com/user-attachments/assets/068f9d8e-9386-4ac4-b2dc-b14ce7aa3b2d" />








### Adaptive Thresholding

<img width="424" height="365" alt="image" src="https://github.com/user-attachments/assets/07a0ad18-d482-42d7-846b-dbd9693e514e" />
<img width="431" height="367" alt="image" src="https://github.com/user-attachments/assets/dddf093d-15db-4235-9f88-9775739e0512" />



### Optimum Global Thesholding using Otsu's Method

<img width="426" height="364" alt="image" src="https://github.com/user-attachments/assets/2cd858f8-4744-4235-8d66-84b79c6ea2ca" />



## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
