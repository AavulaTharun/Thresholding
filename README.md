# Thresholding of Images
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

Step 1:
Load the necessary packages.

Step 2:
Read the Image and convert to grayscale.

Step 3:
Use Global thresholding to segment the image.

Step 4:
Use Adaptive thresholding to segment the image.

Step 5:
Use Otsu's method to segment the image.

Step 6:
Display the results.

## Program

```

import cv2
import matplotlib.pyplot as plt
image = cv2.imread("mountain.jpg")


# Read the Image and convert to grayscale

grayImage = cv2.cvtColor(image,cv2.COLOR_BGR2GRAY)


# Use Global thresholding to segment the image


ret,thresh = cv2.threshold(grayImage,100,200,cv2.THRESH_BINARY)
ret1,thresh1 = cv2.threshold(grayImage,100,200,cv2.THRESH_BINARY_INV)
ret2, thresh2 = cv2.threshold(grayImage,100,200,cv2.THRESH_TRUNC)
ret3, thresh3 = cv2.threshold(grayImage,100,200,cv2.THRESH_TOZERO)
ret4, thresh4 = cv2.threshold(grayImage,100,200,cv2.THRESH_TOZERO_INV)





# Use Adaptive thresholding to segment the image

th1 = cv2.adaptiveThreshold(grayImage,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
th2 = cv2.adaptiveThreshold(grayImage,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
titles = ["Original Image","Adaptive Mean Thresholding","Adaptive Gaussian Thresholding"]
imgs = [grayImage,th1,th2]




# Use Otsu's method to segment the image 
ret5,th3 = cv2.threshold(grayImage,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)



# Display the results

cv2.imshow("Original Image",image)
cv2.imshow("Gray Image",grayImage)
cv2.imshow("THRESH_BINARY",thresh)
cv2.imshow("THRESH_BINARY_INV",thresh1)
cv2.imshow("THRESH_TRUNC",thresh2)
cv2.imshow("THRESH_TOZERO",thresh3)
cv2.imshow("THRESH_TOZERO_INV",thresh4)

for i in range(3):
    plt.subplot(3,1,i+1)
    plt.imshow(imgs[i],'gray')
    plt.title(titles[i])
    plt.xticks([]),plt.yticks([])
plt.show()


cv2.imshow("Otsu method",th3)



```
## Output

### Original Image

![ex-09 1](https://user-images.githubusercontent.com/93427201/171139997-21580a52-4fda-4edb-b96e-ea066abbb28a.jpeg)

![ex-09 2](https://user-images.githubusercontent.com/93427201/171140005-58a5e271-22b5-4bf6-8c71-2c2e68ac734e.jpeg)

### Global Thresholding

![ex-09 3](https://user-images.githubusercontent.com/93427201/171140071-9034aacf-6e8b-40da-9dd6-cd56babce146.jpeg)
![ex-09 4](https://user-images.githubusercontent.com/93427201/171140096-9f733481-e5f5-43a5-98c5-9017172b0b16.jpeg)
![ex-09 5](https://user-images.githubusercontent.com/93427201/171140110-a820b551-2532-4587-b36f-ee6bae363c45.jpeg)


### Adaptive Thresholding

![ex-09 6](https://user-images.githubusercontent.com/93427201/171140209-63c5e6e2-88b5-47b7-9a79-1831f259d60c.jpeg)


![ex-09 7](https://user-images.githubusercontent.com/93427201/171140210-6934b739-c338-48e2-810b-55904ea48299.jpeg)


### Optimum Global Thesholding using Otsu's Method

![ex-09 8](https://user-images.githubusercontent.com/93427201/171140235-16c6d372-af00-4ec8-83a0-27349b2298e1.jpeg)


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

