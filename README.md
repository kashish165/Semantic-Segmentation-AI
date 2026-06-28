# Semantic Segmentation AI 

A high-performance real-time **semantic segmentation + object detection system** built using **DeepLabV3 + YOLOv8 + OpenCV + PyTorch**.

This project transforms raw video footage into structured pixel-level understanding of a scene, combining scene segmentation, object segmentation, and real-time visual rendering.

---
## dev/creator=tubakhxn

## What it does

- Performs real-time semantic segmentation using DeepLabV3-MobileNetV3
- Adds object-level segmentation using YOLOv8 segmentation model
- Uses fast heuristic scene detection for additional context layering
- Generates fully processed output video with overlays
- Applies cinematic post-processing (vignette + edge enhancement)
- Displays live FPS, inference latency, and system performance
- Supports video files and webcam input
- Saves annotated output video automatically
- Screenshot capture during runtime

---

## Core Features

- Hybrid segmentation pipeline (DeepLab + YOLO + heuristic rules)
- Async inference worker (non-blocking real-time processing)
- Lightweight DeepLabV3-MobileNetV3 backbone (optimized for speed)
- YOLOv8n-seg for instance segmentation
- Vectorized color LUT rendering for fast frame composition
- GPU acceleration with FP16 support (CUDA)
- Optimized inference resolution (320px DeepLab / 416px YOLO)
- Real-time HUD with FPS, latency, frame counter, and class tracking

---

## Architecture

The system uses a 3-layer vision pipeline:

1. Scene segmentation (fast heuristic + DeepLabV3)
2. Object segmentation (YOLOv8 instance masks)
3. Rendering engine (color blending + edge detection + HUD)

Each frame is processed asynchronously to avoid blocking the main video loop.

---

## Technologies Used

- PyTorch  
- TorchVision (DeepLabV3-MobileNetV3)  
- Ultralytics YOLOv8  
- OpenCV  
- NumPy  
- PIL (image preprocessing)

---

## Performance Optimizations

- DeepLabV3-MobileNetV3 (lightweight backbone)
- FP16 inference on GPU
- Reduced inference resolution (320px / 416px)
- Async inference thread (decoupled processing)
- Vectorized mask rendering using LUTs
- Precomputed vignette effect
- Frame skipping strategy for heavy models

---

## Installation

No manual setup required. The script auto-installs dependencies.

```bash
python semantic_segmentation_ai_fast.py video.mp4
```

---

## Pothole Detection

- Also supports detection and segmentation of potholes in road scenes (requires a YOLOv8 segmentation model trained for potholes)
- Highlights potholes along with other road features for improved road safety analysis
- To enable pothole detection, use a YOLOv8 model trained on pothole datasets (replace `yolov8n-seg.pt` with your custom model)
