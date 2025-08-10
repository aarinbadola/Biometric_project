# 🔐 Biometric Project – Face Recognition + Active Liveness Detection

A full-stack biometric authentication system using **face recognition** and **active liveness detection** (blink/head-move detection).  
It allows secure user registration, authentication, and real-time video-based verification via webcam or uploaded video.

---

## 📌 Features

- 🧠 **Face Recognition** using embeddings and threshold-based matching.
- 👁️ **Active Liveness Detection** – Detects blinking and head movement to prevent spoofing.
- 📷 Webcam support + video upload processing.
- 🔒 **Encrypted storage** of biometric data.
- 🌐 **Full-stack architecture** – Backend API + frontend UI.
- 📜 Access logs for all authentication attempts.

---

## 🚀 Tech Stack

**Backend:**
- Python 3
- FastAPI / Flask (configurable)
- OpenCV
- face_recognition
- NumPy
- cryptography

**Frontend:**
- HTML / CSS / JavaScript
- WebRTC (for live video streaming)
- Fetch API for backend communication

**Database & Storage:**
- PostgreSQL / SQLite
- Encrypted local storage for images

---

## 📂 Project Structure
Biometric_project/
│
├── README.md # Project documentation
├── requirements.txt # Python dependencies
├── .gitignore # Ignore unnecessary files
│
├── backend/
│ ├── main.py # Starts FastAPI/Flask server
│ ├── config.py # Config variables (DB URL, thresholds, keys)
│ │
│ ├── routes/
│ │ ├── init.py
│ │ ├── liveness_routes.py # Endpoints for liveness detection
│ │ ├── face_routes.py # Endpoints for face match/register
│ │ └── auth_routes.py # Login / JWT authentication
│ │
│ ├── services/
│ │ ├── init.py
│ │ ├── liveness_service.py # Liveness logic (blink, head movement)
│ │ ├── face_match.py # Face embedding & matching logic
│ │ └── video_processing.py # Frame extraction & preprocessing
│ │
│ ├── utils/
│ │ ├── init.py
│ │ ├── logger.py # Logs authentication attempts
│ │ └── encryption.py # File/data encryption
│ │
│ └── storage/ # Encrypted face data
│
├── frontend/
│ ├── index.html # Main web UI
│ ├── styles.css # Styling
│ └── scripts.js # API communication + webcam capture
│
└── tests/
├── test_liveness.py
├── test_face_match.py
└── test_auth.py

## Create and activate virtual environment
python -m venv venv
source venv/bin/activate   # Mac/Linux
venv\Scripts\activate      # Windows

## Install dependencies
pip install -r requirements.txt

## Configure environment
-Edit backend/config.py to set:
-Database connection
-Matching threshold
-API keys (if applicable)

## Start the backend
cd backend
uvicorn main:app --reload

# 📡 API Endpoints

| Method | Endpoint       | Description                     |
|--------|---------------|---------------------------------|
| `POST` | `/api/register` | Register a new face             |
| `POST` | `/api/verify`   | Verify face & liveness          |
| `GET`  | `/api/logs`     | Get access logs                 |

---

# 🔐 Security Features

- **AES encryption** for stored images
- **Threshold-based matching** for accurate recognition
- **Active liveness detection** to prevent photo/video spoofing
- **JWT authentication** for secure API access

---

# 🧪 Running Tests

```bash
pytest tests/

## 🤝 Contributing

Fork this repository  

Create a feature branch:  
```bash
git checkout -b feature-name


📜 License
MIT License © 2025 aarinbadola & yudhveer10



AARIN