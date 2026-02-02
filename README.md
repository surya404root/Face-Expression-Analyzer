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
