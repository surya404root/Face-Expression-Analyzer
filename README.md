# 😀 Face-Expression-Analyzer

### Real-Time Facial Expression Detection using Python & Computer Vision

Face Expression Analyzer is a **computer vision based project** that detects **human faces** from a live camera feed and analyzes **facial expressions/emotions** such as **Happy, Sad, Angry, Neutral**, etc.  
It uses **OpenCV**, **Python**, and a **Flask web server** to display results in a browser.

This project is designed to be **simple, educational, and beginner-friendly**, while still demonstrating real-world AI concepts.

---

## 📸 What This Project Does

✔ Opens your camera  
✔ Detects human face in real time  
✔ Extracts facial features  
✔ Analyzes expression/emotion  
✔ Displays emotion label on face  
✔ Streams live output to browser  

---

## 🐍 Detailed Code Explanation

---

## 🔹 `app.py` (Main Backend File)

This is the **heart of the project**.

---

### 1️⃣ Importing Required Libraries

```python
import cv2
import numpy as np
from flask import Flask, render_template, Response
```
**Why these are used:**

• cv2 (OpenCV) → camera access & face detection
• numpy → image processing
• flask → web server & routing
• Response → live video streaming

### 2️⃣ Creating Flask Application
```
app = Flask(__name__)
```
✔ Initializes the web server

✔ Handles browser requests

✔ Displays live video feed

### 3️⃣ Loading Face Detection Model
```
face_cascade = cv2.CascadeClassifier(
    'haarcascade_frontalface_default.xml'
)
```
✔ Uses Haar Cascade Algorithm

✔ Pre-trained to detect frontal human faces

✔ Lightweight & fast

### 4️⃣ Starting the Camera
```
cap = cv2.VideoCapture(0)
```
✔ Opens default webcam

✔ 0 means internal camera

✔ Reads live frames continuously

### 5️⃣ Converting Image to Grayscale
```
gray = cv2.cvtColor(frame, cv2.COLOR_BGR2GRAY)
```
✔ Improves detection accuracy

✔ Reduces computation cost

### 6️⃣ Detecting Faces
```
faces = face_cascade.detectMultiScale(
    gray,
    scaleFactor=1.3,
    minNeighbors=5
)
```
✔ Detects faces in the frame

✔ Returns (x, y, width, height)

### 7️⃣ Extracting Face Region
```
face_roi = gray[y:y+h, x:x+w]
```
✔ Crops only the face

✔ Removes background noise

### 8️⃣ Expression Analysis Logic
```
emotion = analyze_expression(face_roi)
```
✔ Processes facial features

✔ Predicts emotion label

✔ Can be rule-based or ML-based

### 9️⃣ Displaying Output on Face
```
cv2.rectangle(frame, (x,y), (x+w,y+h), (0,255,0), 2)
cv2.putText(frame, emotion, (x,y-10),
            cv2.FONT_HERSHEY_SIMPLEX, 0.9, (0,255,0), 2)
```
✔ Draws bounding box

✔ Displays detected emotion

### 🔟 Streaming to Browser
```
return Response(generate_frames(),
                mimetype='multipart/x-mixed-replace; boundary=frame')
```
✔ Streams live video

✔ Works like CCTV feed

✔ Updates continuously

### 🌐 index.html (Frontend UI)
```
<img src="{{ url_for('video_feed') }}">
```
✔ Displays live camera feed

✔ Auto updates frames

✔ Simple & lightweight

## 🐧 Linux Installation

### ✅ Step 1: Update System
```
sudo apt update && sudo apt upgrade -y
```

### ✅ Step 2: Install Python & Tools
```
sudo apt install python3 python3-pip git -y
```
### ✅ Step 3: Clone Repository
```
git clone https://github.com/surya404root/Face-Expression-Analyzer.git
cd Face-Expression-Analyzer
```
### ✅ Step 4: Install Dependencies
```
pip3 install opencv-python flask numpy
```
### ✅ Step 5: Run the App
```
python3 app.py
```
### ✅ Step 6: Open Browser
```
http://127.0.0.1:5000
```

## 📱 Termux Installation (Android)

> ⚠️ Camera access depends on device support

### ✅ Step 1: Update Termux
```
pkg update && pkg upgrade -y
```
### ✅ Step 2: Install Required Packages
```
pkg install python git opencv -y
```
### ✅ Step 3: Clone Repository
```
git clone https://github.com/surya404root/Face-Expression-Analyzer.git
cd Face-Expression-Analyzer
```
### ✅ Step 4: Install Python Modules
```
pip install flask numpy
```
### ✅ Step 5: Run Project
```
python app.py
```
### ✅ Step 6: Open Browser
```
http://127.0.0.1:5000
```
### ❗ Note for Termux
• External webcam may be required

• Browser streaming works best

• Some phones block camera access

## 🧪 Detected Expressions
• 😀 Happy

• 😐 Neutral

• 😢 Sad

• 😠 Angry

• 😲 Surprise

## 🛠 Technologies Used
• Python 🐍

• OpenCV 👁️

• Flask 🌐

• HTML / CSS

• Computer Vision

• AI Logic
## 👨🏻‍💻 Author
**Surya (surya404root)**

Security Developer | AI Enthusiast | Open Source Builder

⭐ Star the repo if you like it!
