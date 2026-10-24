# Vehicle Damage Detection Using Deep Learning

## Project Overview
This project uses deep learning and computer vision to classify vehicle images into six categories based on vehicle orientation and damage type. A ResNet50 model is integrated with a FastAPI backend to provide predictions through a REST API.

## Objectives
- Classify vehicle images into front and rear categories.
- Identify normal, crushed, and breakage conditions.
- Expose the trained model through an API for image-based predictions.

## Technologies Used
- **Python** – Core programming language
- **PyTorch** – Deep learning and model inference
- **ResNet50** – Pretrained convolutional neural network using transfer learning
- **FastAPI** – REST API development
- **Pillow (PIL)** – Image loading and preprocessing
- **Uvicorn** – ASGI server for running the API

## Dataset and Classification
The project README reports a dataset of approximately 1,700 images and six target classes:

1. Front Normal
2. Front Crushed
3. Front Breakage
4. Rear Normal
5. Rear Crushed
6. Rear Breakage

## Model Architecture
ResNet50 is used as the feature extraction backbone. The final classification layer is adapted for six output classes. The project uses image preprocessing, including resizing and normalization, before inference.

## Model Performance
The original project documentation reports approximately **80% validation accuracy**. This result has not been independently reproduced.

## API Details
The FastAPI backend accepts an image file and returns the predicted class.

**Endpoint:** `POST /predict`

**Example response:**
```json
{
  "prediction": "Rear Breakage"
}
```

## Installation and Setup

1. Clone the repository:
   ```bash
   git clone https://github.com/utsav2304/vehicle_damage_detection.git
   cd vehicle_damage_detection
   ```

2. Create and activate a virtual environment:
   ```bash
   python -m venv venv
   ```

   Windows:
   ```bash
   venv\Scripts\activate
   ```

   Linux/macOS:
   ```bash
   source venv/bin/activate
   ```

3. Install the dependencies:
   ```bash
   pip install -r requirements.txt
   ```

4. Start the server:
   ```bash
   uvicorn server:app --reload
   ```

   Ensure that the FastAPI application is named `app` inside `server.py`. The model weights and any required supporting files must also be present at the paths expected by the code.

5. Open the interactive API documentation:
   `http://127.0.0.1:8000/docs`

## Project Structure
```text
vehicle_damage_detection/
├── server.py
├── requirements.txt
├── README.md
└── model files and supporting modules
```

The actual model files and supporting modules
