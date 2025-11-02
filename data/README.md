# Data Storage Directory

This folder contains data files used by the legacy Tkinter application.

## 📁 Structure

```
data/
├── StudentDetails/
│   └── studentdetails.csv    # Student information (legacy app)
│
└── TrainingImageLabel/
    └── Trainner.yml          # Trained face recognition model (OpenCV)
```

## ℹ️ Important Notes

### Legacy Application Data

These directories are used by the **legacy Tkinter application** in `../legacy-tkinter/`:

- **StudentDetails/**: Stores student enrollment information in CSV format
- **TrainingImageLabel/**: Contains trained OpenCV cascade classifier data

### Modern Application Data

The **modern web application** (`../backend/` + `../frontend/`) uses:
- **MongoDB** for all data storage
- No file-based storage for student/attendance data
- Face embeddings stored in MongoDB collections

## 🔒 .gitignore

These directories should be in `.gitignore` to avoid committing:
- Personal student data
- Trained models
- Face images

## 📝 CSV Format (Legacy)

`StudentDetails/studentdetails.csv` format:
```csv
Id,Name
1,John Doe
2,Jane Smith
```

## 🔄 Migration

To migrate from legacy to modern system:
1. Export student data from CSV
2. Register students through the modern web interface
3. Capture new face images using the web app's registration feature

## 🗂️ Backup Recommendation

Always backup this directory before:
- Upgrading the system
- Re-training models
- Making bulk changes

---

For more information, see:
- Legacy app: `../legacy-tkinter/README.md`
- Modern app: `../README.md`
