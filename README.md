# EX-08 THRESHOLDING

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
```
DEVELOPED BY: NIRAUNJANA GAYATHRI G R
REGISTER NO: 212222230096
```
### Load the necessary packages
```
import numpy as np
import matplotlib.pyplot as plt
import cv2
```
### Read the Image and convert to grayscale
```
image = cv2.imread("cyc.jpg",1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread("cyc.jpg",0)
```
### Use Global thresholding to segment the image
```
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```
### Use Adaptive thresholding to segment the image
```
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```
### Use Otsu's method to segment the image 
```
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```
### Display the results
```
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

![image](https://github.com/niraunjana/THRESHOLDING-/assets/119395610/c9d5ee4e-4caa-4fcb-aa3a-707626b0c3da)

### Global Thresholding

![image](https://github.com/niraunjana/THRESHOLDING-/assets/119395610/8f6e083b-90fc-4906-9536-d11cbf18c5df)

![image](https://github.com/niraunjana/THRESHOLDING-/assets/119395610/475b3af6-59c0-40d8-b749-08b302006055)

![image](https://github.com/niraunjana/THRESHOLDING-/assets/119395610/0db9ab01-da21-4e77-9dfc-7bf7705f9527)

![image](https://github.com/niraunjana/THRESHOLDING-/assets/119395610/21fd265c-5f9a-4f43-af1d-809ad1af3fae)

![image](https://github.com/niraunjana/THRESHOLDING-/assets/119395610/9371c593-0dad-4180-9c44-54d848b8d531)


### Adaptive Thresholding

![image](https://github.com/niraunjana/THRESHOLDING-/assets/119395610/83705a0c-ae9a-4c37-90c5-4b06368c0b74)

![image](https://github.com/niraunjana/THRESHOLDING-/assets/119395610/9e9216fa-c825-42a6-bc2e-99ab2f2283cc)


### Optimum Global Thesholding using Otsu's Method

![image](https://github.com/niraunjana/THRESHOLDING-/assets/119395610/44a61fc3-a06f-4510-a7fb-0bd8726e2bf0)


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
