# Implementation-of-filter
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1

Import necessary libraries: OpenCV, NumPy, and Matplotlib.Read an image, convert it to RGB format, define an 11x11 averaging kernel, and apply 2D convolution filtering.Display the original and filtered images side by side using Matplotlib.

### Step2
</br>
</br> Define a weighted averaging kernel (kernel2) and apply 2D convolution filtering to the RGB image (image2).Display the resulting filtered image (image4) titled 'Weighted Averaging Filtered' using Matplotlib's imshow function.

### Step3
</br>
</br> Apply Gaussian blur with a kernel size of 11x11 and standard deviation of 0 to the RGB image (image2).Display the resulting Gaussian-blurred image (gaussian_blur) titled 'Gaussian Blurring Filtered' using Matplotlib's imshow function.

### Step4
</br>
</br> Apply median blur with a kernel size of 11x11 to the RGB image (image2).Display the resulting median-blurred image (median) titled 'Median Blurring Filtered' using Matplotlib's imshow function.

### Step5
</br>
</br> Define a Laplacian kernel (kernel3) and perform 2D convolution filtering on the RGB image (image2).Display the resulting filtered image (image5) titled 'Laplacian Kernel' using Matplotlib's imshow function.

### Step6

Apply the Laplacian operator to the RGB image (image2) using OpenCV's cv2.Laplacian function.Display the resulting image (new_image) titled 'Laplacian Operator' using Matplotlib's imshow function.


## Program:
### Developed By: PREETHA.S
### Register Number: 212222230110

### 1. Smoothing Filters

i) Using Averaging Filter
```

import cv2
import numpy as np
import matplotlib.pyplot as plt
image1=cv2.imread("anne.jpeg")
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)
kernel=np.ones((11,11),np.float32)/121
image3=cv2.filter2D(image2,-1,kernel)

plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title('Original')
plt.axis('off')

plt.subplot(1,2,2)
plt.imshow(image3)
plt.title('Filtered')
plt.axis('off')



```
ii) Using Weighted Averaging Filter
```Python

import cv2
import numpy as np
import matplotlib.pyplot as plt
image1=cv2.imread("anne.jpeg")
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)

kernel2=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image3=cv2.filter2D(image2,-1,kernel2)
plt.imshow(image3)
plt.title('WEIGHTED AVERAGE FILTERING')



```
iii) Using Gaussian Filter
```Python

import cv2
import numpy as np
import matplotlib.pyplot as plt
image1=cv2.imread("anne.jpeg")
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)

guassian_blur=cv2.GaussianBlur(src=image2,ksize=(11,11),sigmaX=0,sigmaY=0)
plt.imshow(guassian_blur)
plt.title('GAUSSIAN FILTER')



```

iv) Using Median Filter
```Python

import cv2
import numpy as np
import matplotlib.pyplot as plt
image1=cv2.imread("pre.jpeg")
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)

median=cv2.medianBlur(src=image2,ksize=11)
plt.imshow(median)
plt.title('MEDIAN FILTER')



```

### 2. Sharpening Filters
i) Using Laplacian Kernal
```Python


import cv2
import numpy as np
import matplotlib.pyplot as plt
image1=cv2.imread("pre.jpeg")
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)

kernel3=np.array([[0,1,0],[1,-4,1],[0,1,0]])
image3=cv2.filter2D(image2,-1,kernel3)

plt.imshow(image3)
plt.title('LAPLACIAN KERNEL')


```
ii) Using Laplacian Operator
```Python

import cv2
import numpy as np
import matplotlib.pyplot as plt
image1=cv2.imread("pre.jpeg")
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)

new_image=cv2.Laplacian(image2,cv2.CV_64F)
plt.imshow(new_image)
plt.title('LAPLACIAN OPERATOR')



```

## OUTPUT:
### 1. Smoothing Filters

i) Using Averaging Filter

(-0.5, 719.5, 959.5, -0.5)

![image](https://github.com/Preetha-Senthamilan/Implementation-of-filter/assets/119390282/7ea3087c-b64e-43bf-ab60-7db2a1c6cb0b)

ii) Using Weighted Averaging Filter

Text(0.5, 1.0, 'WEIGHTED AVERAGE FILTERING')

</br>
</br>
</br>![image](https://github.com/Preetha-Senthamilan/Implementation-of-filter/assets/119390282/a67fc579-f3ea-4961-9a1b-1deff99a3322)

</br>
</br>

iii) Using Gaussian Filter

Text(0.5, 1.0, 'GAUSSIAN FILTER')
</br>
</br>![image](https://github.com/Preetha-Senthamilan/Implementation-of-filter/assets/119390282/3c79207c-44a4-47d3-ac5c-c63bba159da6)

</br>
</br>

iv) Using Median Filter
</br>
</br>Text(0.5, 1.0, 'MEDIAN FILTER')
</br>
</br>![image](https://github.com/Preetha-Senthamilan/Implementation-of-filter/assets/119390282/7e7ded21-11ed-4988-ac0d-00aeb2a45e5d)

</br>

### 2. Sharpening Filters
</br>

i) Using Laplacian Kernal
</br>
Text(0.5, 1.0, 'LAPLACIAN KERNEL')
</br>
</br>![image](https://github.com/Preetha-Senthamilan/Implementation-of-filter/assets/119390282/4a4f58e2-2a1d-4727-ae71-c27607cc8afd)

</br>
</br>

ii) Using Laplacian Operator
</br>
</br>Text(0.5, 1.0, 'LAPLACIAN OPERATOR')
</br>
</br>![image](https://github.com/Preetha-Senthamilan/Implementation-of-filter/assets/119390282/9d7474ac-512d-4235-9e5f-6dbeb90ec7e4)

</br>

## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
