Biometric Face Recognition & Active Liveness Detection
This project is a full-stack biometric authentication system that combines face recognition with active liveness detection (blink, head movement, etc.) to ensure secure identity verification.

It’s built with:

Backend: FastAPI (Python)

Face Recognition: face-recognition library

Liveness Detection: OpenCV + MediaPipe

Database: PostgreSQL

Frontend (optional): HTML/CSS/JS for webcam UI

📂 Project Structure
plaintext
Copy
Edit
Biometric_project/
│
├── README.md                  # Project description, setup, usage
├── requirements.txt           # Python dependencies
├── .gitignore                  # Ignore unnecessary files
│
├── backend/                    # Backend code
│   ├── main.py                  # FastAPI entry point
│   ├── config.py                # Config variables (DB, thresholds, keys)
│   │
│   ├── routes/                  # API routes
│   │   ├── __init__.py
│   │   ├── liveness_routes.py   # Liveness endpoints
│   │   ├── face_routes.py       # Face match/register endpoints
│   │   └── auth_routes.py       # Authentication endpoints
│   │
│   ├── services/                # Core logic
│   │   ├── __init__.py
│   │   ├── liveness_service.py  # Liveness detection logic
│   │   ├── face_match.py        # Face embeddings & matching
│   │   └── video_processing.py  # Frame extraction & preprocessing
│   │
│   ├── utils/                   # Helper utilities
│   │   ├── __init__.py
│   │   ├── logger.py            # Logs verification attempts
│   │   └── encryption.py        # Encryption utilities
│   │
│   └── storage/                 # Encrypted image data
│
├── frontend/                    # Optional frontend
│   ├── index.html               # Webcam capture UI
│   ├── styles.css
│   └── scripts.js               # Sends data to API
│
└── tests/                       # Automated tests
    ├── test_liveness.py
    ├── test_face_match.py
    └── test_auth.py
🚀 Features
✅ Face Registration — Store encrypted face embeddings in a secure database.
✅ Face Verification — Match a new image/video against registered faces.
✅ Active Liveness Detection — Detect blinking, head turns, and expressions.
✅ Encrypted Storage — All biometric data stored securely.
✅ JWT Authentication — Secure API access.
✅ Webcam Frontend (optional) — For real-time capture & verification.

📦 Installation
1️⃣ Clone the repository
bash
Copy
Edit
git clone https://github.com/yourusername/biometric_project.git
cd biometric_project
2️⃣ Install dependencies
bash
Copy
Edit
pip install -r requirements.txt
3️⃣ Setup PostgreSQL database
sql
Copy
Edit
CREATE DATABASE biometrics;
Update backend/config.py with your database credentials:

python
Copy
Edit
DB_URL = "postgresql://username:password@localhost/biometrics"
4️⃣ Run the backend
bash
Copy
Edit
cd backend
uvicorn main:app --reload
Backend runs at:
➡️ http://127.0.0.1:8000/docs (Swagger API docs)

🖥️ Frontend (Optional)
If you want a browser-based UI:

Open frontend/index.html in your browser

Allow webcam access

Capture & send images/videos to the backend API

📡 API Endpoints
Method	Endpoint	Description
POST	/face/register	Register a new user's face
POST	/face/match	Verify face against DB
POST	/liveness/check	Check if the user is live (blink/head move)
POST	/auth/login	Get JWT token
GET	/auth/me	Get logged-in user info

🧪 Running Tests
bash
Copy
Edit
pytest tests/
🔒 Security Notes
All stored biometric data is AES encrypted before saving.

JWT tokens are used for API access control.

HTTPS is recommended for deployment.

📜 License
MIT License — You’re free to use, modify, and distribute this project.

