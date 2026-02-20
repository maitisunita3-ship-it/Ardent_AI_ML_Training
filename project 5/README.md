<img width="405" height="615" alt="image" src="https://github.com/user-attachments/assets/45a39a4c-001d-4dd1-a27c-bdd1d17180bf" />


# 😊 Real-Time Emotion Detection System

> A real-time facial emotion recognition system built with Python, OpenCV, and a custom Keras deep learning model — no DeepFace dependency required.

[![Python](https://img.shields.io/badge/Python-3.8+-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://python.org)
[![OpenCV](https://img.shields.io/badge/OpenCV-4.x-5C3EE8?style=for-the-badge&logo=opencv&logoColor=white)](https://opencv.org)
[![Keras](https://img.shields.io/badge/Keras-TensorFlow-D00000?style=for-the-badge&logo=keras&logoColor=white)](https://keras.io)
[![GitHub](https://img.shields.io/badge/GitHub-maitisunita3--ship--it-181717?style=for-the-badge&logo=github)](https://github.com/maitisunita3-ship-it)

---

## 📸 Demo

The system detects faces in real-time from your webcam and overlays the predicted emotion label directly on the video feed.

**Detectable Emotions:**

| Label | Emotion |
|-------|---------|
| 😠 | Angry |
| 🤢 | Disgust |
| 😨 | Fear |
| 😄 | Happy |
| 😢 | Sad |
| 😲 | Surprise |
| 😐 | Neutral |

---

## 🧠 How It Works

```
Webcam Feed
    │
    ▼
Convert to Grayscale (OpenCV)
    │
    ▼
Detect Faces (Haar Cascade Classifier)
    │
    ▼
Crop & Resize ROI → 64×64 px
    │
    ▼
Normalize Pixel Values (÷ 255)
    │
    ▼
Predict Emotion (Keras CNN Model)
    │
    ▼
Overlay Label + Bounding Box on Frame
```

1. **Face Detection** — Haar Cascade (`haarcascade_frontalface_default.xml`) locates faces in each grayscale frame.
2. **Preprocessing** — The detected face region (ROI) is resized to `64×64` pixels and normalized to `[0, 1]`.
3. **Emotion Prediction** — The preprocessed image is passed through a pre-trained CNN (`emotion_model.hdf5`) which outputs probabilities for 7 emotion classes.
4. **Visualization** — A bounding box and emotion label are drawn on the live video frame using OpenCV.

---

## 📂 Project Structure

```
emotion-detection/
├── emotion_detection.py                   # Main script — run this
├── emotion_model.hdf5                     # Pre-trained Keras CNN model
├── haarcascade_frontalface_default.xml    # OpenCV face detection model
└── README.md                              # Project documentation
```

---

## ⚙️ Requirements

- Python 3.8+
- Webcam (built-in or external)
- macOS / Windows / Linux

### Install Dependencies

```bash
pip install opencv-python numpy tensorflow keras
```

> **macOS users:** The script uses `cv2.CAP_AVFOUNDATION` for native Mac webcam compatibility — no extra setup needed.

---

## 🚀 Getting Started

**1. Clone the repository**
```bash
git clone https://github.com/maitisunita3-ship-it/Portfolio.git
cd emotion-detection
```

**2. Make sure all three files are in the same directory**
```
emotion_detection.py
emotion_model.hdf5
haarcascade_frontalface_default.xml
```

**3. Run the script**
```bash
python emotion_detection.py
```

**4. Press `q` to quit the webcam window.**

---

## 🔬 Model Details

| Property | Value |
|---|---|
| **Model File** | `emotion_model.hdf5` |
| **Architecture** | Convolutional Neural Network (CNN) |
| **Input Shape** | `(1, 64, 64, 1)` — grayscale |
| **Output Classes** | 7 emotions |
| **Framework** | Keras (TensorFlow backend) |
| **Face Detector** | Haar Cascade (OpenCV built-in) |

---

## 🧩 Key Libraries

| Library | Purpose |
|---|---|
| `opencv-python` | Webcam capture, face detection, drawing overlays |
| `numpy` | Array reshaping and normalization |
| `keras` / `tensorflow` | Loading and running the CNN model |

---

## 📌 Notes

- Ensure **camera permissions** are granted to your terminal/IDE on macOS.
- Works best with **good lighting** and a **front-facing camera angle**.
- The model was trained on grayscale `64×64` face images — results are optimal under similar conditions.
- If you're on **Windows/Linux**, you can remove the `cv2.CAP_AVFOUNDATION` flag:
  ```python
  cap = cv2.VideoCapture(0)  # Works on all platforms
  ```

---

## 🙏 Acknowledgements

- **OpenCV** for the Haar Cascade face detection model
- **Keras / TensorFlow** for the deep learning framework
- Mentored by **SK Sahil** (AI Developer & Tutor · [Code_ScholarEU](https://www.instagram.com/code_scholar_eu/))

---

## 👤 Author

**Sunita Maiti**
- 🐙 GitHub: [maitisunita3-ship-it](https://github.com/maitisunita3-ship-it)
- 💼 Portfolio: [View Portfolio](https://github.com/maitisunita3-ship-it/Portfolio)

---

<div align="center">
  <sub>Built with ❤️ using Python · OpenCV · Keras | No DeepFace required</sub>
</div>
