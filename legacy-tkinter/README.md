# Legacy Tkinter Desktop Application

This folder contains the original Tkinter-based desktop GUI implementation of the attendance system.

## ⚠️ Note

This is the **legacy version**. For the modern web-based application, please use the `backend/` and `frontend/` folders in the parent directory.

## 📋 Requirements

- Python 3.9+
- OpenCV
- Tkinter (usually comes with Python)
- See `requirements.txt` for full list

## 🚀 Quick Start

```bash
# Install dependencies
pip install -r requirements.txt

# Run the application
python attendance.py
```

## 📁 Files

- `attendance.py` - Main GUI application
- `automaticAttedance.py` - Automatic attendance marking logic
- `show_attendance.py` - Display attendance records
- `takeImage.py` - Capture student images
- `trainImage.py` - Train face recognition model
- `takemanually.py` - Manual attendance entry
- `test.py` - Testing utilities

## 🎯 Features

- Desktop GUI interface
- Face detection using OpenCV Haar Cascades
- Local CSV storage
- Automated and manual attendance modes
- Image training for face recognition

## 📖 Usage

1. **Register Student**
   - Click "Register a new student"
   - Enter ID and Name
   - Click "Take Image" to capture face photos
   - Click "Train Image" to train the model

2. **Take Attendance**
   - Click "Take Attendance"
   - Enter subject name
   - System will detect and mark attendance automatically

3. **View Attendance**
   - Click "View Attendance"
   - Select subject to view records

## 🔧 Configuration

Update file paths in:
- `attendance.py` (lines 32-43)
- `automaticAttedance.py`

## 📝 Data Storage

- Student details: `../data/StudentDetails/studentdetails.csv`
- Trained models: `../data/TrainingImageLabel/Trainner.yml`
- Images: Create `TrainingImage/` folder in this directory

## 🆕 Modern Alternative

For a better experience with web interface and MongoDB, use:
- **Backend**: `../backend/`
- **Frontend**: `../frontend/`

See parent README.md for details.
