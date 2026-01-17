---

# **Social Distancing Monitoring System**


A **real‑time social distancing monitoring system** built using **YOLOv3** and **OpenCV**, designed to detect people in video streams and estimate the distances between them to monitor compliance with social distancing protocols — especially relevant during public health crises such as the COVID‑19 pandemic. ([GitHub][1])

## 🧠 Overview

This project implements:

✔ Real‑time object detection using **YOLOv3**, pre‑trained on the COCO dataset to accurately detect people in video frames. ([GitHub][1])
✔ Distance estimation between detected individuals to assess if the socially recommended spacing is being maintained.
✔ Alerts triggered when individuals are closer than the defined safety threshold, helping enforce social distancing.
✔ Support for live camera feeds or recorded video inputs for flexible deployment.

---

## 📦 Features

### 📍 Detection

* Leverages **YOLOv3**, a state‑of‑the‑art single‑stage object detector for fast inference and accurate human detection. ([GitHub][1])
* Uses bounding boxes to localize each person in the frame.

### 📏 Distance Measurement

* Computes the **Euclidean distance** between centroids of detected individuals.
* Applies threshold logic to classify interactions as safe or potential violations.

### 🔔 Alerts

* Flags and visualizes violations where people are too close.
* Can be adapted to trigger external notifications or logs.

### 📹 Video Support

* Supports real‑time webcam or IP‑camera streams.
* Also accepts existing video files for analysis.

---

## 🧰 Repository Structure

```
Social-Distancing-Monitoring-/
├── config.py              # Parameters and distance thresholds
├── detection.py           # Main detection and processing logic
├── thread.py              # Optional multithreading utilities
├── mailer.py              # (Optional) alerting/mail utility
├── videos/                # Sample video files for testing
├── requirements.txt       # Python dependencies
└── README.md              # Project documentation
```

---

## 🚀 Getting Started

### 🔧 Prerequisites

Install the required Python packages:

```bash
pip install -r requirements.txt
```

Make sure you have the YOLOv3 model files (**yolov3.weights** and **yolov3.cfg**), which can be downloaded from the original repository:

* YOLO v3: [https://pjreddie.com/media/files/yolov3.weights](https://pjreddie.com/media/files/yolov3.weights)
* YOLO config: [https://github.com/pjreddie/darknet/blob/master/cfg/yolov3.cfg](https://github.com/pjreddie/darknet/blob/master/cfg/yolov3.cfg)

---

### ▶️ Running the System

#### Run on a test video

```bash
python detection.py --input videos/test.mp4
```

#### Run with a webcam

```bash
python detection.py --input 0
```

(Here `0` is the default webcam — replace with an IP camera URL for live streams.)

---

## 📊 How It Works

1. **Detection:**
   Each frame is passed through the YOLOv3 model to identify people with bounding boxes. ([GitHub][1])

2. **Distance Computation:**
   The system computes the centroids of detected boxes and then calculates pairwise distances.

3. **Violation Analysis:**
   If the distance between two people falls below a safety threshold, the system flags a violation and highlights it visually.

---

## 🧪 Example Outputs

Processed frames show:

✔ Green boxes for safe distances
✔ Red boxes for violations
✔ Optional display of count and alert messages

(*Include sample screenshots or video clips here for better visualization.*)

---

## 📈 Applications

This system can be adapted for:

* Surveillance in **public spaces**, workplaces, and retail stores
* Monitoring **queue areas** or entrances
* Real‑time alerting in smart city systems
* Research and prototyping for crowd analytics

---

## 🤝 Contributions

Contributions, issues, and feature requests are welcome!
Feel free to fork this repo and submit pull requests.

# Author: Shailaj Gautam

---

