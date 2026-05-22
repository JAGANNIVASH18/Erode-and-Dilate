# Implementation-of-Erosion-and-Dilation

## Aim
To perform erosion and dilation operations on a text image using Python and OpenCV.

---

## Software Required
- Anaconda – Python 3.7
- OpenCV

---

## Algorithm

### Step 1
Import the required libraries such as OpenCV, NumPy, and Matplotlib.

### Step 2
Create a text image using the `cv2.putText()` function.

### Step 3
Generate a structuring element for morphological operations.

### Step 4
Apply the erosion operation to the text image.

### Step 5
Apply the dilation operation and display the output images.

---

## Program

### Import the Necessary Packages

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
```

### Create the Text using cv2.putText

```python
img2 = np.zeros((100,400), dtype='uint8')

font = cv2.FONT_HERSHEY_SIMPLEX

cv2.putText(
    img2,
    'TheAILearner',
    (5,70),
    font,
    2,
    (255),
    5,
    cv2.LINE_AA
)
```

### Create the Structuring Element

```python
kernel = np.ones((5,5), np.uint8)

kernel1 = cv2.getStructuringElement(
    cv2.MORPH_CROSS,
    (7,7)
)
```

### Erode the Image

```python
image_erode1 = cv2.erode(img2, kernel1)
```

### Dilate the Image

```python
image_dilate1 = cv2.dilate(img2, kernel1)
```

### Display the Results

```python
titles = ["Original Image", "Eroded Image", "Dilated Image"]

images = [img2, image_erode1, image_dilate1]

for i in range(0,3):

    plt.figure(figsize=(10,10))

    plt.subplot(1,2,1)
    plt.title("Original Image")
    plt.imshow(img2, cmap='gray')
    plt.axis("off")

    plt.subplot(1,2,2)
    plt.title(titles[i])
    plt.imshow(images[i], cmap='gray')
    plt.axis("off")

    plt.show()
```

---

## Output

### Display the Input Image
<img width="731" height="119" alt="image" src="https://github.com/user-attachments/assets/c3a30b36-89d9-4c59-9f1a-4bc28329c597" />


### Display the Eroded Image
<img width="771" height="115" alt="image" src="https://github.com/user-attachments/assets/f71028ef-52d0-46e1-b0fd-0a6aa0ddb3df" />


### Display the Dilated Image
<img width="724" height="127" alt="image" src="https://github.com/user-attachments/assets/41dc8642-c867-4afd-850b-1abc0b97cb9e" />


---

## Result
Thus, erosion and dilation operations were successfully performed on the generated text image using Python and OpenCV.
