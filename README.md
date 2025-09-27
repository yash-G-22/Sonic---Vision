# SONIC-VISION : Real-Time Object Detection with Gesture-Based Selection for Visually Impaired Users  

## 📌 Overview  
This project is designed to assist **visually impaired users** by combining **hand gesture recognition** and **real-time object detection** with **audio feedback**.  
- Users point at objects using their **index finger**.  
- The system detects and confirms the object being pointed at.  
- The object’s name is then **spoken aloud** using a text-to-speech engine.  

This allows visually impaired individuals to **interact with their surroundings independently**.  

---

## 🛠 Features  
- 🎥 **Live Video Capture** – Captures frames continuously from the camera.  
- ✋ **Hand Tracking** – Uses **MediaPipe Hands** to track the index finger position.  
- 🧠 **Object Detection** – YOLOv8 model for real-time object detection.  
- 🎯 **Object Selection Logic** – Ensures detection only if the fingertip points to an object.  
- ⏳ **Stability Check** – Confirms an object if pointed at consistently for ~2 seconds.  
- 🔊 **Audio Feedback** – Announces the object’s name via **Text-to-Speech**.  
- ⚡ **Optimizations** – Multithreading, smoothing filters, Non-Maximum Suppression (NMS).  

---

## 🏗 System Architecture  

**Workflow**:  
1. Capture live video input.  
2. Track hand & detect fingertip.  
3. Run YOLOv8 for object detection.  
4. Match fingertip with detected objects.  
5. Confirm if stable for 2 seconds.  
6. Announce object name via TTS.  
7. Repeat continuously.  

**High-Level Architecture:**  

```
Camera Input 
      ↓ 
Hand Tracking (MediaPipe) 
      ↓ 
Object Detection (YOLOv8) 
      ↓ 
Object Filtering & Selection 
      ↓ 
Audio Feedback (TTS)
```

---

## 📂 Modules  
- **handtracking.py** → Tracks index finger, applies smoothing.  
- **object_detection.py** → Detects objects using YOLOv8 & filters.  
- **integration.py** → Maps fingertip to bounding boxes, ensures stability.  
- **audio_feedback.py** → Provides TTS output using `pyttsx3`.  
- **main.py** → Integrates all modules, runs video loop with OpenCV.  

---

## 🧰 Technologies Used  
- **Machine Learning Models**:  
  - YOLOv8 (Ultralytics) – Object Detection  
  - MediaPipe Hands – Hand & Finger Tracking  
- **Libraries & Tools**:  
  - OpenCV – Video Processing  
  - NumPy – Image Computation  
  - pyttsx3 – Text-to-Speech  
  - Threading – Asynchronous Processing  

---

## 📦 Installation  

1. Clone the repository:  
   ```bash
   git clone https://github.com/your-username/gesture-object-detection.git
   cd gesture-object-detection
   ```

2. Install dependencies:  
   ```bash
   pip install -r requirements.txt
   ```

3. Run the main program:  
   ```bash
   python main.py
   ```

---

## 📑 Requirements  
`requirements.txt` should include:  
```
ultralytics
mediapipe
opencv-python
numpy
pyttsx3
```

---

## 🎬 Demo  
- **Image to Text Demo** – [Demo Video 1](./Image%20to%20Text.mp4)  
- **Full Workflow Recording** – [Demo Video 2](./Recording%202025-04-18%20154013.mp4)  

---

## 🚀 Future Improvements  
- Add support for multiple gestures (zoom, select, skip).  
- Improve TTS with multilingual support.  
- Deploy as a **mobile app** for accessibility.  

---

## 👩‍💻 Contributors  
- Developed as part of an academic project on **assistive technologies for accessibility**.  
