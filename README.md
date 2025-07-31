# Real-Time-Attendance-System-Using-ESP-32

##  Overview

This project implements a **contactless real-time attendance system** using the **ESP32-CAM** module. It captures facial images, matches them with a **preloaded dataset**, and stores the attendance record (name and timestamp) in **Firebase Realtime Database**. This system offers an efficient, accurate, and touch-free alternative to manual or RFID-based attendance methods.

---

##  Features

-  Face Detection & Recognition using OpenCV
-  Real-time image capture using ESP32-CAM
-  Cloud-based attendance logging with Firebase
-  Preloaded dataset with labeled student images
-  Excel export and timestamped records
-  Lightweight, low-cost, and scalable

---

## Tech Stack

### 🔌 Hardware:
- [ESP32-CAM](https://randomnerdtutorials.com/esp32-cam-video-streaming-face-recognition/)
- FTDI Programmer (USB to TTL Converter)
- Wi-Fi Router

###  Software & Libraries:
#### Arduino (ESP32):
- `WiFi.h`
- `Firebase_ESP_Client.h`
- `esp_camera.h`
- `ArduinoJson.h`

#### Python (for face recognition):
- `face_recognition`
- `opencv-python`
- `numpy`
- `firebase-admin` *(optional if using Python for DB)*
- `datetime`, `os`


##  How It Works

1. **Dataset Preparation**:
   - Add clear face images (passport-size) of all users to the `dataset/` folder.
   - Name each image file using the person’s name (e.g., `Viraj.jpg`).

2. **Hardware Setup**:
   - Connect ESP32-CAM to your PC using the FTDI programmer.
   - Flash the Arduino sketch using Arduino IDE.
   - Connect to Wi-Fi and set up Firebase credentials.

3. **Face Recognition**:
   - ESP32-CAM captures the face in real-time.
   - Python script processes the image, compares it with the dataset using `face_recognition`, and identifies the person.
   - Upon match, attendance is logged in Firebase and/or Excel.

4. **Attendance Storage**:
   - The recognized name and timestamp are stored in:
     - Firebase Realtime Database (Cloud)
     - Excel file (Local log)

---

## Firebase Setup

1. Go to [Firebase Console](https://console.firebase.google.com/)
2. Create a new project.
3. Add Realtime Database and get your config credentials.
4. Replace them in your `firebase_config.json` or inside Arduino code.

---

##  Future Improvements

- Add web/mobile dashboard to manage attendance
- Enable live face registration from ESP32
- Use Raspberry Pi for on-device recognition
- Implement facial liveness detection (to avoid spoofing)



