Exp.No : 04 
&emsp;
&emsp;
&emsp;
&emsp;
&emsp;
&emsp;
&emsp;
&emsp;
&emsp;
&emsp;
&emsp;
&emsp;
&emsp;
&emsp;
&emsp;
&emsp;
&emsp;
&emsp;
&emsp;
&emsp;
&emsp;
&emsp;
Date : 30.03.2023 
<br>

# Histogram and Histogram Equalization of an image
## Aim
To obtain a histogram for finding the frequency of pixels in an Image with pixel values ranging from 0 to 255. Also write the code using OpenCV to perform histogram equalization.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
- **Step1:** Read the gray and color image using imread()
- **Step2:** Print the image using imshow().
- **Step3:** Use calcHist() function to mark the image in graph frequency for gray and color image.
- **Step4:** cv2.equalize() is used to transform the gray image to equalized form.
- **Step5:** The Histogram of gray scale image and color image is shown.

## Program:
> Developed By: Kaushika A <br>
> Register Number: 212221230048

```python
# Write your code to find the histogram of gray scale image and color image channels.
import cv2
import matplotlib.pyplot as plt

gray=cv2.imread("grey_referece.PNG",0)
gray= cv2.resize(gray, (627,403))
cv2.imshow('gray image',gray)

color=cv2.imread("color_reference.PNG",1)
color= cv2.resize(color, (627,415))
cv2.imshow('color image',color)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
```python
# Display the histogram of gray scale image and any one channel histogram from color image
gray_hist=cv2.calcHist([gray],[0],None,[256],[0,255])
color_hist=cv2.calcHist([color],[2],None,[256],[0,255])

plt.figure()
plt.title("gray image")
plt.xlabel("grayscale value")
plt.ylabel("pixel count")
plt.stem(gray_hist)
plt.show()

plt.figure()
plt.title("color image")
plt.xlabel("colorscale value")
plt.ylabel("pixel count")
plt.stem(color_hist)
plt.show()

```
```python
# Write the code to perform histogram equalization of the image. 
gray_equalized=cv2.equalizeHist(gray)

cv2.imshow('gray image',gray)
cv2.imshow('equalized gray image',gray_equalized)
cv2.waitKey(0)
cv2.destroyAllWindows()

```
## Output:
#### Input Grayscale Image and Color Image
<img src="https://github.com/Kaushika-Anandh/Histogram-of-an-image/blob/main/1.PNG" width="600" height="250">
<br>


#### Histogram of Grayscale Image and any channel of Color Image
<img src="https://github.com/Kaushika-Anandh/Histogram-of-an-image/blob/main/2.png" width="300" height="270">

<img src="https://github.com/Kaushika-Anandh/Histogram-of-an-image/blob/main/3.png" width="300" height="270">


#### Histogram Equalization of Grayscale Image
<img src="https://github.com/Kaushika-Anandh/Histogram-of-an-image/blob/main/4.PNG" width="600" height="250">
<br>


## Result: 
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
