# Histogram-of-an-images
## Aim
To obtain a histogram for finding the frequency of pixels in an Image with pixel values ranging from 0 to 255. Also write the code using OpenCV to perform histogram equalization.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Read the gray and color image using imread()

### Step2:
Print the image using imshow().



### Step3:
Use calcHist() function to mark the image in graph frequency for gray and color image.

### step4:
Use calcHist() function to mark the image in graph frequency for gray and color image.

### Step5:
The Histogram of gray scale image and color image is shown.


## Program:
```
# Developed By: Pradeep kumar G
# Register Number: 212223230150
```
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

## Find the histogram of gray scale image and color image channels

clr_img = cv2.imread('lion.png')
clr_img = cv2.cvtColor(clr_img, cv2.COLOR_BGR2RGB)

gray_img = cv2.imread('lion.png', cv2.IMREAD_GRAYSCALE)

plt.figure(figsize = (16,8))
plt.subplot(221); plt.imshow(gray_img, cmap = 'gray'); plt.title('Gray Image')
plt.subplot(222); plt.imshow(clr_img,); plt.title('Color Image')

# histogram of 'r' channel of color image
color_hist = cv2.calcHist([clr_img], [0], None, [256], [0, 256]) # rgb_img -- r(0) g(1) b(2)

# histogram of gray image
gray_hist = cv2.calcHist([gray_img], [0], None, [256], [0, 256])


## Display the histogram of gray scale image and any one channel histogram from color image

# gray image
plt.figure(figsize=(6, 4))
plt.title("Gray Image Histogram")
plt.xlabel("Intensity (0-255)")
plt.ylabel("Frequency")
plt.plot(gray_hist, color='black')
plt.xlim([0, 256])
plt.show()

# color image
plt.figure(figsize=(6, 4))
plt.title("Color Image Histogram")
plt.xlabel("Intensity (0-255)")
plt.ylabel("Frequency")
plt.plot(gray_hist, color='r')
plt.xlim([0, 256])
plt.show()



## Perform histogram equalization of the image. 

# Display the images.
img_eq = cv2.equalizeHist(gray_img)

hist_equalized = cv2.calcHist([img_eq], [0], None, [256], [0, 256])

plt.figure(figsize = (16,8))
plt.subplot(221); plt.imshow(gray_img, cmap = 'gray'); plt.title('Original Gray Image')
plt.subplot(222); plt.imshow(img_eq, cmap = 'gray'); plt.title('Equalized Image')

plt.figure(figsize=(6, 4))
plt.title("Equalized Image Histogram")
plt.xlabel("Intensity (0-255)")
plt.ylabel("Frequency")
plt.plot(hist_equalized, color='black')
plt.xlim([0, 256])
plt.show()

```
# Output:

## 1) Input Grayscale Image and Color Image
   
<img width="1374" height="448" alt="image" src="https://github.com/user-attachments/assets/888eb987-2a2d-4666-91af-8ce6e6fcd97a" />


## 2) Histogram of Grayscale Image and any channel of Color Image

### i) Gray Image Histogram
<img width="778" height="498" alt="image" src="https://github.com/user-attachments/assets/c5268415-7172-4a8d-b741-200144c10c1f" />

### ii) Color Image Histogram (Red Channel)
<img width="781" height="502" alt="image" src="https://github.com/user-attachments/assets/cc5fc35a-5a30-4015-84de-b88c81a5b642" />


## 3) Histogram Equalization of Grayscale Image.
   
### i) Equalized Image

<img width="1381" height="442" alt="image" src="https://github.com/user-attachments/assets/f3049e1c-4ad6-400b-9eef-08faec883df3" />

### ii) Equalization Histogram

<img width="782" height="521" alt="image" src="https://github.com/user-attachments/assets/6b8c4cf8-b71a-4176-9fe4-a212a18cccc8" />

## Result: 
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
