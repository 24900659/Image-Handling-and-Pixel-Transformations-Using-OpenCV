# Image-Handling-and-Pixel-Transformations-Using-OpenCV
Name: MOHANA K.V.S.L
Register Number: 212224240093
AIM

To perform image handling and pixel transformations using Python and OpenCV, including reading and displaying images, drawing shapes, adding text, color space conversion, pixel manipulation, image resizing, cropping, flipping, and saving the modified image.

SOFTWARE REQUIRED
```
Python
OpenCV
Matplotlib
Jupyter Notebook
Anaconda (optional)
```
INSTALLATION
```
Install the required libraries using the following command:

pip install opencv-contrib-python-headless matplotlib
```
ALGORITHM
```
Step 1: Read and Display an Image
Import OpenCV and Matplotlib libraries.
Read an image from the local directory using cv2.imread().
Convert the image from BGR to RGB.
Display the original image using Matplotlib.
Step 2: Draw Shapes and Add Text
Draw a line from the top-left to the bottom-right of the image.
Draw a circle at the center of the image.
Draw a rectangle around the image.
Add the text "OpenCV Drawing" at the top-left corner.
Step 3: Color Space Conversion
Convert the RGB image to HSV and display it.
Convert the RGB image to grayscale and display it.
Convert the RGB image to YCrCb and display it.
Convert the HSV image back to RGB and display it.
Step 4: Pixel Manipulation
Access and print the pixel value at coordinates (100, 100).
Change the pixel at coordinates (200, 200) to white.
Modify a 300 × 300 region of the image to white.
Display the modified image.
Step 5: Image Resizing
Read the original image.
Resize the image to half its original width and height.
Display the resized image.
Step 6: Image Cropping
Read the original image.
Extract a 300 × 300 region of interest starting at (50, 50).
Display the cropped image.
Step 7: Image Flipping
Flip the original image horizontally.
Flip the original image vertically.
Display both flipped images.
Step 8: Save the Final Modified Image
Save the modified image in the local directory using cv2.imwrite().
Verify that the image has been saved successfully.
```
PROGRAM
Step 1: Read and Display an Image
```
import cv2
import matplotlib.pyplot as plt

# Read the image using OpenCV
img = cv2.imread(r"C:\Users\admin\OneDrive\Desktop\ai assistant\WhatsApp Image 2026-10-30 at 8.45.52 AM.jpeg", cv2.IMREAD_COLOR)

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img,cv2.COLOR_BGR2RGB)

# Display the image using Matplotlib
plt.imshow(img_rgb, cmap='viridis')  # You can change 'viridis' to another cmap or use None for RGB images
plt.title("Original Image")
plt.axis('off')  # Removes axis ticks and labels
plt.show()
```
Step 2: Draw Shapes and Add Text
```
2.1 Draw a Line
# Load the image
image = cv2.imread(r"C:\Users\admin\OneDrive\Desktop\ai assistant\WhatsApp Image 2026-10-30 at 8.45.52 AM.jpeg") 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img_rgb.shape

# Draw a line from top-left to bottom-right
line_img = cv2.line(img_rgb, (0, 0), (768, 600), (255, 0, 0), 2) # cv2.line(image, start_point, end_point, color, thickness)

# Display the image
plt.imshow(line_img, cmap='viridis')  
plt.title("Image with Line")
plt.axis('off')  
plt.show()
2.2 Draw a Circle
# Load the image
image = cv2.imread(r"C:\Users\admin\OneDrive\Desktop\ai assistant\WhatsApp Image 2026-10-30 at 8.45.52 AM.jpeg") 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

img_rgb.shape

circle_img = cv2.circle(img_rgb,(400,300),150,(255,0,0),10) # cv2.circle(image, center, radius, color, thickness)

# Display the image
plt.imshow(circle_img, cmap='viridis')  
plt.title("Image with Circle")
plt.axis('off')  
plt.show()
2.3 Draw a Rectangle
# Load the image
image = cv2.imread(r"C:\Users\admin\OneDrive\Desktop\ai assistant\WhatsApp Image 2026-10-30 at 8.45.52 AM.jpeg") 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

img.shape

# Draw a rectangle around the Whole image
rectangle_img = cv2.rectangle(img_rgb, (0, 0), (768, 600), (0, 0, 255), 10)  # cv2.rectangle(image, start_point, end_point, color, thickness)

# Display the image
plt.imshow(rectangle_img, cmap='viridis')  
plt.title("Image with Rectangle")
plt.axis('off')  
plt.show()
2.4 Add Text to the Image
# Load the image
image = cv2.imread(r"C:\Users\admin\OneDrive\Desktop\ai assistant\WhatsApp Image 2026-10-30 at 8.45.52 AM.jpeg") 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

# Add text to the image
text_img = cv2.putText(img_rgb, "OpenCV Drawing", (10, 30), cv2.FONT_HERSHEY_SIMPLEX, 1, (255, 255, 255), 10)  ## cv2.putText(image, text, position, font, font_scale, color, thickness)


# Display the image
plt.imshow(text_img, cmap='viridis')  
plt.title("Image with Text")
plt.axis('off')  
plt.show()
```
Step 3: Color Space Conversion
```
# Load the image
image = cv2.imread(r"C:\Users\admin\OneDrive\Desktop\ai assistant\WhatsApp Image 2026-10-30 at 8.45.52 AM.jpeg") 

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
```
Step 4: Pixel Manipulation
```
# Modify a block of pixels (300x300) to white, starting from (200, 200)
image[200:500, 200:500] = [255, 255, 255]  # Rows: 200-499, Columns: 200-499

# Convert BGR to RGB for displaying with Matplotlib
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)

# Display the modified image
plt.imshow(image_rgb)
plt.title("Image with 300x300 White Block")
plt.axis("off")
plt.show()
```
Step 5: Image Resizing
```
image = cv2.imread(r"C:\Users\admin\OneDrive\Desktop\ai assistant\WhatsApp Image 2026-10-30 at 8.45.52 AM.jpeg") 
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
```

Step 6: Image Cropping
```
# Load the image
image = cv2.imread(r"C:\Users\admin\OneDrive\Desktop\ai assistant\WhatsApp Image 2026-10-30 at 8.45.52 AM.jpeg") 

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
```
Step 7: Image Flipping
```
# Load the image
image = cv2.imread(r"C:\Users\admin\OneDrive\Desktop\ai assistant\WhatsApp Image 2026-10-30 at 8.45.52 AM.jpeg") 

# Flip the image horizontally (left-right)
flipped_horizontally = cv2.flip(image, 1)

# Convert BGR to RGB for displaying with Matplotlib
flipped_horizontally_rgb = cv2.cvtColor(flipped_horizontally, cv2.COLOR_BGR2RGB)

# Horizontal flip
plt.imshow(flipped_horizontally_rgb)
plt.title("Flipped Horizontally")
plt.axis("off")

# Flip the image vertically (up-down)
flipped_vertically = cv2.flip(image, 0)

# Convert BGR to RGB for displaying with Matplotlib
flipped_vertically_rgb = cv2.cvtColor(flipped_vertically, cv2.COLOR_BGR2RGB)

# Vertical flip
plt.imshow(flipped_vertically_rgb)
plt.title("Flipped Vertically")
plt.axis("off")
```
OUTPUT
#The following outputs are obtained:

#1. Original image displayed using OpenCV and Matplotlib.

<img width="336" height="413" alt="image" src="https://github.com/user-attachments/assets/d085fa5c-6fcc-41ec-8cce-9781309bc999" />

#2. Image with a line drawn from the top-left to the bottom-right.

<img width="314" height="409" alt="image" src="https://github.com/user-attachments/assets/ef584574-6f6a-44c4-a04f-e7fbd3352b06" />


#3. Image with a circle .

<img width="339" height="414" alt="image" src="https://github.com/user-attachments/assets/6fd56bea-0fc2-47f5-a14f-6eca2bd4dd5e" />


#4. Image with a rectangle around its boundary.

<img width="319" height="427" alt="image" src="https://github.com/user-attachments/assets/72e7f162-ebfe-4935-b0bb-d601506ee127" />


#5. Image with the text "OpenCV Drawing".

<img width="312" height="427" alt="image" src="https://github.com/user-attachments/assets/5e28ab01-4a2a-4d5e-9f49-fa3956314efb" />


#6. HSV, grayscale, and YCrCb color space conversions.

#HSV conversion

<img width="315" height="409" alt="image" src="https://github.com/user-attachments/assets/6ed25a02-ae2b-4092-8ccc-b44435832e9e" />



#grayscale conversion

<img width="331" height="402" alt="image" src="https://github.com/user-attachments/assets/73af0719-94c7-4dcb-87dc-c38c6e766371" />



#YCrCb conversion

<img width="315" height="404" alt="image" src="https://github.com/user-attachments/assets/e1ea8f4c-4186-4176-a957-60db90990918" />


#7. Image converted from HSV back to RGB.

<img width="335" height="413" alt="image" src="https://github.com/user-attachments/assets/f637b80f-7cbf-41b6-ba12-084c90be22e1" />


#8. Pixel value displayed and a white region added to the image.

<img width="322" height="407" alt="image" src="https://github.com/user-attachments/assets/01f91c36-8974-49a5-b952-c6ddfc44d5f9" />


#9. Image resized to half its original dimensions.

<img width="528" height="415" alt="image" src="https://github.com/user-attachments/assets/1f344488-9cb9-43dc-acd8-e2283af416d7" />


#10. Cropped region of interest displayed.

<img width="474" height="417" alt="image" src="https://github.com/user-attachments/assets/5d4d97d3-37ac-45ca-8917-e339a1e602b0" />


#11. Horizontally flipped image displayed.

<img width="329" height="413" alt="image" src="https://github.com/user-attachments/assets/ad537d08-7124-48f7-9b06-ad2b2ac5a69d" />


#12. Vertically flipped image displayed.

<img width="325" height="406" alt="image" src="https://github.com/user-attachments/assets/ba838385-821b-4b6c-b6c3-c4e5b0dd035b" />



RESULT
Thus, image handling and pixel transformations were performed using Python, OpenCV, and Matplotlib. The experiment demonstrated image reading, shape drawing, text insertion, color space conversion, pixel manipulation, image resizing, cropping, flipping, and saving.

