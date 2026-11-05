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
<img width="412" height="467" alt="image" src="https://github.com/user-attachments/assets/d93725a2-65be-49e5-b1e4-eec5c040e980" />
<img width="398" height="447" alt="image" src="https://github.com/user-attachments/assets/4d211b88-1961-49ca-8766-b9bea5aa0844" />
<img width="417" height="470" alt="image" src="https://github.com/user-attachments/assets/0b92866d-1afc-4094-aee9-b0a15aca4084" />
<img width="386" height="451" alt="image" src="https://github.com/user-attachments/assets/427bd04a-6e7c-4243-a5cc-a6d3e4299ce5" />
<img width="405" height="453" alt="image" src="https://github.com/user-attachments/assets/eae9aca6-5513-41a6-8695-51e240cb6882" />
<img width="395" height="456" alt="image" src="https://github.com/user-attachments/assets/2c839ccd-f23d-42ae-a97c-4d9c3e20ff46" />
<img width="398" height="452" alt="image" src="https://github.com/user-attachments/assets/e9a05742-f35c-4791-b6f7-6376611e1dd2" />
<img width="391" height="450" alt="image" src="https://github.com/user-attachments/assets/e60249c3-55d4-45ea-8322-55803a6b4bce" />
<img width="387" height="451" alt="image" src="https://github.com/user-attachments/assets/7cb22400-d97c-4b8a-8971-de5af08ad5e8" />
<img width="392" height="443" alt="image" src="https://github.com/user-attachments/assets/2fc2bbf2-8b1c-42ea-844f-8df102928ebc" />
<img width="393" height="447" alt="image" src="https://github.com/user-attachments/assets/55802b03-f9bf-4d77-a475-0ee68f1a299d" />
<img width="548" height="447" alt="image" src="https://github.com/user-attachments/assets/2130d5fc-8b5b-48fc-81ac-a745127febee" />












## Result:
Thus, the images were read, displayed, brightness and contrast adjustments were made, and bitwise operations were performed successfully using the Python program.


