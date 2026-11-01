# DIPT-EXP-1

# Developed by: Nara Guna Susmitha
# Reg no: 212224230176

Image-Handling-and-Pixel-Transformations-Using-OpenCV
# AIM:
Write a Python program using OpenCV that performs the following tasks:

# Read and Display an Image.
Adjust the brightness of an image.
Modify the image contrast.
Generate a third image using bitwise operations.
# Software Required:
Anaconda - Python 3.7
Jupyter Notebook (for interactive development and execution)
# Algorithm:
Step 1:
Load an image from your local directory and display it.

Step 2:
o Draw a line from the top-left to the bottom-right of the image. o Draw a circle at the center of the image. o Draw a rectangle around a specific region of interest in the image. o Add the text "OpenCV Drawing" at the top-left corner of the image.

Step 3:
o Convert the image from RGB to HSV and display it. o Convert the image from RGB to GRAY and display it. o Convert the image from RGB to YCrCb and display it.
o Convert the HSV image back to RGB and display it.

Step 4:
o Access and print the value of the pixel at coordinates (100, 100). o Modify the color of the pixel at (200, 200) to white.

Step 5:
o Resize the original image to half its size and display it.

Step6:
o Crop a region of interest (ROI) from the image (e.g., a 100x100 pixel area starting at (50, 50)) and display it.

Step7:
o Flip the original image horizontally and display it. o Flip the original image vertically and display it.

Step8:
o Save the final modified image to your local directory.

# Ex. No. 01

# Import neccessary libraries

import cv2
import matplotlib.pyplot as plt

# Read the image using OpenCV

img = cv2.imread('Qno. 1.jpg', cv2.IMREAD_COLOR)

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)

img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

# Display the image using Matplotlib

plt.imshow(img_rgb, cmap='viridis')  # You can change 'viridis' to another cmap or use None for RGB images
plt.title("Original Image")
plt.axis('off')  # Removes axis ticks and labels
plt.show()

# Load the image

image = cv2.imread('Qno. 1.jpg') 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)

img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

# Shape 

img_rgb.shape

# Draw a line from top-left to bottom-right

line_img = cv2.line(img_rgb, (0, 0), (768, 600), (255, 0, 0), 2) # cv2.line(image, start_point, end_point, color, thickness)

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)

plt.imshow(line_img, cmap='viridis')  
plt.title("Image with Line")
plt.axis('off')  
plt.show()

# Load the image
image = cv2.imread('Qno. 1.jpg') 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img_rgb.shape
circle_img = cv2.circle(img_rgb,(400,300),150,(255,0,0),10) # cv2.circle(image, center, radius, color, thickness)
plt.imshow(circle_img, cmap='viridis')  
plt.title("Image with Circle")
plt.axis('off')  
plt.show()

# Rectangle around  the whole image

# Load the image
image = cv2.imread('Qno. 1.jpg') 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

# Draw a rectangle around the Whole image
rectangle_img = cv2.rectangle(img_rgb, (0, 0), (768, 600), (0, 0, 255), 10)  # cv2.rectangle(image, start_point, end_point, color, thickness)
plt.imshow(rectangle_img, cmap='viridis')  
plt.title("Image with Rectangle")
plt.axis('off')  
plt.show()

# Text "OpenCV Drawing" at the top-left corner of the image.
# Load the image
image = cv2.imread('Qno. 1.jpg') 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)# Add text to the image
text_img = cv2.putText(img_rgb, "OpenCV Drawing", (10, 30), cv2.FONT_HERSHEY_SIMPLEX, 1, (255, 255, 255), 10)  ## cv2.putText(image, text, position, font, font_scale, color, thickness)
plt.imshow(text_img, cmap='viridis')  
plt.title("Image with Text")
plt.axis('off')  
plt.show()

# Load the image
image = cv2.imread('Qno. 1.jpg') 
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
# Original RGB Image
plt.imshow(image_rgb)
plt.title("Original RGB Image")
plt.axis("off")

# Convert RGB to HSV
image_hsv = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2HSV)
# HSV Image
plt.imshow(image_hsv)
plt.title("HSV Image")
plt.axis("off")
# Convert RGB to GRAY
image_gray = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2GRAY)
# Grayscale Image
plt.imshow(image_gray, cmap='gray')
plt.title("Grayscale Image")
plt.axis("off")
# Convert RGB to YCrCb
image_ycrcb = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2YCrCb)
# YCrCb Image
plt.imshow(image_ycrcb)
plt.title("YCrCb Image")
plt.axis("off")
# Convert HSV back to RGB
image_hsv_to_rgb = cv2.cvtColor(image_hsv, cv2.COLOR_HSV2RGB)
plt.imshow(image_hsv_to_rgb)
plt.title("HSV to RGB Image")
plt.axis("off")
# Convert BGR to RGB for displaying with Matplotlib
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
# Display the modified image
plt.imshow(image_rgb)
plt.title("Image with 300x300 White Block")
plt.axis("off")
plt.show()
# Load the image
image = cv2.imread('Qno. 1.jpg') 
image.shape
# Resize the image to half its size
resized_image = cv2.resize(image, (768 // 2, 600 // 2))  # (new_width, new_height)
# Convert BGR to RGB for displaying with Matplotlib
resized_image_rgb = cv2.cvtColor(resized_image, cv2.COLOR_BGR2RGB)
resized_image_rgb.shape
# Display the resized image
plt.imshow(resized_image_rgb)
plt.title("Resized Image (Half Size)")
plt.axis("off")
plt.show()
# Load the image
image = cv2.imread('Qno. 1.jpg') 
image.shape
# Crop a 300x300 region starting from (50, 50)
roi = image[50:350, 50:350]  # Rows: 50-349, Columns: 50-349
# Convert BGR to RGB for displaying with Matplotlib
roi_rgb = cv2.cvtColor(roi, cv2.COLOR_BGR2RGB)
# Display the cropped region (ROI)
plt.imshow(roi_rgb)
plt.title("Cropped Region of Interest (ROI)")
plt.axis("off")
plt.show()
# Flip the original image horizontally and display it. 
# Load the image
image = cv2.imread('Qno. 1.jpg') 
# Flip the image horizontally (left-right)
flipped_horizontally = cv2.flip(image, 1)
# Convert BGR to RGB for displaying with Matplotlib
flipped_horizontally_rgb = cv2.cvtColor(flipped_horizontally, cv2.COLOR_BGR2RGB)
# Horizontal flip
plt.imshow(flipped_horizontally_rgb)
plt.title("Flipped Horizontally")
plt.axis("off")# Flip the image vertically (up-down)
flipped_vertically = cv2.flip(image, 0)
# Convert BGR to RGB for displaying with Matplotlib
flipped_vertically_rgb = cv2.cvtColor(flipped_vertically, cv2.COLOR_BGR2RGB)
# Vertical flip
plt.imshow(flipped_vertically_rgb)
plt.title("Flipped Vertically")
plt.axis("off")

# Output:
```
```
<img width="433" height="505" alt="image" src="https://github.com/user-attachments/assets/54bc1848-26d7-4ab2-a26b-5bd19a45dc89" />
```
```
<img width="436" height="503" alt="image" src="https://github.com/user-attachments/assets/1c86a862-0301-4e14-ad13-e29c074bd229" />
```
```
<img width="433" height="503" alt="image" src="https://github.com/user-attachments/assets/c6abd343-c476-4b2d-a06e-f6dbccc265af" />
```
```
<img width="433" height="502" alt="image" src="https://github.com/user-attachments/assets/b2a54980-1af8-4ad0-bd16-727190e74e87" />
```
```
<img width="432" height="498" alt="image" src="https://github.com/user-attachments/assets/ced5509f-6579-4a7d-8005-8d588a0280e0" />
```
```
<img width="435" height="502" alt="image" src="https://github.com/user-attachments/assets/c6ec8a18-1ffd-47be-a71b-94d5097bee26" />
```
```
<img width="435" height="497" alt="image" src="https://github.com/user-attachments/assets/9677de86-2612-4819-845a-0568eda7fda3" />
```
```
<img width="440" height="501" alt="image" src="https://github.com/user-attachments/assets/77ba8bee-ecb2-4a6a-96c1-b5c7ae574c25" />
```
```
<img width="433" height="497" alt="image" src="https://github.com/user-attachments/assets/ca5be190-ad7a-48f3-92b9-411c47573eaa" />
```
```
<img width="432" height="497" alt="image" src="https://github.com/user-attachments/assets/9d02f567-38f1-48f4-ad6a-43820f6d0e98" />
```
```
<img width="433" height="501" alt="image" src="https://github.com/user-attachments/assets/edfd3409-374a-451c-8ffd-a62656e7b7c4" />
```
```
<img width="605" height="500" alt="image" src="https://github.com/user-attachments/assets/eb8101fe-6ce0-4e30-a43f-af2fe5d1b792" />
```
```
<img width="482" height="506" alt="image" src="https://github.com/user-attachments/assets/3c50969d-29c6-4c81-8afc-a5bc87e2065a" />
```
```
<img width="438" height="507" alt="image" src="https://github.com/user-attachments/assets/3dffa413-01a3-4d81-9309-1b25d6072db4" />
```
```
# Result:

Thus, the images were read, displayed, brightness and contrast adjustments were made, and bitwise operations were performed successfully using the Python program.















