# 📁 Project Folder Structure

This document explains the reorganized folder structure of the Face Recognition Attendance Management System.

## 🎯 Overview

The project has been reorganized from a messy root directory into a clean, professional structure that separates:
- **Modern web application** (backend + frontend)
- **Legacy desktop application** (Tkinter)
- **Data storage**
- **Documentation**
- **Configuration files**

---

## 📂 Complete Directory Structure

```
project-root/
│
├── 📁 backend/                    # Flask REST API Server
│   ├── app.py                     # Main Flask application
│   ├── recognition.py             # Face recognition logic
│   ├── requirements.txt           # Python dependencies
│   │
│   ├── 📁 auth/                   # Authentication module
│   │   └── routes.py              # Login, signup, logout
│   │
│   ├── 📁 student/                # Student management
│   │   ├── registration.py        # Student registration with face data
│   │   ├── updatedetails.py       # Update student information
│   │   ├── demo_session.py        # Demo face recognition
│   │   └── view_attendance.py     # Student attendance view
│   │
│   └── 📁 teacher/                # Teacher management
│       └── attendance_records.py  # Attendance session management
│
├── 📁 frontend/                   # Next.js Web Application
│   ├── 📁 app/                    # Next.js App Router pages
│   │   ├── page.tsx               # Homepage
│   │   ├── signup/                # Signup page
│   │   ├── signin/                # Login page
│   │   ├── dashboard/             # Main dashboard
│   │   ├── student/               # Student features
│   │   └── teacher/               # Teacher features
│   │
│   ├── 📁 public/                 # Static assets
│   ├── package.json               # Node.js dependencies
│   ├── tsconfig.json              # TypeScript config
│   └── next.config.ts             # Next.js config
│
├── 📁 legacy-tkinter/             # Legacy Desktop Application
│   ├── README.md                  # Legacy app documentation
│   ├── attendance.py              # Main GUI entry point
│   ├── automaticAttedance.py      # Auto attendance logic
│   ├── show_attendance.py         # View attendance
│   ├── takeImage.py               # Capture face images
│   ├── trainImage.py              # Train face model
│   ├── takemanually.py            # Manual attendance
│   ├── test.py                    # Testing utilities
│   ├── requirements.txt           # Legacy dependencies
│   ├── AMS.ico                    # App icon
│   ├── 📁 UI_Image/               # GUI images
│   ├── haarcascade_frontalface_alt.xml
│   └── haarcascade_frontalface_default.xml
│
├── 📁 data/                       # Data Storage (Legacy App)
│   ├── README.md                  # Data directory documentation
│   ├── 📁 StudentDetails/         # Student CSV files
│   │   └── studentdetails.csv     # Student information
│   └── 📁 TrainingImageLabel/     # Trained models
│       └── Trainner.yml           # OpenCV cascade model
│
├── 📁 docs/                       # Documentation & Media
│   ├── LEGACY_README.md           # Original README
│   └── 📁 Project Snap/           # UI Screenshots
│       ├── 1.PNG
│       ├── 2.PNG
│       └── ... (more screenshots)
│
├── 📁 config/                     # Configuration Files
│   ├── _config.yml                # Jekyll/GitHub Pages config
│   └── project_requirement.txt    # Original requirements doc
│
├── 📁 .idea/                      # IDE settings (PyCharm)
├── 📁 .vscode/                    # IDE settings (VS Code)
│
├── .gitignore                     # Git ignore rules
├── README.md                      # Main project README
└── FOLDER_STRUCTURE.md            # This file

```

---

## 🔍 Directory Details

### **1. `/backend/` - Flask API Server**

**Purpose**: Modern REST API for the web application

**Key Files**:
- `app.py` - Flask app initialization, model loading, blueprint registration
- `recognition.py` - Face detection and recognition logic
- `requirements.txt` - Python packages (Flask, DeepFace, MTCNN, MongoDB)

**Technologies**:
- Flask 3.1.2
- DeepFace (Facenet512)
- MTCNN face detection
- MongoDB (PyMongo)
- Flask-CORS, Flask-Bcrypt

**Runs on**: `http://127.0.0.1:5000`

---

### **2. `/frontend/` - Next.js Web App**

**Purpose**: Modern web interface for students and teachers

**Key Features**:
- Responsive UI with TailwindCSS
- TypeScript for type safety
- React 19 + Next.js 15
- Real-time face recognition
- Attendance management

**Runs on**: `http://localhost:3000`

---

### **3. `/legacy-tkinter/` - Desktop GUI App**

**Purpose**: Original Tkinter implementation (preserved for reference)

**Usage**: Standalone desktop application using OpenCV

**Note**: This is the **old version**. Use the modern web app for new deployments.

---

### **4. `/data/` - Data Storage**

**Purpose**: Legacy app data storage

**Contents**:
- Student CSV files (legacy)
- Trained OpenCV models (legacy)

**Note**: Modern web app uses **MongoDB** instead of file storage.

---

### **5. `/docs/` - Documentation**

**Purpose**: Project documentation and screenshots

**Contents**:
- Original README
- UI screenshots
- Project documentation

---

### **6. `/config/` - Configuration**

**Purpose**: Project configuration files

**Contents**:
- Jekyll config (for GitHub Pages)
- Original requirements document

---

## 🚀 Getting Started

### **Modern Web App (Recommended)**

```bash
# Terminal 1: Backend
cd backend
pip install -r requirements.txt
python app.py

# Terminal 2: Frontend
cd frontend
npm install
npm run dev
```

### **Legacy Desktop App**

```bash
cd legacy-tkinter
pip install -r requirements.txt
python attendance.py
```

---

## 🔄 Changes Made

### **Before Reorganization** ❌
```
project-root/
├── attendance.py
├── automaticAttedance.py
├── show_attendance.py
├── ... (10+ Python files in root)
├── haarcascade files in root
├── UI_Image/
├── StudentDetails/
├── backend/
├── frontend/
└── ... (messy structure)
```

### **After Reorganization** ✅
```
project-root/
├── backend/          # Clean API structure
├── frontend/         # Clean web app
├── legacy-tkinter/   # Legacy app isolated
├── data/            # Data organized
├── docs/            # Documentation organized
├── config/          # Configs organized
└── README.md        # Comprehensive docs
```

---

## 📝 Key Benefits

1. **Separation of Concerns**: Modern and legacy code separated
2. **Clean Root**: Only essential directories in root
3. **Better Navigation**: Easy to find files
4. **Professional Structure**: Industry-standard organization
5. **Clear Documentation**: README in each major folder
6. **Version Control**: Better .gitignore structure

---

## 🛡️ Security

**.gitignore** protects:
- Environment variables (`.env`)
- Student data (`data/StudentDetails/*.csv`)
- Trained models (`data/TrainingImageLabel/*.yml`)
- Python cache (`__pycache__/`)
- Training images (`TrainingImage/`)

---

## 📚 Further Reading

- Main README: `README.md`
- Legacy app docs: `legacy-tkinter/README.md`
- Data directory: `data/README.md`
- Original README: `docs/LEGACY_README.md`

---

**Last Updated**: October 30, 2025  
**Status**: ✅ Reorganization Complete
