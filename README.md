# Face_Recognition_Aanti-spoof
Face Recognition with Silent Face Anti-Spoofing
📘 Overview

This project implements a Face Recognition Attendance System with Real-time Anti-Spoofing Detection to prevent fraudulent access using printed photos or video replays.
It combines face recognition and liveness detection modules using deep learning models.

⚙️ Project Structure
Face_Recognition_Anti-spoof/
│
├── Face_reco_liv/
│   └── pythonProject/
│       └── Silent-Face-Anti-Spoofing/
│           ├── datasets/
│           ├── images/
│           ├── resources/
│           │   ├── anti_spoof_models/
│           │   │   ├── 2.7_80x80_MiniFASNetV2.pth
│           │   │   ├── 4_0_0_80x80_MiniFASNetV1SE.pth
│           │   └── detection_model/
│           │       ├── deploy.prototxt
│           │       └── Widerface-RetinaFace.caffemodel
│           ├── src/
│           ├── requirements.txt
│           ├── test.py
│           └── train.py
│
├── face-attendance-system/
│   ├── db/
│   ├── main.py
│   ├── util.py
│   ├── Aadish.pickle
│   ├── requirements.txt
│   └── log.txt
│
└── README.md

🧩 Core Components
1. Face Detection

Uses RetinaFace (deploy.prototxt + Widerface-RetinaFace.caffemodel)

Detects and crops faces from camera frames.

2. Anti-Spoofing Model

Based on Silent Face Anti-Spoofing (MiniFASNet architectures).

Predicts if the detected face is real or spoof (photo/video attack).

3. Face Recognition

Encodes and matches faces using stored embeddings (Aadish.pickle).

Used for attendance marking or authentication.

4. Attendance System Integration

Logs recognized faces in the database (db/)

Maintains records of login time and user identity.

main.py integrates recognition and anti-spoof detection for real-time use.

🧠 Model Files
Model	Description
2.7_80x80_MiniFASNetV2.pth	Lightweight anti-spoofing model for live detection
4_0_0_80x80_MiniFASNetV1SE.pth	Enhanced version with SE attention module
Widerface-RetinaFace.caffemodel	Face detection backbone
deploy.prototxt	RetinaFace architecture definition
🧪 Running the Project
🧰 1. Clone the Repository
git clone https://github.com/<your-username>/Face_Recognition_Anti-spoof.git
cd Face_Recognition_Anti-spoof/face-attendance-system

📦 2. Install Dependencies

For Linux/macOS:

pip install -r requirements.txt


For Windows:

pip install -r requirements_windows.txt

🎥 3. Run Face Attendance with Anti-Spoofing
python main.py

🧩 4. To Test Anti-Spoofing Separately
cd ../Face_reco_liv/pythonProject/Silent-Face-Anti-Spoofing
python test.py

🧠 5. To Train / Fine-tune Model
python train.py

🖼️ Output

Detects faces from live video feed

Displays “Real Face” or “Spoof Detected” label

Logs recognized users in the attendance record

🧾 Requirements
Library	Purpose
OpenCV	Video processing, frame handling
PyTorch	Model inference for MiniFASNet
Numpy	Array operations
Imutils	Frame resizing and convenience functions
Scikit-learn	Embedding and recognition utilities
🚀 Future Enhancements

Add web dashboard (FastAPI + React frontend)

Support for multi-face recognition

Model optimization for edge devices (Jetson Nano / Raspberry Pi)

👨‍💻 Author

Aadish Parashar
Associate Project Manager | AI Engineer
