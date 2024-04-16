# THRESHOLDING
## Aim

### To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
### 1. Anaconda - Python 3.7
### 2. OpenCV

## Algorithm

### Step1:

Import necessary packages



### Step2:


Read the image


### Step3:

If the read image is a color image, convert it into a grayscale image



### Step4:

Perform the threshold operation you want to do(global thresholding or adaptive thresholding or otsu's thresholding)



### Step5:

Display the Results

## Developed By : SANJAY T

## Reg.No. 212222110039

## Program

```python
# Load the necessary packages

import cv2
import matplotlib.pyplot as plt

# Read the Image and convert to grayscale


# Read the image
img = cv2.imread('dip08')
o_image = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
image_path = 'dip08'
image = cv2.imread(image_path, cv2.IMREAD_GRAYSCALE)

if image is None:
    raise FileNotFoundError(f"Image not found at path: {image_path}")



# Use Global thresholding to segment the image

_, binary_thresh = cv2.threshold(image, 127, 255, cv2.THRESH_BINARY)
_, binary_inv_thresh = cv2.threshold(image, 127, 255, cv2.THRESH_BINARY_INV)
_, tozero_thresh = cv2.threshold(image, 127, 255, cv2.THRESH_TOZERO)
_, tozero_inv_thresh = cv2.threshold(image, 127, 255, cv2.THRESH_TOZERO_INV)
_, truncate_thresh = cv2.threshold(image, 127, 255, cv2.THRESH_TRUNC)


# Use Adaptive thresholding to segment the image

adaptive_mean_thresh = cv2.adaptiveThreshold(image, 255, cv2.ADAPTIVE_THRESH_MEAN_C, cv2.THRESH_BINARY, 11, 2)
adaptive_gaussian_thresh = cv2.adaptiveThreshold(image, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C, cv2.THRESH_BINARY, 11, 2)



# Use Otsu's method to segment the image 

_, otsu_thresh = cv2.threshold(image, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)


# Display the results

plt.figure(figsize=(12, 15))

# Original and Gray Image
plt.subplot(1, 2, 1)
plt.imshow(o_image)
plt.title('Original Image')
plt.axis('off')

plt.subplot(1, 2, 2)
plt.imshow(image, cmap='gray')
plt.title('Gray Iamge')
plt.axis('off')


 # Original, Threshold (Binary) and Threshold (Binary inverse)
plt.subplot(1, 2, 1)
plt.imshow(image, cmap='gray')
plt.title('Gray Image')
plt.axis('off')

plt.subplot(1, 2, 2)
plt.imshow(binary_thresh, cmap='gray')
plt.title('Binary Threshold')
plt.axis('off')

plt.subplot(1, 2, 1)
plt.imshow(binary_thresh, cmap='gray')
plt.title('Binary Threshold')
plt.axis('off')

plt.subplot(1, 2, 2)
plt.imshow(binary_inv_thresh, cmap='gray')
plt.title('Binary Inverse Threshold')
plt.axis('off')

#  Threshold (to Zero) and Threshold (to Inverse Zero)
plt.subplot(1, 2, 1)
plt.imshow(tozero_thresh, cmap='gray')
plt.title('Threshold(To Zero)')
plt.axis('off')

plt.subplot(1, 2, 2)
plt.imshow(tozero_inv_thresh, cmap='gray')
plt.title('Threshold(To Inverse Zero)')
plt.axis('off')

# Original, Threshold Image (Truncate)
plt.subplot(1, 2, 1)
plt.imshow(image, cmap='gray')
plt.title('Gray Image')
plt.axis('off')


plt.subplot(1, 2, 2)
plt.imshow(truncate_thresh, cmap='gray')
plt.title('Truncate Threshold')
plt.axis('off')

# Adaptive threshold (mean) and Adaptive threshold (Gaussian)
plt.subplot(1, 2, 1)
plt.imshow(adaptive_mean_thresh, cmap='gray')
plt.title('Adaptive Threshold (Mean)')
plt.axis('off')

plt.subplot(1, 2, 2)
plt.imshow(adaptive_gaussian_thresh, cmap='gray')
plt.title('Adaptive Threshold (Gaussian)')
plt.axis('off')



# Original, Otsu's threshold
plt.subplot(1, 2, 1)
plt.imshow(image, cmap='gray')
plt.title('Gray Image')
plt.axis('off')

plt.subplot(1, 2, 2)
plt.imshow(otsu_thresh, cmap='gray')
plt.title("Otsu's Threshold")
plt.axis('off')





```
## Output

### Original Image
<br>
<br>

![image](https://github.com/sanjaythiyagarajan/THRESHOLDING-/assets/119409242/bb50745a-f7b4-4876-aca0-6dfaf43103e6)

<br>
<br>

### Global Thresholding
<br>
<br>

![image](https://github.com/sanjaythiyagarajan/THRESHOLDING-/assets/119409242/78cb5fc8-d42f-4538-93c7-21be535f6eaf)


![image](https://github.com/sanjaythiyagarajan/THRESHOLDING-/assets/119409242/cb6fef82-0456-4cdf-958f-f580190f811d)


![image](https://github.com/sanjaythiyagarajan/THRESHOLDING-/assets/119409242/3158d5b1-2c5b-4212-90b1-59a7ee3b0585)


![image](https://github.com/sanjaythiyagarajan/THRESHOLDING-/assets/119409242/10e9f255-4be4-42ab-bc35-266124581f9f)



<br>
<br>

### Adaptive Thresholding
<br>
<br>


![image](https://github.com/sanjaythiyagarajan/THRESHOLDING-/assets/119409242/a3de6f83-17e1-41f8-820a-3cf55169ffc8)


<br>
<br>

### Optimum Global Thesholding using Otsu's Method
<br>
<br>

![image](https://github.com/sanjaythiyagarajan/THRESHOLDING-/assets/119409242/8af22634-1bd6-484e-9930-f5dcd9217c69)




<br>
<br>


## Result
### Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
