# Ex 05 Implementation-of-filter
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:

### Step 1:
Import necessary libraries: OpenCV, NumPy, and Matplotlib.Read an image, convert it to RGB format, define an 11x11 averaging kernel, and apply 2D convolution filtering.Display the original and filtered images side by side using Matplotlib.

### Step 2:
Define a weighted averaging kernel (kernel2) and apply 2D convolution filtering to the RGB image (image2).Display the resulting filtered image (image4) titled 'Weighted Averaging Filtered' using Matplotlib's imshow function.

### Step 3:
Apply Gaussian blur with a kernel size of 11x11 and standard deviation of 0 to the RGB image (image2).Display the resulting Gaussian-blurred image (gaussian_blur) titled 'Gaussian Blurring Filtered' using Matplotlib's imshow function.

### Step 4:
Apply median blur with a kernel size of 11x11 to the RGB image (image2).Display the resulting median-blurred image (median) titled 'Median Blurring Filtered' using Matplotlib's imshow function.

### Step 5 :
Define a Laplacian kernel (kernel3) and perform 2D convolution filtering on the RGB image (image2).Display the resulting filtered image (image5) titled 'Laplacian Kernel' using Matplotlib's imshow function.

### Step 6 :
Apply the Laplacian operator to the RGB image (image2) using OpenCV's cv2.Laplacian function.Display the resulting image (new_image) titled 'Laplacian Operator' using Matplotlib's imshow function.

## Program:
### Developed By : LEANN JOBY MATHEW
### Register Number : 212222230074
</br>

### 1. Smoothing Filters

i) Using Averaging Filter
```Python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread('dog.png')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

kernel = np.ones((11,11), np. float32)/121
image3 = cv2.filter2D(image2, -1, kernel)

plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title('Orignal')
plt.axis('off')

plt.subplot(1,2,2)
plt.imshow(image3)
plt.title('Filtered')
plt.axis('off')
```
![image](https://github.com/Leann4468/Implementation-of-filter/assets/121165979/99db3f1b-57e0-443d-a330-4973c47ceba8)

![image](https://github.com/Leann4468/Implementation-of-filter/assets/121165979/32859d2b-ef5a-4f7d-bc15-675546fd11c5)

![image](https://github.com/Leann4468/Implementation-of-filter/assets/121165979/ca7d2e5b-9ba0-43ff-9a1f-402db8936ac4)

ii) Using Weighted Averaging Filter
```Python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread('dog.png')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

kernel2 = np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image4 = cv2.filter2D(image2, -1, kernel2)
plt.imshow(image4)
plt.title('Weighted Averaging Filtered')
```
![image](https://github.com/Leann4468/Implementation-of-filter/assets/121165979/54d1bc21-9438-42e0-997b-83ab0c822d8d)

![image](https://github.com/Leann4468/Implementation-of-filter/assets/121165979/5b61c3ec-dc24-4cfc-9796-7edd356d687b)

iii) Using Gaussian Filter
```Python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread('dog.png')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

gaussian_blur = cv2.GaussianBlur(src=image2, ksize=(11,11), sigmaX=0, sigmaY=0)
plt.imshow(gaussian_blur)
plt.title(' Gaussian Blurring Filtered')
```
![image](https://github.com/Leann4468/Implementation-of-filter/assets/121165979/77a3d8d2-24ec-410d-9573-1e2b611c0230)

![image](https://github.com/Leann4468/Implementation-of-filter/assets/121165979/93673b9b-3330-4394-9a80-7753e4a41fcc)

iv) Using Median Filter
```Python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread('dog.png')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

median=cv2.medianBlur (src=image2, ksize=11)
plt.imshow(median)
plt.title(' Median Blurring Filtered')
```
![image](https://github.com/Leann4468/Implementation-of-filter/assets/121165979/06c3dbfb-2571-4b51-9c5f-c7f23ae23420)

![image](https://github.com/Leann4468/Implementation-of-filter/assets/121165979/72a82705-fc83-4e9a-8bc7-1c0ed376fec2)

### 2. Sharpening Filters
i) Using Laplacian Kernal
```Python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread('dog.png')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

kernel3 = np.array([[0,1,0], [1, -4,1],[0,1,0]])
image5 =cv2.filter2D(image2, -1, kernel3)
plt.imshow(image5)
plt.title('Laplacian Kernel')
```
![image](https://github.com/Leann4468/Implementation-of-filter/assets/121165979/40c43918-191c-42b7-963e-28342b8ea7aa)

![image](https://github.com/Leann4468/Implementation-of-filter/assets/121165979/2327ab84-ca43-4d0f-9354-61333d19a228)

ii) Using Laplacian Operator
```Python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread('dog.png')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

new_image = cv2.Laplacian (image2, cv2.CV_64F)
plt.imshow(new_image)
plt.title('Laplacian Operator')
```
![image](https://github.com/Leann4468/Implementation-of-filter/assets/121165979/558022ed-7c6d-4216-9706-e2b4eeb0cefc)

![image](https://github.com/Leann4468/Implementation-of-filter/assets/121165979/e6b9bfc2-e68c-4d24-b92b-2563f9d3bbc8)

## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
