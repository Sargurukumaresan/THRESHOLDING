# THRESHOLDING

## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
Import the necessary packages.

### Step2:
Create the text using cv2.putText.

### Step3:
Create the structuring element.

### Step4:
Erode the image using cv2.erode().

### Step5:
Dilate the imge using cv2.dilate().

## Program

```
DEVELOPED BY:SARGURU.K
REGISTER NUMBER:212222230134
```
# Load the necessary packages
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
```

# Read the Image and convert to grayscale
```
image=cv2.imread("dip4.jpg")
plt.imshow(image)
plt.title('original image')
plt.axis('off')
gray_img=cv2.cvtColor(image,cv2.COLOR_BGR2GRAY)
plt.imshow(gray_img,'gray')
plt.title('Gray image')
plt.axis('off')
```

# Use Global thresholding to segment the image
```
ret,thresh_img1=cv2.threshold(gray_img,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(gray_img,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(gray_img,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(gray_img,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(gray_img,100,255,cv2.THRESH_TRUNC)
```

# Use Adaptive thresholding to segment the image
```
thresh_img7=cv2.adaptiveThreshold(gray_img,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(gray_img,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```

# Use Otsu's method to segment the image 
```
ret,thresh_img6=cv2.threshold(gray_img,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```

# Display the results
```
titles=["Gray Image", "Threshold Image (Binary)", "Threshold Image (Binary Inverse)", "Threshold Image (To Zero)"
       , "Threshold Image (To Zero-Inverse)", "Threshold Image (Truncate)", "Otsu", "Adaptive Threshold (Mean)", "Adaptive Threshold (Gaussian)"]
images=[gray_img, thresh_img1, thresh_img2, thresh_img3, thresh_img4, thresh_img5, thresh_img6, thresh_img7, thresh_img8] 

for i in range(0,9):
    plt.figure(figsize=(5,5))
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
![Screenshot from 2023-09-26 22-32-00](https://github.com/Dhanudhanaraj/THRESHOLDING/assets/119218812/59cd3c56-12e2-4f8a-b032-9c71966bc8a8)


### Global Thresholding
![Screenshot from 2023-09-26 22-32-23](https://github.com/Dhanudhanaraj/THRESHOLDING/assets/119218812/94b8a75b-f00e-478a-8f34-d8c5464b1b08)


### Adaptive Thresholding

![Screenshot from 2023-09-26 22-32-55](https://github.com/Dhanudhanaraj/THRESHOLDING/assets/119218812/cc02cef3-e2db-4a7f-a3bd-8ee4b0ebd5db)


### Optimum Global Thesholding using Otsu's Method
![Screenshot from 2023-09-26 22-32-41](https://github.com/Dhanudhanaraj/THRESHOLDING/assets/119218812/0856b94a-ff79-48b6-b47a-ba6366622496)


## Result

Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
