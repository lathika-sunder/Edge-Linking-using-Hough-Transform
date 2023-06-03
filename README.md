# Edge-Linking-using-Hough-Transform
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import all the necessary modules for the program.

### Step2:
Load a image using imread() from cv2 module.

### Step3:
Convert the image to grayscale.

### Step4:
Using Canny operator from cv2,detect the edges of the image.

### Step5:
Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.


## Program:

```
Lathika Sunder
212221230054
```
```Python

# Read image and convert it to grayscale image
import cv2
import numpy as np
import matplotlib.pyplot as plt
BGR_image=cv2.imread('chess.png')
gray=cv2.cvtColor(BGR_image,cv2.COLOR_BGR2GRAY)
img= cv2.GaussianBlur(BGR_image,(3,3),0)
plt.imshow(img)


# Find the edges in the image using canny detector and display
edges1 = cv2.Canny(img,100,200)
plt.imshow(edges1,cmap = 'gray')
plt.title('Edge Image'), plt.xticks([]), plt.yticks([])
plt.show()


# Detect points that form a line using HoughLinesP

lines=cv2.HoughLinesP(edges1,1,np.pi/180, threshold=80, minLineLength=50,maxLineGap=250)

# Draw lines on the image

for line in lines:
    x1, y1, x2, y2 = line [0] 
    cv2.line(BGR_image,(x1, y1),(x2, y2),(210,100,200),3)

# Display the result
plt.imshow(BGR_image)



```
## Output

### Input image and grayscale image
![image](https://github.com/lathika-sunder/Edge-Linking-using-Hough-Transform/assets/95066409/169f4ad6-1169-4539-bb2d-08ceae822f28)

### Canny Edge detector output

![image](https://github.com/lathika-sunder/Edge-Linking-using-Hough-Transform/assets/95066409/dc2f707f-4b87-4299-86ed-ed0d74c05e22)

### Display the result of Hough transform

![image](https://github.com/lathika-sunder/Edge-Linking-using-Hough-Transform/assets/95066409/45c23e1b-6e59-4841-976a-95b927830cf8)

## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform. 
