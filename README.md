# MY-Brain-Tumour-Project
<img width="1159" height="813" alt="image" src="https://github.com/user-attachments/assets/e5c4ce37-e6db-4bcb-b296-34ae2284b7c2" />
🧠 NeuroVision AI: Deep Learning Brain Tumor Detection & Analysis
"Illuminating the unseen, one pixel at a time."

🔬 The Vision
In neuro-oncology, time isn't just money—it's millions of irreplaceable neurons. NeuroVision AI is an advanced computer vision platform designed to assist radiologists by rapidly identifying, classifying, and segmenting brain tumors from Magnetic Resonance Imaging (MRI) scans.
By combining deep convolutional neural networks (CNNs) with explainable AI (XAI) attention heatmaps, NeuroVision acts as a second pair of eyes for medical professionals, delivering rapid diagnostic insights without operating as a black box.
⚡ Key Features
🩺 Multi-Class Tumor Classification: Accurately categorizes MRI scans across four distinct states:
Glioma
Meningioma
Pituitary Tumor
No Tumor (Healthy Control)
🎯 Explainable AI (Grad-CAM Integration): Visualizes model focus areas using Gradient-weighted Class Activation Mapping, generating heatmaps over the precise anatomical structures driving predictions.
🚀 Production-Ready Inference API: Asynchronous REST backend built with FastAPI, supporting sub-second inference times and batch processing.
🐳 Containerized & Portable: Fully Dockerized deployment with isolated runtime environments for seamless cloud or on-premise clinical deployment.
🛡️ Robust Data Preprocessing Pipeline: Built-in CLAHE (Contrast Limited Adaptive Histogram Equalization), skull-stripping, and artifact removal algorithms to handle varied MRI scan origins.
🏗️ System Architecture
  ┌─────────────────┐       ┌──────────────────────┐       ┌────────────────────────┐
  │   Input MRI     │  ───► │  Preprocessing Engine│  ───► │   Deep Convolutional   │
  │   (DICOM/PNG)   │       │ (CLAHE + Normalizer) │       │   Backbone (EfficientNet)│
  └─────────────────┘       └──────────────────────┘       └───────────┬────────────┘
                                                                       │
                                                                       ▼
  ┌─────────────────┐       ┌──────────────────────┐       ┌────────────────────────┐
  │ Clinical Decision│ ◄─── │  Grad-CAM Explainability│ ◄─── │ Classification &       │
  │ Support Interface│       │  Heatmap Generator   │       │ Confidence Score       │
  └─────────────────┘       └──────────────────────┘       └────────────────────────┘
🛠️ Tech Stack
Core Framework: Python 3.10+, PyTorch, Torchvision
Computer Vision & Image Processing: OpenCV, PIL, Scikit-Image, Albumentations
Explainable AI: Captum / Grad-CAM PyTorch
Backend API: FastAPI, Uvicorn, Pydantic
DevOps & Containerization: Docker, Docker Compose, MLflow
🚀 Quick Start
Prerequisites
Ensure you have the following installed on your machine:
Python 3.10 or higher
CUDA-compatible GPU (Optional, for hardware acceleration)
Docker Desktop (Optional, for containerized run)
Installation
Clone the Repository
Bash
git clone https://github.com/your-username/neurovision-ai.git
cd neurovision-ai
Set Up Virtual Environment
Bash
python -m venv venv
source venv/bin/activate  # On Windows use: venv\Scripts\activate
Install Dependencies
Bash
pip install --upgrade pip
pip install -r requirements.txt
Running the System
Option A: Local FastAPI Server
Bash
uvicorn app.main:app --host 0.0.0.0 --port 8000 --reload
Access the interactive API documentation at http://localhost:8000/docs.
Option B: Docker Deployment
Bash
docker build -t neurovision-ai:latest .
docker run -p 8000:8000 --gpus all neurovision-ai:latest
📊 Performance Metrics
Evaluated on the benchmark Kaggle Brain Tumor MRI Dataset (7,023 images across 4 categories):
Tumor Category	Precision	Recall	F1-Score
Glioma	0.96	0.95	0.95
Meningioma	0.94	0.96	0.95
Pituitary	0.98	0.98	0.98
No Tumor	0.97	0.96	0.97
Overall Accuracy	—	—	96.5%
📁 Project Structure
neurovision-ai/
├── app/
│   ├── api/             # FastAPI routes and endpoints
│   ├── core/            # Model loading & inference logic
│   ├── preprocessing/   # Image transformation routines
│   └── main.py          # Application entrypoint
├── models/              # Model architectures & weights (.pth)
├── notebooks/           # Training and evaluation experiments
├── tests/               # Unit and integration test suite
├── Dockerfile           # Docker container blueprint
├── requirements.txt     # Python dependencies
└── README.md            # Project documentation
⚠️ Medical Disclaimer
IMPORTANT: This software is developed purely for research, educational, and clinical decision-support experimentation. It is NOT a certified diagnostic medical device and should NEVER replace professional medical evaluations, clinical judgments, or formal diagnosis by a qualified radiologist or medical professional.

📄 License
Distributed under the MIT License. See LICENSE for more information.
