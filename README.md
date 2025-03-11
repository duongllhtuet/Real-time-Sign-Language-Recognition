Real-time Sign Language Recognition (ASL to Text/Speech)



📌 Overview

This project implements a real-time sign language recognition system that converts American Sign Language (ASL) gestures into text and speech. The system is designed for low-latency inference (≤ 100ms/frame) and can run on both cloud and edge devices.

🚀 Features

Real-time Gesture Recognition: Detects and classifies ASL signs from live webcam input.

Fast & Optimized Inference: Uses TensorRT and ONNX for acceleration.

Multi-Device Support: Runs on CPU, GPU, and edge devices (Jetson Nano, Raspberry Pi, etc.).

Extensible Model Architecture: Supports MediaPipe + Transformer, 3D CNN, and ST-GCN.

REST API & Web Interface: Provides a FastAPI backend and a React-based web client.

Comprehensive MLOps Pipeline: Includes data versioning (DVC), experiment tracking (MLflow), and CI/CD (GitHub Actions).

📂 Project Structure

📦 sign-language-recognition
├── 📁 data                # Datasets and annotations
├── 📁 models              # Pretrained models & training scripts
├── 📁 src                 # Core source code (detection, tracking, inference)
│   ├── inference.py       # Real-time inference pipeline
│   ├── train.py           # Training script
│   ├── preprocess.py      # Data preprocessing
│   ├── utils.py           # Utility functions
├── 📁 deployment          # Deployment scripts (Docker, Kubernetes, Jetson Nano)
├── 📁 webapp              # Web-based frontend (React.js)
├── 📄 requirements.txt    # Python dependencies
├── 📄 README.md           # Project documentation
├── 📄 LICENSE             # License file
└── 📄 .gitignore          # Git ignore file

🛠️ Installation

1️⃣ Clone the Repository

git clone https://github.com/yourusername/sign-language-recognition.git
cd sign-language-recognition

2️⃣ Set Up the Environment

pip install -r requirements.txt

For GPU acceleration, install TensorRT:

pip install nvidia-tensorrt

3️⃣ Run the Application

python src/inference.py --source webcam

🧠 Model Architecture

The system employs multiple architectures for gesture recognition:

MediaPipe Holistic + Transformer (Fast, real-time, lower accuracy)

ST-GCN (Spatial-Temporal Graph CNN) (Best for hand-body relations)

3D CNN (I3D, SlowFast) (End-to-end video-based recognition)

🚀 Deployment

🖥️ Local Deployment

uvicorn src.api:app --host 0.0.0.0 --port 8000

Access API at: http://localhost:8000/docs

🐳 Docker Deployment

docker build -t asl-recognition .
docker run -p 8000:8000 asl-recognition

☁️ Cloud Deployment (AWS Lambda)

cd deployment/aws
sh deploy.sh

📊 Experiment Tracking & Monitoring

MLflow: Tracks model training metrics.

Prometheus + Grafana: Monitors real-time inference latency.

Evidently AI: Detects data drift.

📚 References

MediaPipe Holistic

ST-GCN Paper

TensorRT Optimization

🔗 Contributing

We welcome contributions! Please follow our CONTRIBUTING.md guide.

📜 License

This project is licensed under the MIT License. See LICENSE for details.

