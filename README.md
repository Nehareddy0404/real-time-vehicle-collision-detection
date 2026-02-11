# 🚗 Real Time Vehicle Collision Detection System

## 🎯 Project Aim

The goal of this project is to develop a real-time vehicle collision detection system that processes dashcam footage and alerts the driver when there is a risk of collision.

The system is designed to:

- Capture real-time vehicle footage
- Detect vehicles and obstacles using object detection models
- Trigger an alert when an object approaches within a defined risk zone

---

## 🧠 Object Detection Models Used

This project compares three YOLO-based detection models:

1. **Pre-trained YOLO (Scaled In-Built Weights)**
2. **Custom-trained YOLO model** (trained on ~600 vehicle images)
3. **Tiny YOLO model** (optimized for speed)

### About YOLO

YOLO (You Only Look Once) is a real-time object detection algorithm designed for high-speed inference. It works by dividing an image into a grid and predicting bounding boxes and class probabilities for each cell.

YOLO is optimized for:
- Real-time video processing
- High frame-per-second performance
- Efficient object localization

---

## 📊 Model Evaluation

The models were evaluated using **1000 test vehicle images**  
(Some images contained multiple vehicles.)

### Observed Results:

- **Pre-trained YOLO**
  - Detected: 1256 vehicles
  - Higher recall
  - More false positives

- **Custom-trained YOLO (600 images)**
  - Detected: 1004 vehicles
  - Balanced detection
  - Fewer false positives compared to pre-trained

- **Tiny YOLO**
  - Detected: 401 vehicles
  - Faster inference
  - Lower detection accuracy

---

## 📈 Performance Comparison

### Vehicle Detection Results

![Model Comparison Chart](https://user-images.githubusercontent.com/72432304/121334585-d5efbd00-c92a-11eb-8bbf-890187214a88.png)

---

## 🔍 Result Analysis

Using the scaled pre-trained YOLO model:

- Vehicles are detected in real time.
- If an object approaches rapidly within the defined Region of Interest (front view), the system triggers an alert.
- The system demonstrates sufficient speed and accuracy for real-time collision risk monitoring.

### Accuracy Insights

- The pre-trained YOLO model achieved the highest detection count but produced more false positives.
- The custom-trained model showed fewer false positives but slightly lower detection performance.
- Tiny YOLO significantly reduced detection count, prioritizing speed over accuracy.

The lower accuracy of the manually trained model may be due to limited dataset size (~600 images) and varying video clarity.

---

## ⚙️ Tech Stack

- Python
- YOLO (Object Detection)
- OpenCV
- NumPy

---

## 🚀 How to Run

```bash
git clone https://github.com/Nehareddy0404/real-time-vehicle-collision-detection.git
cd real-time-vehicle-collision-detection
pip install -r requirements.txt
python VCD2.py
```

-----

🔮 Future Improvements
Improve custom model dataset size for higher accuracy
Implement object tracking across frames
Add collision probability scoring
Deploy as an embedded real-time device system
