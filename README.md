# Image-Handling-and-Pixel-Transformations-Using-OpenCV 

## Program Developed By:
- # Name: Nara Guna Susmitha
  # Register Number: 212224230176

## AIM:
Write a Python program using OpenCV that performs the following tasks:

1) Read and Display an Image.  
2) Adjust the brightness of an image.  
3) Modify the image contrast.  
4) Generate a third image using bitwise operations.

## Software Required:
- Anaconda - Python 3.7
- Jupyter Notebook (for interactive development and execution)

## Algorithm:
### Step 1:
Load an image from your local directory and display it.

### Step 2:
o Draw a line from the top-left to the bottom-right of the image.
o Draw a circle at the center of the image. 
o Draw a rectangle around a specific region of interest in the image. 
o Add the text "OpenCV Drawing" at the top-left corner of the image.

### Step 3:
o Convert the image from RGB to HSV and display it.
o Convert the image from RGB to GRAY and display it. 
o Convert the image from RGB to YCrCb and display it.  
o Convert the HSV image back to RGB and display it.

### Step 4:
o Access and print the value of the pixel at coordinates (100, 100). 
o Modify the color of the pixel at (200, 200) to white.

### Step 5:
o Resize the original image to half its size and display it.

### Step6:
o Crop a region of interest (ROI) from the image (e.g., a 100x100 pixel area starting at (50, 50)) and display it.

### Step7:
o Flip the original image horizontally and display it. 
o Flip the original image vertically and display it.

### Step8:
o Save the final modified image to your local directory.

## Ex. No. 01

### Import neccessary libraries
        import cv2
        import matplotlib.pyplot as plt
### Read the image using OpenCV
    img = cv2.imread('Qno. 1.jpg', cv2.IMREAD_COLOR)
### Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
    img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

    ### Display the image using Matplotlib
    plt.imshow(img_rgb, cmap='viridis')  # You can change 'viridis' to another cmap or use None for RGB images
    plt.title("Original Image")
    plt.axis('off')  # Removes axis ticks and labels
    plt.show()
### Load the image
    image = cv2.imread('Qno. 1.jpg') 
### Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
    img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
    img_rgb.shape
### Draw a line from top-left to bottom-right
    line_img = cv2.line(img_rgb, (0, 0), (768, 600), (255, 0, 0), 2) # cv2.line(image, start_point, end_point, color, thickness)
    plt.imshow(line_img, cmap='viridis')  
    plt.title("Image with Line")
    plt.axis('off')  
    plt.show()
    ### Load the image
    image = cv2.imread('Qno. 1.jpg') 
### Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
    img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
    img_rgb.shape
    circle_img = cv2.circle(img_rgb,(400,300),150,(255,0,0),10) # cv2.circle(image, center, radius, color, thickness)
    plt.imshow(circle_img, cmap='viridis')  
    plt.title("Image with Circle")
    plt.axis('off')  
    plt.show()
### Load the image
    image = cv2.imread('Qno. 1.jpg') 
### Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
    img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
      img.shape
### Draw a rectangle around the Whole image
    rectangle_img = cv2.rectangle(img_rgb, (0, 0), (768, 600), (0, 0, 255), 10)  # cv2.rectangle(image, start_point, end_point, color, thickness)
    plt.imshow(rectangle_img, cmap='viridis')  
    plt.title("Image with Rectangle")
    plt.axis('off')  
    plt.show()
### Load the image
    image = cv2.imread('Qno. 1.jpg') 
### Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
    img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
### Add text to the image
    text_img = cv2.putText(img_rgb, "OpenCV Drawing", (10, 30), cv2.FONT_HERSHEY_SIMPLEX, 1, (255, 255, 255), 10)  ## cv2.putText(image, text, position, font, font_scale, color, thickness)
    plt.imshow(text_img, cmap='viridis')  
    plt.title("Image with Text")
    plt.axis('off')
     plt.show()
### Load the image
    image = cv2.imread('Qno. 1.jpg') 
    image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
### Original RGB Image
        plt.imshow(image_rgb)
        plt.title("Original RGB Image")
        plt.axis("off")
### Convert RGB to HSV
        image_hsv = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2HSV)
### HSV Image
    plt.imshow(image_hsv)
    plt.title("HSV Image")
    plt.axis("off")
### Convert RGB to GRAY
    image_gray = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2GRAY)
### Grayscale Image
    plt.imshow(image_gray, cmap='gray')
    plt.title("Grayscale Image")
    plt.axis("off")
### Convert RGB to YCrCb
    image_ycrcb = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2YCrCb)
### YCrCb Image
    plt.imshow(image_ycrcb)
    plt.title("YCrCb Image")
    plt.axis("off")
### Convert HSV back to RGB
    image_hsv_to_rgb = cv2.cvtColor(image_hsv, cv2.COLOR_HSV2RGB)
    plt.imshow(image_hsv_to_rgb)
    plt.title("HSV to RGB Image")
    plt.axis("off")
### Modify a block of pixels (300x300) to white, starting from (200, 200)
    image[200:500, 200:500] = [255, 255, 255]  # Rows: 200-499, Columns: 200-499
### Display the modified image
    plt.imshow(image_rgb)
    plt.title("Image with 300x300 White Block")
    plt.axis("off")
     plt.show()
### Load the image
    image = cv2.imread('Qno. 1.jpg') 
    image.shape
### Resize the image to half its size
    resized_image = cv2.resize(image, (768 // 2, 600 // 2))  # (new_width, new_height)
### Convert BGR to RGB for displaying with Matplotlib
    resized_image_rgb = cv2.cvtColor(resized_image, cv2.COLOR_BGR2RGB)
    resized_image_rgb.shape
### Display the resized image
    plt.imshow(resized_image_rgb)
    plt.title("Resized Image (Half Size)")
    plt.axis("off")
    plt.show()
### Load the image
    image = cv2.imread('Qno. 1.jpg') 
    image.shape
    ### Crop a 300x300 region starting from (50, 50)
    roi = image[50:350, 50:350]  # Rows: 50-349, Columns: 50-349
### Convert BGR to RGB for displaying with Matplotlib
    roi_rgb = cv2.cvtColor(roi, cv2.COLOR_BGR2RGB)
### Display the cropped region (ROI)
    plt.imshow(roi_rgb)
    plt.title("Cropped Region of Interest (ROI)")
    plt.axis("off")
    plt.show()
### Load the image
    image = cv2.imread('Qno. 1.jpg') 
### Flip the image horizontally (left-right)
    flipped_horizontally = cv2.flip(image, 1)
### Convert BGR to RGB for displaying with Matplotlib
    flipped_horizontally_rgb = cv2.cvtColor(flipped_horizontally, cv2.COLOR_BGR2RGB)
### Horizontal flip
    plt.imshow(flipped_horizontally_rgb)
    plt.title("Flipped Horizontally")
    plt.axis("off")
### Flip the image vertically (up-down)
    flipped_vertically = cv2.flip(image, 0)
### Convert BGR to RGB for displaying with Matplotlib
    flipped_vertically_rgb = cv2.cvtColor(flipped_vertically, cv2.COLOR_BGR2RGB)
### Vertical flip
    plt.imshow(flipped_vertically_rgb)
    plt.title("Flipped Vertically")
     plt.axis("off")


## Output:
<img width="412" height="467" alt="image" src="https://github.com/user-attachments/assets/6cc2d171-262f-460e-af0a-17d347320412" />
<img width="398" height="447" alt="image" src="https://github.com/user-attachments/assets/2adca665-d90e-4562-89b5-64ce5df8b9c7" />
<img width="417" height="470" alt="image" src="https://github.com/user-attachments/assets/8cca89a6-adce-4c6e-97f9-85a316d5b66e" />
<img width="386" height="451" alt="image" src="https://github.com/user-attachments/assets/712d0a02-9b04-487d-ba05-96d369b05511" />
<img width="405" height="453" alt="image" src="https://github.com/user-attachments/assets/0a102026-480d-4f94-8a3c-2b3576eda7e2" />
<img width="395" height="456" alt="image" src="https://github.com/user-attachments/assets/143c1729-0f20-4050-b372-0d5280a30b9b" />
<img width="398" height="452" alt="image" src="https://github.com/user-attachments/assets/c395efab-f5be-4c2f-994d-ccde84f35967" />
<img width="391" height="450" alt="image" src="https://github.com/user-attachments/assets/1a8e111e-3d18-4641-9bb8-e03b1e9932b2" />
<img width="387" height="451" alt="image" src="https://github.com/user-attachments/assets/5c5398c4-5bef-4345-b33a-c35b458ec00e" />
<img width="392" height="443" alt="image" src="https://github.com/user-attachments/assets/d868e62e-8ae8-44e9-af48-493d56f89cb6" />
<img width="393" height="447" alt="image" src="https://github.com/user-attachments/assets/b2a8c917-eed3-45f8-9b85-088d465e9f3b" />
<img width="548" height="447" alt="image" src="https://github.com/user-attachments/assets/135224d5-90ac-4603-886b-1d62d2268fb0" />
<img width="436" height="447" alt="image" src="https://github.com/user-attachments/assets/280c501c-fd35-4d02-bf3e-7434e330e7f1" />
<img width="415" height="447" alt="image" src="https://github.com/user-attachments/assets/17079bc0-0a32-418e-979b-33dc052cc887" />
<img width="406" height="472" alt="image" src="https://github.com/user-attachments/assets/671e5ad6-1796-45fc-8bf2-18ac0c594d38" />
## Result:
Thus, the images were read, displayed, brightness and contrast adjustments were made, and bitwise operations were performed successfully using the Python program.


