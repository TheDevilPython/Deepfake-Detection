
# 🎭 Deepfake Detection System

A deep learning-based web application to automatically detect whether a given video is **real or AI-generated (deepfake)**. This system uses **ResNeXt CNN** for spatial feature extraction and **LSTM RNN** for temporal sequence analysis, integrated with a Django web app for easy usage.

---

## 📽️ Live Demo

🚀 Upload a video and get results instantly:
- Classification: **REAL / FAKE**
- Model Confidence: ✅ Confidence Score
- Rendered Output: Overlay result on video in browser

---

## 📌 Features

- 📹 Upload video and detect deepfakes
- 🧠 Uses pre-trained **ResNeXt50_32x4d** + **LSTM**
- 🔐 Video is encrypted during processing
- 🧪 Tested on multiple datasets: **FaceForensics++, DFDC, Celeb-DF**
- 📊 Achieves up to **97.7% accuracy** on benchmark datasets

---

## 📂 Project Structure

```
Deepfake-Detection/
│
├── models/              # Trained model files (upload yours here)
├── static/              # CSS, JS, media assets
├── templates/           # Django HTML templates (UI)
├── video_processing/    # Preprocessing logic
├── deepfake_detector/   # Django app
├── manage.py            # Django project manager
├── requirements.txt     # Python dependencies
└── README.md            # This file
```

---

## 🧠 Model Architecture

- ✅ **ResNeXt-50** CNN extracts 2048-dim feature vectors per frame
- ⏱ **LSTM RNN** analyzes sequential frame data (temporal inconsistencies)
- 🧮 **Softmax** gives prediction + confidence
- 🔁 Trained on **6000 videos** (50/50 real-fake split)

---

## 💾 Installation & Setup Guide

### 1. ⚙️ Clone the Repository

```bash
git clone https://github.com/TheDevilPython/Deepfake-Detection.git
cd Deepfake-Detection
```

### 2. 🐍 Create a Virtual Environment (Recommended)

```bash
python -m venv venv
source venv/bin/activate      # On Windows: venv\Scripts\activate
```

### 3. 📦 Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. 📁 Add Trained Models

Place all your trained `.pt` model files inside the `models/` directory.  
If you don’t have them yet, train your model first using your training pipeline.

### 5. 🔄 Migrate Database

```bash
python manage.py migrate
```

### 6. 🚀 Run the Server

```bash
python manage.py runserver 0.0.0.0:8000
```

Then visit: [http://localhost:8000](http://localhost:8000)

---

## 🔒 Security & Privacy

- 🔐 All uploaded videos are **encrypted** before processing
- 🕓 Stored videos are automatically deleted after **30 minutes**
- ✅ Uses **SSL certificates** for secure connections (production)

---

## 📊 Datasets Used

| Dataset            | Description                                |
|--------------------|--------------------------------------------|
| FaceForensics++    | Face manipulation benchmark dataset         |
| Deepfake Detection Challenge (DFDC) | From Kaggle's DFDC challenge   |
| Celeb-DF           | Celebrity-based real & fake videos         |
| YouTube Real Data  | Additional real-world test scenarios       |

---

## ⚙️ Technologies Used

| Stack           | Tools |
|----------------|-------|
| Language       | Python 3 |
| Deep Learning  | PyTorch, ResNeXt, LSTM |
| Video Processing | OpenCV, face_recognition |
| Web Framework  | Django |
| Deployment     | Google Cloud Platform (GCP) |
| UI/UX          | HTML, CSS, JavaScript |
| Security       | Symmetric encryption, SSL |

---

## 🧪 Test Cases (Examples)

| Action                        | Expected Result            |
|------------------------------|----------------------------|
| Upload video with no faces   | Error: No faces detected   |
| Upload valid real video      | Output: "REAL"             |
| Upload deepfake video        | Output: "FAKE"             |
| Upload video > 100MB         | Error: Max size exceeded   |
| Upload .docx file            | Error: Invalid file type   |

---

## 📈 Results

| Dataset        | Accuracy (%) | Sequence Length |
|----------------|---------------|------------------|
| FaceForensics++| 97.76%        | 100 frames       |
| Celeb-DF + FF++| 93.97%        | 100 frames       |
| Mixed Dataset  | 89.34%        | 40 frames        |

---

## 🚧 Future Scope

- Detect **audio and full-body deepfakes**
- Convert app to a **mobile-compatible version**
- Release a **browser plugin** for video content analysis
- Real-time detection using **ONNX / TensorFlow Lite**

---

## 🧑‍💻 Maintainer

Made with ❤️ by **Karthik U Rao**  
📬 [GitHub](https://github.com/TheDevilPython)

---

## 📄 License

This project is licensed under the **MIT License**. See the [LICENSE](LICENSE) file for details.
