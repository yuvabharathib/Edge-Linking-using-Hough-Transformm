# Edge-Linking-using-Hough-Transformm
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

Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.

## DEVELOPED BY: Yuvabharathi.B
## REG NO: 212222230181
## Output
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('HappyFish.jpg')  # Replace with your image path

# Detect lines using the probabilistic Hough transform
lines = cv2.HoughLinesP(edges, rho=1, theta=np.pi/180, threshold=100, minLineLength=50, maxLineGap=10)

# Draw the lines on the original image
output_image = image.copy()

if lines is not None:
    for line in lines:
        x1, y1, x2, y2 = line[0]
        cv2.line(output_image, (x1, y1), (x2, y2), (0, 255, 0), 2)


# Displaying results using Matplotlib
plt.figure(figsize=(12, 12))

# Input Image and Grayscale Image
plt.subplot(2, 2, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Input Image')
plt.axis('off')


```
![Screenshot 2024-10-15 190000](https://github.com/user-attachments/assets/db09cf30-fc8c-4f5e-9461-f371d6d55918)

### Input image and grayscale image
```
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.subplot(2, 2, 2)
plt.imshow(gray_image, cmap='gray')
plt.title('Grayscale Image')
plt.axis('off')

```

![Screenshot 2024-10-15 185952](https://github.com/user-attachments/assets/a3634d7b-bd4b-4318-a1d9-61d2c3c41662)

### Canny Edge detector output
```
edges = cv2.Canny(gray_image, 50, 150, apertureSize=3)
plt.subplot(2, 2, 3)
plt.imshow(edges, cmap='gray')
plt.title('Canny Edge Detector Output')
plt.axis('off')
```

![Screenshot 2024-10-15 185946](https://github.com/user-attachments/assets/4711f4f4-5136-4ba7-9026-8357d2eeaf18)


### Display the result of Hough transform
```

# Hough Transform Result
plt.subplot(2, 2, 4)
plt.imshow(cv2.cvtColor(output_image, cv2.COLOR_BGR2RGB))
plt.title('Hough Transform - Line Detection')
plt.axis('off')

# Display all results
plt.show()

```
![Screenshot 2024-10-15 185937](https://github.com/user-attachments/assets/ae0c4b65-4123-44d5-b4ea-902c237b0783)

## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform.
