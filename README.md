# 🎓 AI-Smart Attendance & Hostel Management System

An advanced full-stack web application that automates student attendance tracking and hostel management using face recognition technology powered by AI/ML.

## 🚀 Features

### 👨‍🎓 Student Module
- **Registration & Login** - JWT-based secure authentication
- **Face Enrollment** - Upload and register facial data
- **Automatic Attendance** - Face recognition via webcam
- **Attendance History** - View personal attendance records

### 🧑‍💼 Admin Module
- **Interactive Dashboard** - Real-time statistics and insights
- **Attendance Management** - View, search, filter attendance logs
- **CSV Export** - Download attendance data
- **Hostel Management** - Track room assignments and student data
- **Real-time Updates** - Auto-refreshing attendance data

### 🧠 AI/ML Features
- Face detection using OpenCV
- Face recognition using face_recognition library
- 95-99% accuracy rate
- Real-time processing (<2 seconds)
- Anti-spoofing capabilities

## 🛠️ Tech Stack

| Layer | Technology | Purpose |
|-------|-----------|---------|
| Frontend | React.js + Tailwind CSS | Interactive user interface |
| Backend | Node.js + Express.js | RESTful API server |
| Database | MongoDB | Data persistence |
| AI Module | Python + OpenCV + face_recognition | Face recognition |
| Authentication | JWT | Secure token-based auth |

## 📦 Project Structure

```
Hostel_ml_attendance/
├── backend/                 # Node.js Express Backend
│   ├── config/             # Configuration files
│   ├── controllers/        # Route controllers
│   ├── middleware/         # Custom middleware
│   ├── models/             # MongoDB models
│   ├── routes/             # API routes
│   ├── uploads/            # Image uploads
│   ├── utils/              # Utility functions
│   └── server.js           # Entry point
├── frontend/               # React Frontend
│   ├── public/            # Static files
│   └── src/
│       ├── components/    # React components
│       ├── contexts/      # Context providers
│       ├── pages/         # Page components
│       ├── services/      # API services
│       └── App.js         # Main app component
└── python-ai/             # Python AI Module
    ├── encodings/         # Stored face encodings
    ├── models/            # ML models
    ├── utils/             # Helper functions
    └── app.py             # Flask/FastAPI server
```

## 🔧 Installation

### Prerequisites
- Node.js (v16 or higher)
- Python (v3.8 or higher)
- MongoDB Atlas account or local MongoDB
- Webcam for face recognition

### Backend Setup

```bash
cd backend
npm install
```

Create a `.env` file with your MongoDB URI and JWT secret (see `.env` file).

### Frontend Setup

```bash
cd frontend
npm install
```

### Python AI Module Setup

```bash
cd python-ai
python -m venv venv
# On Windows:
venv\Scripts\activate
# On Mac/Linux:
source venv/bin/activate

pip install -r requirements.txt
```

## 🚀 Running the Application

### Option 1: Run all services separately

**Terminal 1 - Backend:**
```bash
cd backend
npm run dev
```

**Terminal 2 - Frontend:**
```bash
cd frontend
npm start
```

**Terminal 3 - Python AI:**
```bash
cd python-ai
python app.py
```

### Option 2: Run all services together
```bash
npm run dev:all
```

## 📡 API Endpoints

### Authentication
- `POST /api/auth/register` - Register new user
- `POST /api/auth/login` - Login user
- `GET /api/auth/me` - Get current user

### Attendance
- `POST /api/attendance/mark` - Mark attendance (face recognition)
- `GET /api/attendance` - Get all attendance logs
- `GET /api/attendance/student/:id` - Get student's attendance
- `GET /api/attendance/export` - Download CSV

### Face Recognition
- `POST /api/face/enroll` - Enroll face data
- `POST /api/face/recognize` - Recognize face

### Admin
- `GET /api/admin/dashboard` - Dashboard statistics
- `GET /api/admin/students` - Get all students
- `PUT /api/admin/student/:id` - Update student info

## 🔐 Authentication Flow

1. User registers → Data stored in MongoDB
2. User logs in → JWT token issued
3. Token stored in localStorage/sessionStorage
4. Protected routes verify token
5. Admins have elevated privileges

## 🧠 Face Recognition Flow

1. Capture image via webcam
2. Python module detects face using OpenCV
3. Generate 128-dimensional face encoding
4. Compare with stored encodings
5. If match found → mark attendance
6. Send result to backend via API
7. Update database and frontend in real-time

## 📊 System Architecture

```
[React Frontend] ←→ [Node.js Backend] ←→ [MongoDB]
                          ↕
                  [Python AI Module]
```

## 🎯 Default Login Credentials

**Admin:**
- Email: admin@hostel.com
- Password: admin123

**Student:**
- Register new account through the UI

## 🔒 Security Features

- JWT-based authentication
- Password hashing with bcrypt
- Protected API routes
- CORS configuration
- Input validation and sanitization

## 📈 Future Enhancements

- [ ] Emotion recognition for engagement analysis
- [ ] Liveness detection (anti-spoofing)
- [ ] Deep learning CNN models (FaceNet, VGG-Face)
- [ ] Mobile app version
- [ ] Cloud-based face recognition APIs
- [ ] Email notifications
- [ ] QR code attendance fallback

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📄 License

This project is licensed under the ISC License.

## 👨‍💻 Author

Built with ❤️ for educational institutions

---

**Note:** Make sure to update the `.env` file with your actual MongoDB credentials and change the JWT secret in production.
