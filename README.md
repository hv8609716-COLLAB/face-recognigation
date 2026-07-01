# Face Detection using Python & OpenCV (Google Colab)

This project performs **Face Detection** using **Python** and **OpenCV** inside **Google Colab**.

Instead of using a live webcam, this version allows users to upload an image and automatically detects faces.

---

## Features

✅ Runs directly in Google Colab
✅ Detects faces from uploaded images
✅ Uses OpenCV Haar Cascade
✅ Beginner-friendly project

---

## Tech Stack

* Python
* OpenCV
* Google Colab

---

## Installation

Open Google Colab and install dependencies:

```bash
!pip install opencv-python
```

---

## Project Files

```text
face-detection-colab/
│
├── face_detection_colab.ipynb
├── README.md
└── sample_images/
```

---

## Usage

Run the notebook and upload an image.

Example workflow:

1. Open Google Colab
2. Install dependencies
3. Run all cells
4. Upload image
5. View detected faces

---

## Example Code

```python
import cv2
from google.colab.patches import cv2_imshow
from google.colab import files

face_cascade = cv2.CascadeClassifier(
    cv2.data.haarcascades +
    "haarcascade_frontalface_default.xml"
)

uploaded = files.upload()

filename = list(uploaded.keys())[0]

img = cv2.imread(filename)

gray = cv2.cvtColor(
    img,
    cv2.COLOR_BGR2GRAY
)

faces = face_cascade.detectMultiScale(
    gray,
    1.1,
    5
)

for (x,y,w,h) in faces:
    cv2.rectangle(
        img,
        (x,y),
        (x+w,y+h),
        (0,255,0),
        2
    )

cv2_imshow(img)

print("Faces detected:", len(faces))
```

---

## Output

The uploaded image will appear with rectangles drawn around detected faces.


---

## Autthor
Harsh vardhan
