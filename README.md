# 🩺 SkinScope — Skin Disease Detector

A deep-learning web application for **skin disease image classification**.

SkinScope allows users to upload a skin image and receive a predicted disease label in **English and Arabic** through a simple web interface.

> ⚠️ **Medical Disclaimer:** SkinScope is an educational/informational AI project. It is not a medical diagnostic tool and should not be used as a replacement for a qualified healthcare professional.

---

## ✨ Features

- 🧠 TensorFlow-based trained deep learning model
- 🖼️ Upload a skin image for prediction
- 🌍 Bilingual prediction results:
  - English
  - Arabic
- 🚀 FastAPI backend
- 💻 Simple browser-based interface
- ❤️ Health and model-readiness API endpoints
- 📦 Easy local setup for Windows, macOS, and Linux

---

## 🏗️ Project Structure

```text
SkinScope/
│
├── app/
│   ├── main.py
│   └── ...
│
├── model/
│   └── trained model files
│
├── requirements.txt
├── run.sh
└── README.md
```

> The exact structure may vary depending on the files included in your repository.

---

## ⚙️ Requirements

Recommended environment:

- **Python 3.11**
- At least **4 GB available RAM**
- Internet connection during the first setup to install dependencies

Python 3.11 is recommended for better compatibility with the TensorFlow environment.

---

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone <YOUR_GITHUB_REPOSITORY_URL>
cd SkinScope
```

### 2. Install dependencies

#### Windows

Open Command Prompt or PowerShell inside the project folder:

```bash
py -m pip install -r requirements.txt
```

#### macOS / Linux

```bash
python3 -m pip install -r requirements.txt
```

---

## ▶️ Run the Application

### Windows

```bash
py -m uvicorn app.main:app --host 0.0.0.0 --port 8080
```

### macOS / Linux

```bash
chmod +x run.sh
./run.sh
```

After the server starts, open:

**http://localhost:8080**

---

## 🔌 API

SkinScope provides the following endpoints:

| Method | Endpoint | Description |
|---|---|---|
| `GET` | `/api/healthz` | Checks whether the service is running |
| `GET` | `/api/ready` | Checks model readiness |
| `POST` | `/api/predict` | Uploads an image and returns the prediction |

### Prediction Request

Send an image using the `file` form field:

```text
POST /api/predict
```

### Example Response

```json
{
  "label_en": "Acne",
  "label_ar": "حب الشباب",
  "disease": {
    "english": "Acne",
    "arabic": "حب الشباب"
  }
}
```

---

## 🧠 How It Works

The application follows a simple pipeline:

```text
User uploads image
        ↓
FastAPI receives image
        ↓
Image preprocessing
        ↓
TensorFlow model
        ↓
Disease classification
        ↓
English + Arabic result
        ↓
Displayed to the user
```

---

## 🎯 Purpose

The goal of SkinScope is to demonstrate how a trained **computer vision / deep learning model** can be integrated into a real web application.

The project combines:

- Deep Learning
- Computer Vision
- TensorFlow
- FastAPI
- Python
- Web-based AI inference

---

## 🌐 Supported Results

The application returns disease names in both **English and Arabic**, making the prediction interface more accessible to Arabic-speaking users.

The available disease classes depend on the classes used to train the included model.

---

## ⚠️ Medical Disclaimer

SkinScope is intended for **educational and informational purposes only**.

AI image classification can make incorrect predictions. The result should **not** be considered a professional medical diagnosis, and users should consult a qualified healthcare professional for medical advice, diagnosis, or treatment.

---

## 👨‍💻 Author

**Abdullah Omar Ramadan**

Computer Science / AI & Machine Learning Student

---

## ⭐ If You Find This Project Useful

Feel free to ⭐ star the repository and use the project as a learning reference for deploying deep-learning computer vision models as web applications.
