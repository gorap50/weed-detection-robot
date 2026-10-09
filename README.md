# Weed Detection Robot 🌿

Real-time crop vs. weed detection system deployed on Raspberry Pi using **YOLOv4 + OpenCV**. Processes live camera feed and draws bounding boxes with confidence scores — built for smart agriculture edge deployment.

## Demo

![Detection Output](opencv/detection.jpeg)

## How It Works

1. Raspberry Pi camera captures live video frames
2. Each frame is converted to a blob and passed through YOLOv4
3. Non-Maximum Suppression (NMS) filters overlapping detections
4. Bounding boxes + confidence scores drawn on frame in real time
5. Press `q` to quit

## Tech Stack

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![OpenCV](https://img.shields.io/badge/OpenCV-5C3EE8?style=flat&logo=opencv&logoColor=white)
![Raspberry Pi](https://img.shields.io/badge/Raspberry_Pi-A22846?style=flat&logo=raspberry-pi&logoColor=white)

- **YOLOv4** (Darknet) — Object detection model
- **OpenCV DNN** — Model inference + camera capture
- **NumPy / Matplotlib** — Image processing + visualization
- **Raspberry Pi 4** — Edge hardware

## Model Config

| Parameter | Value |
|---|---|
| Input size | 512 × 512 |
| Confidence threshold | 0.5 |
| NMS threshold | 0.5 |
| Classes | `crop`, `weed` |

## Project Structure



weed-detection-robot/
├── opencv/
│ ├── weedDetectionFromCamera.py # Live camera detection (Raspberry Pi)
│ ├── detection_with_opencv.ipynb # Notebook: static image detection
│ └── detection.jpeg # Sample detection output
└── data/ # Not tracked — add locally
├── images/ # Training/test images
├── weights/crop_weed_detection.weights
├── cfg/crop_weed.cfg
└── names/obj.names




## Getting Started

```bash
git clone https://github.com/gorap50/weed-detection-robot.git
cd weed-detection-robot
pip install opencv-python numpy matplotlib
```

Add your trained YOLOv4 weights to `data/weights/`, then:

**Live camera (Raspberry Pi):**
```bash
python opencv/weedDetectionFromCamera.py
```

**Static image detection:**
Open `opencv/detection_with_opencv.ipynb` in Jupyter Notebook.

## Hardware Requirements

- Raspberry Pi 4 (2GB+ RAM)
- Raspberry Pi Camera Module v2
- microSD card (32GB+)
