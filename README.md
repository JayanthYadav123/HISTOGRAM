# Histogram and Histogram Equalization of an image
## Aim
To obtain a histogram for finding the frequency of pixels in an Image with pixel values ranging from 0 to 255. Also write the code using OpenCV to perform histogram equalization.

## Software Required:
Anaconda - Python 3.7

## Algorithm:

<b>Step1:</b> Import all the necessary libraries.

<b>Step2:</b> Read the images using imread() function.

<b>Step3:</b> Using calcHist() we can find the histogram of the images.

<b>Step4:</b> Using equalizeHist() we can equalize the image.

<b>Step5:</b> Using matplotlib.pyplot plot the histogram.

## Program:
```python
# Developed By: G Jayanth 
# Register Number: 212221230030
import cv2
import matplotlib.pyplot as plt

# Write your code to find the histogram of gray scale image and color image channels.

gray_image = cv2.imread("kitty.jpg")
color_image = cv2.imread("heist.jpg",-1)
cv2.imshow("Gray Image",gray_image)
cv2.imshow("Colour Image",color_image)
cv2.waitKey(0)
cv2.destroyAllWindows()

# Display the histogram of gray scale image and any one channel histogram from color image

grayscale_image=cv2.imread("kitty.jpg")
colourscale_image=cv2.imread("heist.jpg")
hist=cv2.calcHist(grayscale_image,[0],None,[255],[0,255])
hist1=cv2.calcHist(colourscale_image,[1],None,[255],[0,255])
plt.figure()
plt.title("Histogram")
plt.xlabel("grayscale")
plt.ylabel("pixel count")
plt.stem(hist)
plt.show()
plt.xlabel("colour scale")
plt.ylabel("pixel count")
plt.stem(hist1)
plt.show()


# code to perform histogram equalization of the image. 

gi=cv2.imread("kitty.jpg",0)
colorscale=cv2.imread("heist.jpg")
g=cv2.resize(gi,(500,400))
equ=cv2.equalizeHist(gi)
cv2.imshow("Grey Scale",g)
cv2.imshow("Equalization",equ)
cv2.waitKey(0)
cv2.destroyAllWindows()

```
## Output:
### Input Grayscale Image and Color Image

<img width="137" alt="Gray" src="https://github.com/JayanthYadav123/HISTOGRAM/assets/94836154/89051a3d-cf7d-4c77-a228-80dd4dd51612">

<img width="152" alt="Colour" src="https://github.com/JayanthYadav123/HISTOGRAM/assets/94836154/c7cc405e-f29e-41b3-a071-3ba12ad6c2bb">


### Histogram of Grayscale Image and any channel of Color Image

<img width="271" alt="Histo" src="https://github.com/JayanthYadav123/HISTOGRAM/assets/94836154/239e1c02-920c-413b-a76f-85865d31a3ae">

### Histogram Equalization of Grayscale Image

<img width="200" alt="gr" src="https://github.com/JayanthYadav123/HISTOGRAM/assets/94836154/870e171c-9f1c-47e4-acd5-a714182dcc7a">

<img width="139" alt="equ" src="https://github.com/JayanthYadav123/HISTOGRAM/assets/94836154/dc9543ae-cc96-4805-a67e-1be0ae26c330">


## Result: 
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
