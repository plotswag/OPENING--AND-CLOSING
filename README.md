# OPENING--AND-CLOSING
## Aim
To implement Opening and Closing using Python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV
## Algorithm:
### Step1:
Import the necessary packages


### Step2:
Create the Text using cv2.putText

### Step3:
Create the structuring element

### Step4:
Use Opening operation

### Step5:
Use Closing Operation

 
## Program:
```
Developed By : JEEVANESH
Reg no : 212222243002
```
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Step 1: Create a blank image
image = np.zeros((300, 600, 3), dtype="uint8")

# Step 2: Create the text using cv2.putText
text = "Jeevanesh"
font = cv2.FONT_HERSHEY_SIMPLEX
cv2.putText(image, text, (50, 150), font, 2, (255, 255, 255), 3)

# Step 3: Create a structuring element (5x5 rectangular)
kernel = cv2.getStructuringElement(cv2.MORPH_RECT, (5, 5))

# Step 4: Use Opening operation (erosion followed by dilation)
opening_image = cv2.morphologyEx(image, cv2.MORPH_OPEN, kernel)

# Step 5: Use Closing operation (dilation followed by erosion)
closing_image = cv2.morphologyEx(image, cv2.MORPH_CLOSE, kernel)

# Convert images from BGR to RGB for Matplotlib
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
opening_image_rgb = cv2.cvtColor(opening_image, cv2.COLOR_BGR2RGB)
closing_image_rgb = cv2.cvtColor(closing_image, cv2.COLOR_BGR2RGB)

# Plot the original, opening, and closing images using Matplotlib
plt.figure(figsize=(10, 5))

plt.subplot(1, 3, 1)
plt.imshow(image_rgb)
plt.title("Original Image")
plt.axis("off")

plt.subplot(1, 3, 2)
plt.imshow(opening_image_rgb)
plt.title("Opening Operation")
plt.axis("off")

plt.subplot(1, 3, 3)
plt.imshow(closing_image_rgb)
plt.title("Closing Operation")
plt.axis("off")

plt.tight_layout()
plt.show()


```
## Output:

### Display the input Image
![image](https://github.com/user-attachments/assets/c0b6710d-71e5-447a-83e2-28913ed49b8f)



### Display the result of Opening
![image](https://github.com/user-attachments/assets/f08fb4d8-db33-4ea5-99c9-08f6ba11fae2)




### Display the result of Closing
![image](https://github.com/user-attachments/assets/b418a6c1-79d7-474d-8ce4-5813a0a1cfe1)





## Result
Thus the Opening and Closing operation is used in the image using python and OpenCV.
