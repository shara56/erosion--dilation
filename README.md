
# Implementation-of-Erosion-and-Dilation
## Aim
To implement Erosion and Dilation using Python and OpenCV.
## Software Required
1. Anaconda - Python 3.7
2. OpenCV
## Algorithm:
### Step1:
Apply the dilation operation on the image using cv2.dilate() with the same structuring element. Dilation will increase the size of the white regions (text) in the image, effectively reversing the effect of erosion

### Step2:
Initialize a blank image (100 pixels high and 400 pixels wide) using NumPy. The image should be a single-channel (grayscale) array filled with zeros (black).

### Step3:
Use OpenCV's cv2.putText() function to overlay the text "HYCINTH" on the blank image. Define the font style, position, font scale, color, and thickness for rendering the text.

### Step4:
Specify the size of the structuring element (e.g., 5x5 pixels) and create a rectangular structuring element using cv2.getStructuringElement(). This element will be used for the morphological operations.

### Step5:
Apply the erosion operation on the image using cv2.erode() with the defined structuring element. Erosion will reduce the size of the white regions (text) in the image.

```
DEVELOPED BY : Sharangini T K
REGISTER NO: 212222230143
```
## Program:
# Import the necessary packages
``` Python
import cv2
import matplotlib.pyplot as plt

# Create a blank image (100 pixels high and 400 pixels wide)
img = np.zeros((100, 400), dtype='uint8')
```
# Create the Text using cv2.putText
```
# Put some text on the image for demonstration
cv2.putText(img, 'SHARA', (60, 70), cv2.FONT_HERSHEY_SIMPLEX, 2, (255), 5)
```

# Create the structuring element
```
# Create a rectangular structuring element
kernel_size = (5, 5)  # Width and height of the kernel
structuring_element = cv2.getStructuringElement(cv2.MORPH_RECT, kernel_size)

# Perform Erosion
eroded_image = cv2.erode(img, structuring_element, iterations=1)

# Perform Dilation
dilated_image = cv2.dilate(img, structuring_element, iterations=1)

# Display the original, eroded, and dilated images
plt.figure(figsize=(15, 5))
```
# Original Image
```
# Original Image

plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.axis('off')

plt.show()
```
![Screenshot 2024-11-16 210237](https://github.com/user-attachments/assets/23c731ab-a9dc-4697-9bdd-2c0711a613a3)
# Erode the image
```
plt.figure(figsize=(15, 5))
# Eroded Image
plt.imshow(eroded_image, cmap='gray')
plt.title('Eroded Image')
plt.axis('off')
```
![Screenshot 2024-11-16 210338](https://github.com/user-attachments/assets/c4fd5718-1d53-499e-8bf6-fd3b5d965546)
# Dilate the image
```
plt.figure(figsize=(15, 5))
# Dilated Image
plt.imshow(dilated_image, cmap='gray')
plt.title('Dilated Image')
plt.axis('off')
```
![Screenshot 2024-11-16 210406](https://github.com/user-attachments/assets/bf290115-0a89-47e3-92c0-c6b51fb6ce0a)
## Result
Thus the generated text image is eroded and dilated using python and OpenCV.
