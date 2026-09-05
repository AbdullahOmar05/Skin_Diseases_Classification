# SkinScope — Skin Disease Detector

This folder is a standalone copy of the application. It includes the trained
TensorFlow model, the English upload interface, and bilingual disease results
(English and Arabic).

## Requirements

- Python 3.11 recommended
- At least 4 GB of available RAM
- Internet access the first time, so Python can install the dependencies

## macOS / Linux

Open a terminal inside this folder and run:

```bash
chmod +x run.sh
./run.sh
```

Then open **http://localhost:8080** in your browser.

## Windows

Install Python 3.11, open Command Prompt inside this folder, and run:

```bat
py -m pip install -r requirements.txt
py -m uvicorn app.main:app --host 0.0.0.0 --port 8080
```

Then open **http://localhost:8080**.

## API

- `GET /api/healthz` — service health
- `GET /api/ready` — model readiness
- `POST /api/predict` — upload an image using the `file` form field

The prediction response includes:

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

## Important

This application is for informational purposes only. It does not replace a
professional medical diagnosis.