# 🎓 Face Recognition Attendance Management System

[![Python](https://img.shields.io/badge/Python-3.13+-blue.svg)](https://www.python.org/)
[![Next.js](https://img.shields.io/badge/Next.js-15.5.4-black)](https://nextjs.org/)
[![Flask](https://img.shields.io/badge/Flask-3.1.2-green)](https://flask.palletsprojects.com/)
[![MongoDB](https://img.shields.io/badge/MongoDB-Latest-green)](https://www.mongodb.com/)

A modern, full-stack face recognition attendance system with both a legacy Tkinter GUI and a modern web application implementation.

---

## 📁 Project Structure

```
project/
├── backend/              # Flask REST API
│   ├── app.py           # Main Flask application
│   ├── auth/            # Authentication routes
│   ├── student/         # Student management
│   ├── teacher/         # Teacher & attendance management
│   ├── recognition.py   # Face recognition logic
│   └── requirements.txt # Python dependencies
│
├── frontend/            # Next.js Web Application
│   ├── app/            # Next.js pages & components
│   ├── package.json    # Node.js dependencies
│   └── public/         # Static assets
│
├── legacy-tkinter/      # Legacy Desktop Application
│   ├── attendance.py   # Main Tkinter GUI (old version)
│   ├── requirements.txt # Legacy dependencies
│   └── UI_Image/       # GUI assets
│
├── data/               # Data Storage
│   ├── StudentDetails/ # Student CSV data
│   └── TrainingImageLabel/ # Trained model labels
│
├── docs/               # Documentation & Screenshots
│   ├── Project Snap/   # UI screenshots
│   └── LEGACY_README.md # Original documentation
│
└── config/             # Configuration Files
    ├── _config.yml
    └── project_requirement.txt
```

---

## 🚀 Quick Start

### **Modern Web Application (Recommended)**

#### Prerequisites
- Python 3.13+
- Node.js 18+
- MongoDB (local or Atlas)

#### 1. **Backend Setup**

```bash
cd backend

# Install Python dependencies
pip install -r requirements.txt

# The app will use default MongoDB connection: mongodb://localhost:27017/
# To customize, create a .env file (optional):
# MONGODB_URI=mongodb://localhost:27017/
# DATABASE_NAME=facerecognition

# Start Flask server
python app.py
```

Backend will run on: **http://127.0.0.1:5000**

#### 2. **Frontend Setup**

```bash
cd frontend

# Install Node.js dependencies
npm install

# Start Next.js development server
npm run dev
```

Frontend will run on: **http://localhost:3000**

---

## 🎯 Features

### **Modern Web App**
- ✅ **User Authentication**: Separate student & teacher accounts
- ✅ **Face Registration**: Capture and store student facial data
- ✅ **Real-time Recognition**: MTCNN + DeepFace (Facenet512)
- ✅ **Attendance Tracking**: Session-based attendance management
- ✅ **Export Records**: Download attendance as Excel/CSV
- ✅ **Responsive UI**: Modern, mobile-friendly interface
- ✅ **MongoDB Integration**: Persistent data storage

### **Legacy Tkinter App**
- Desktop GUI application
- OpenCV-based face detection
- Local file storage (CSV)
- See `docs/LEGACY_README.md` for instructions

---

## 🛠️ Technology Stack

### **Backend**
- **Flask** - REST API framework
- **DeepFace** - Face recognition (Facenet512)
- **MTCNN** - Face detection
- **MongoDB** - Database
- **PyMongo** - MongoDB driver
- **Flask-CORS** - Cross-origin support
- **Flask-Bcrypt** - Password hashing

### **Frontend**
- **Next.js 15** - React framework
- **TypeScript** - Type safety
- **TailwindCSS** - Styling
- **Lucide React** - Icons
- **Framer Motion** - Animations

---

## 📊 Database Collections

The MongoDB database (`facerecognition`) uses the following collections:

| Collection | Description |
|------------|-------------|
| `students` | Student profiles with face embeddings |
| `auth_users` | Student authentication credentials |
| `auth_teachers` | Teacher authentication credentials |
| `attendance_records` | Attendance session logs |

---

## 🔐 API Endpoints

### **Authentication**
- `POST /api/signup` - Register new user (student/teacher)
- `POST /api/signin` - User login
- `POST /api/logout` - User logout

### **Student Management**
- `GET /api/students` - List all students
- `POST /api/register-student` - Register student with face data
- `PUT /api/update-student/<id>` - Update student info
- `DELETE /api/delete-student/<id>` - Remove student

### **Attendance**
- `POST /api/attendance/create_session` - Start attendance session
- `POST /api/attendance/real-mark` - Mark attendance via face recognition
- `POST /api/attendance/end_session` - End attendance session
- `GET /api/attendance` - View attendance records
- `GET /api/attendance/export` - Export attendance data

### **Demo & Testing**
- `POST /api/demo/recognize` - Test face recognition
- `GET /api/demo/models/status` - Check model health

---

## 📝 Configuration

### **MongoDB Connection**

Default: `mongodb://localhost:27017/`

To use MongoDB Atlas or custom URI:

1. Create `.env` file in `backend/`:
```env
MONGODB_URI=mongodb+srv://user:pass@cluster.mongodb.net/
DATABASE_NAME=facerecognition
COLLECTION_NAME=students
THRESHOLD=0.6
```

---

## 🎨 Running Legacy Tkinter App

```bash
cd legacy-tkinter

# Install dependencies
pip install -r requirements.txt

# Run the GUI
python attendance.py
```

See `docs/LEGACY_README.md` for detailed instructions.

---

## 🐛 Troubleshooting

### **Backend Issues**

**Error: "Employee ID required for teachers"**
- Ensure frontend signup form includes Employee ID field
- Fixed in latest version

**Model download slow:**
- First run downloads ~95MB Facenet512 model
- Cached to `~/.deepface/weights/`
- Subsequent runs are faster

**MongoDB connection error:**
- Verify MongoDB is running: `Get-Service -Name MongoDB`
- Check connection string in `.env`

### **Frontend Issues**

**Port 3000 already in use:**
```bash
# Use different port
PORT=3001 npm run dev
```

---

## 📸 Screenshots

See `docs/Project Snap/` for UI screenshots of both legacy and modern versions.

---

## 🤝 Contributing

This is a reorganized and enhanced version of the original face recognition attendance system. The folder structure has been cleaned up for better maintainability.

---

## 📄 License

See original repository for license information.

---

## 🌟 Acknowledgments

- Original Legacy Implementation: Tkinter + OpenCV
- Modern Implementation: Next.js + Flask + DeepFace
- Face Recognition: DeepFace library (Facenet512 model)
- Face Detection: MTCNN

---

**Happy Coding! 🚀**
