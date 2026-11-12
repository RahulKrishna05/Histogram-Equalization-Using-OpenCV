# EX.NO:03 - Histogram Equalization Using OpenCV (Grayscale & Color Images)

---

## Aim

To write a Python program using OpenCV to perform histogram equalization on both grayscale and color images to enhance image contrast and brightness.

The program performs the following operations:

- Read and display a grayscale image  
- Plot histogram of the grayscale image  
- Apply histogram equalization on grayscale image  
- Read and display a color image  
- Plot histogram of B, G, R channels  
- Convert image to HSV color space  
- Apply histogram equalization on the Value (V) channel  
- Convert the enhanced image back to BGR format  
- Display original and enhanced images with histograms  

---

## Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (`cv2`)  
- NumPy  
- Matplotlib  

---

## Algorithm

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the image `parrot.jpg` in grayscale format.

### Step 3:
Display the grayscale image and plot its histogram.

### Step 4:
Apply histogram equalization using `cv2.equalizeHist()` to enhance contrast.

### Step 5:
Display original grayscale image, its histogram, enhanced image, and its histogram using a 2 × 2 grid.

### Step 6:
Read the same image in color format.

### Step 7:
Split the image into B, G, R channels and plot their histograms.

### Step 8:
Convert the image from BGR to HSV color space.

### Step 9:
Apply histogram equalization on the V (Value) channel.

### Step 10:
Merge the channels and convert the image back to BGR format.

### Step 11:
Display original color image, histogram, enhanced image, and enhanced histogram using a 2 × 2 grid.

---

## Program & Output

### Developed By:
**Name:** Rahul Krishna

### Register No: 212223040162

```
import cv2
import numpy as np
import matplotlib.pyplot as plt
img = cv2.imread('me.jpg', cv2.IMREAD_GRAYSCALE)
plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()
```

<img width="476" height="434" alt="d12111c5-75e2-4b08-afa0-f95cb41a14c1" src="https://github.com/user-attachments/assets/9c39d607-e782-41e0-931e-5c17ce5f35f0" />

```
plt.hist(img.ravel(),256,range = [0, 256]);
plt.title('Original Image')
plt.show()
```

<img width="579" height="434" alt="ea18ef5a-26c7-49d3-9609-9f6c57fe3176" src="https://github.com/user-attachments/assets/59c9ee64-bde4-46f8-af52-7d24395c2162" />

```
img_eq = cv2.equalizeHist(img)
plt.hist(img_eq.ravel(), 256, range = [0, 256])
plt.title('Equalized Histogram')
```

<img width="720" height="547" alt="Screenshot 2026-11-12 114719" src="https://github.com/user-attachments/assets/f58e2a15-babb-4ce7-b82d-aa8fcab9e9ea" />

```
plt.imshow(img_eq, cmap='gray')
plt.title('Original Image')
plt.show()
```

<img width="597" height="540" alt="Screenshot 2026-11-12 114814" src="https://github.com/user-attachments/assets/31306762-9986-4a84-bd18-8e17d62189d2" />

```
img = cv2.imread('me.jpg', cv2.IMREAD_COLOR)
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:, :, 2])
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)
plt.imshow(img_eq[:,:,::-1]);
plt.title('Equalized Image');
plt.show()
```

<img width="612" height="538" alt="Screenshot 2026-11-12 115220" src="https://github.com/user-attachments/assets/b8019dad-ec4e-4154-8da8-a103bb262a1f" />

```
plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized');plt.show()
```

<img width="591" height="543" alt="Screenshot 2026-11-12 114835" src="https://github.com/user-attachments/assets/a8afbb1b-44b7-4138-83c6-a96c04a02651" />

```
plt.figure(figsize = (20,10))
plt.subplot(221); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(222); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
plt.show()
```

<img width="791" height="265" alt="Screenshot 2026-11-12 114919" src="https://github.com/user-attachments/assets/8768dd67-f129-4988-8463-05eab0ef2f54" />

```
plt.figure(figsize = [15,4])
plt.subplot(121); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')
plt.subplot(122); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized')
```

<img width="792" height="237" alt="Screenshot 2026-11-12 115244" src="https://github.com/user-attachments/assets/4e87d1d8-4898-4d8e-9c22-2a07d8ac7013" />


---

## Result

Thus, histogram equalization is successfully performed on both grayscale and color images using OpenCV. The contrast and brightness of the images are significantly improved, enhancing visual quality and feature visibility.
