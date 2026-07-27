# Image-Handling-and-Pixel-Transformations-Using-OpenCV

## AIM:
Write a Python program using OpenCV that performs the following tasks:
1. Read and display an image, then draw basic shapes (line, circle, rectangle) and add text on it.
2. Convert the image between different colour spaces (HSV, GRAY, YCrCb, and back to RGB).
3. Access and modify individual pixels of an image.
4. Resize, crop, and flip an image.
5. Save the final modified image to the local directory.

## Software Required:
- Anaconda - Python 3.7
- Jupyter Notebook (for interactive development and execution)

## Algorithm:

### Step 1:
Load an image from your local directory and display it.

### Step 2:
- Draw a line from the top-left to the bottom-right of the image.
- Draw a circle at the center of the image.
- Draw a rectangle around a specific region of interest in the image.
- Add the text "OpenCV Drawing" at the top-left corner of the image.

### Step 3:
- Convert the image from RGB to HSV and display it.
- Convert the image from RGB to GRAY and display it.
- Convert the image from RGB to YCrCb and display it.
- Convert the HSV image back to RGB and display it.

### Step 4:
- Access and print the value of the pixel at coordinates (100, 100).
- Modify the color of the pixel at (200, 200) to white.

### Step 5:
Resize the original image to half its size and display it.

### Step 6:
Crop a region of interest (ROI) from the image (e.g., a 100x100 pixel area starting at (50, 50)) and display it.

### Step 7:
- Flip the original image horizontally and display it.
- Flip the original image vertically and display it.

### Step 8:
Save the final modified image to your local directory.

## Program Developed By:
**Name:** [Your Name Here]

**Register Number:** [Your Register Number Here]

## Ex. No. 01

1. Read the image using OpenCV `imread()`.
```python
import cv2
import matplotlib.pyplot as plt

# Read the image using OpenCV
img = cv2.imread('Qno. 1.jpg', cv2.IMREAD_COLOR)
```
2. Convert BGR to RGB and display the image using matplotlib `imshow()`.
```python
# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

# Display the image using Matplotlib
plt.imshow(img_rgb, cmap='viridis')
plt.title("Original Image")
plt.axis('off')
plt.show()
```
<img width="462" height="476" alt="image" src="https://github.com/user-attachments/assets/bca5bf9b-4aeb-4e5d-b579-7702db8a38c0" />

3. Draw a line, a circle, a rectangle, and add text on the image.
```python
# Draw a line from top-left to bottom-right
line_img = cv2.line(img_rgb, (0, 0), (768, 600), (255, 165, 0), 2)
plt.imshow(line_img, cmap='viridis')
plt.title("Image with Line")
plt.axis('off')
plt.show()
```
<img width="441" height="449" alt="image" src="https://github.com/user-attachments/assets/34cac758-34ed-44aa-b002-d0bedf705273" />
```
# Draw a circle at the center of the image
circle_img = cv2.circle(img_rgb, (400, 300), 150, (0, 200, 255), 10)
plt.imshow(circle_img, cmap='viridis')
plt.title("Image with Circle")
plt.axis('off')
plt.show()
```
<img width="429" height="462" alt="image" src="https://github.com/user-attachments/assets/30c64dc4-8587-4b09-8c84-34be5ec068ff" />
```
# Draw a rectangle around the whole image
rectangle_img = cv2.rectangle(img_rgb, (0, 0), (768, 600), (255, 0, 255), 10)
plt.imshow(rectangle_img, cmap='viridis')
plt.title("Image with Rectangle")
plt.axis('off')
plt.show()
```
<img width="438" height="466" alt="image" src="https://github.com/user-attachments/assets/d6db16b6-4a52-4b82-93d2-d17eb6f48e99" />
```
# Add text to the image
text_img = cv2.putText(img_rgb, "kick", (10, 30),
                        cv2.FONT_HERSHEY_SIMPLEX, 1, (0, 255, 0), 10)
plt.imshow(text_img, cmap='viridis')
plt.title("Image with Text")
plt.axis('off')
plt.show()
```
<img width="451" height="459" alt="image" src="https://github.com/user-attachments/assets/dc8a4a32-4922-47c3-afd5-eb08f4dd43db" />


4. Convert the image to HSV, GRAY, and YCrCb colour spaces, then convert HSV back to RGB.
```python
image = cv2.imread('Qno. 1.jpg')
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)

# Original RGB Image
plt.imshow(image_rgb)
plt.title("Original RGB Image")
plt.axis("off")
```
<img width="439" height="464" alt="image" src="https://github.com/user-attachments/assets/9634c9e1-3abe-4d6f-aeaa-636b7263154d" />
```
# Convert RGB to HSV
image_hsv = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2HSV)
plt.imshow(image_hsv)
plt.title("HSV Image")
plt.axis("off")
```
<img width="422" height="459" alt="image" src="https://github.com/user-attachments/assets/51c8b276-6b44-4596-a463-c6a6715b3cbd" />
```
# Convert RGB to GRAY
image_gray = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2GRAY)
plt.imshow(image_gray, cmap='gray')
plt.title("Grayscale Image")
plt.axis("off")
```
<img width="433" height="466" alt="image" src="https://github.com/user-attachments/assets/52aaa86b-20b6-43b7-8123-4601ef02bd70" />
```
# Convert RGB to YCrCb
image_ycrcb = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2YCrCb)
plt.imshow(image_ycrcb)
plt.title("YCrCb Image")
plt.axis("off")
```
<img width="439" height="461" alt="image" src="https://github.com/user-attachments/assets/0e7ff4ab-cf62-4cd7-b4f6-cbdc7c9de3db" />
```
# Convert HSV back to RGB
image_hsv_to_rgb = cv2.cvtColor(image_hsv, cv2.COLOR_HSV2RGB)
plt.imshow(image_hsv_to_rgb)
plt.title("HSV to RGB Image")
plt.axis("off")
```
<img width="435" height="468" alt="image" src="https://github.com/user-attachments/assets/9da3623e-e559-4909-9c68-02fa27ae0649" />

5. Access the pixel value at (100, 100) and modify the pixel block at (200, 200) to white.
```python
# Access the pixel value at (100, 100)
print(image[100, 100])

# Modify a block of pixels (300x300) to white, starting from (200, 200)
image[200:500, 200:500] = [255, 255, 255]

# Convert BGR to RGB for displaying with Matplotlib
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
plt.imshow(image_rgb)
plt.title("Image with 300x300 White Block")
plt.axis("off")
plt.show()
```
<img width="439" height="471" alt="image" src="https://github.com/user-attachments/assets/c2f21adf-1b0c-4e18-9ae2-6d88b40aa5ad" />

6. Resize the image to half its original size.
```python
image = cv2.imread('Qno. 1.jpg')

# Resize the image to half its size
resized_image = cv2.resize(image, (768 // 2, 600 // 2))

# Convert BGR to RGB for displaying with Matplotlib
resized_image_rgb = cv2.cvtColor(resized_image, cv2.COLOR_BGR2RGB)
plt.imshow(resized_image_rgb)
plt.title("Resized Image (Half Size)")
plt.axis("off")
plt.show()
```
<img width="558" height="470" alt="image" src="https://github.com/user-attachments/assets/be8b11ba-1ad0-4c7f-9d32-57aa9d06344d" />

7. Crop a region of interest (ROI) from the image.
```python
image = cv2.imread('Qno. 1.jpg')

# Crop a 300x300 region starting from (50, 50)
roi = image[50:350, 50:350]

# Convert BGR to RGB for displaying with Matplotlib
roi_rgb = cv2.cvtColor(roi, cv2.COLOR_BGR2RGB)
plt.imshow(roi_rgb)
plt.title("Cropped Region of Interest (ROI)")
plt.axis("off")
plt.show()
```
<img width="447" height="467" alt="image" src="https://github.com/user-attachments/assets/78e19b4b-a38b-4062-a715-97c6e8a897b6" />

8. Flip the image horizontally and vertically.
```python
image = cv2.imread('Qno. 1.jpg')

# Flip the image horizontally (left-right)
flipped_horizontally = cv2.flip(image, 1)
flipped_horizontally_rgb = cv2.cvtColor(flipped_horizontally, cv2.COLOR_BGR2RGB)
plt.imshow(flipped_horizontally_rgb)
plt.title("Flipped Horizontally")
plt.axis("off")
```
<img width="443" height="464" alt="image" src="https://github.com/user-attachments/assets/8d347242-585b-470b-b655-afaa054e8bc1" />
```
# Flip the image vertically (up-down)
flipped_vertically = cv2.flip(image, 0)
flipped_vertically_rgb = cv2.cvtColor(flipped_vertically, cv2.COLOR_BGR2RGB)
plt.imshow(flipped_vertically_rgb)
plt.title("Flipped Vertically")
plt.axis("off")
```
<img width="455" height="460" alt="image" src="https://github.com/user-attachments/assets/000ef866-eac7-410f-83fc-09d733b4737d" />


9. Save the final modified image.
```python
# Save the final modified image to the local directory
cv2.imwrite('final_output.jpg', image)
```

## Output:
i) Image with Line, Circle, Rectangle, and Text.

ii) Colour Space Conversions (HSV, GRAY, YCrCb, HSV→RGB).

iii) Pixel Access and Modification.

iv) Resized, Cropped, and Flipped Images.

## Result:
Thus, the image was read and displayed, basic shapes and text were drawn on it, colour space conversions were performed, individual pixels were accessed and modified, and the image was resized, cropped, flipped, and saved successfully using the Python program.
