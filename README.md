#  Pneumonia Detection from Chest X-Ray Images

![Python](https://img.shields.io/badge/Python-3.x-blue.svg)
![OpenCV](https://img.shields.io/badge/OpenCV-Image%20Processing-green.svg)
![Google Colab](https://img.shields.io/badge/Google%20Colab-Supported-orange.svg)

Digital Image Processing and Classification of Chest X-Ray images for the detection of Pneumonia vs. Normal cases.

---

##  1. Project Overview
This project aims to process and analyze chest X-ray images to distinguish between healthy lungs and those affected by pneumonia (bacterial or viral). It demonstrates dataset extraction, image loading, preprocessing, and visual analysis using Python and OpenCV.

---

##  2. Dataset Structure
The dataset directory structure after extracting the archive file:

```text
project_subset/New folder (2)/
│
├── Train/                 # Training dataset
│   ├── NORMAL/            # Normal chest X-rays
│   └── PNEUMONIA/         # Pneumonia chest X-rays
│
├── Val/                   # Validation dataset
│   ├── NORMAL/
│   └── PNEUMONIA/
│
└── test/                  # Test dataset
    ├── NORMAL/
    └── PNEUMONIA/
```

---

##  3. Requirements & Dependencies

The project relies on the following packages and tools:

* **Python 3.x**
* **Google Colab** (recommended)
* **OpenCV (`cv2`)**
* **Matplotlib**
* **Unrar Utility** (for extraction)

---

##  4. How to Run

### Step 1: Upload the Dataset Archive
Upload the compressed dataset file `New folder (2).rar` to your Google Colab workspace:
```python
from google.colab import files

uploaded = files.upload()
```

### Step 2: Install Unrar & Extract Files
```bash
!apt-get install unrar
!unrar x "New folder (2).rar" project_subset
```

### Step 3: Load and Display an X-Ray Image
Read and display a sample chest X-ray image in grayscale format:
```python
import cv2
import matplotlib.pyplot as plt

# Image file path
img_path = "project_subset/New folder (2)/Train/NORMAL/IM-0125-0001.jpeg"
img = cv2.imread(img_path, 0)

if img is None:
    print("Error: Image could not be loaded. Check the file path.")
else:
    plt.imshow(img, cmap="gray")
    plt.title("Chest X-Ray Image (Normal)")
    plt.axis("off")
    plt.show()
```

---

##  5. Sample Output & Analysis

| Condition | Visual Characteristics |
| :--- | :--- |
| **Normal X-Ray** | Clear lung fields with normal vascular markings and no significant infiltrates. |
| **Pneumonia X-Ray** | Presence of opacities, consolidation, or cloudiness indicating infection. |

---

##  6. Future Enhancements
- [ ] Build and train a Convolutional Neural Network (CNN) / Transfer Learning model (e.g., ResNet, VGG16) for automatic classification.
- [ ] Apply Contrast Limited Adaptive Histogram Equalization (CLAHE) for image enhancement.
- [ ] Develop a user-friendly Web Application using Streamlit or Flask for real-time diagnosis.
