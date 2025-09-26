# Real-Time Object Detection for Autonomous Vehicles

📌 **Project Description**  
This project builds a deep learning–based **real-time object detection** system for autonomous vehicles. It detects and classifies key road objects—**Cars, Pedestrians, Cyclists**—to support safe navigation across diverse conditions.

The model is trained on the **KITTI Object Detection** dataset. In **Phase 1**, a 100-image cleaned subset established the pipeline. In **Phase 2**, we scaled to the full KITTI dataset (~12 GB) for comprehensive EDA and feature engineering. In **Phase 3**, we trained and validated multiple YOLO models with class balancing and augmentation. In **Phase 4**, we deployed the best model to a **Flutter Android app** that performs continuous on-device inference.

---

## 🚀 Project Phases

### Phase 1: Data Preparation (✅ Completed)
- Collected and uploaded a **100-image** KITTI subset (images + labels).  
- Cleaned the dataset:  
  - Removed images without labels.  
  - Excluded empty label files.  
  - Detected and removed duplicate images.  
  - Filtered invalid/outlier bounding boxes.  
- Converted annotations from **KITTI → YOLO** format.  
- Split into **80% train / 20% val**.  
- Generated `data.yaml` for YOLO training.  
- Exported a `cleaning_report.json` of excluded files.  
- Packaged the final subset as `kitti_yolo_prepared.zip`.

---

### Phase 2: EDA & Feature Engineering (✅ Completed)
- Scaled analysis to the **full KITTI (~12 GB)**.  
- Descriptive statistics on boxes, labels, image distributions.  
- Visualized patterns:  
  - Class frequencies (cars dominant; pedestrians/cyclists rarer).  
  - Bounding-box sizes and aspect ratios.  
  - Object-center heatmaps and objects-per-image.  
- Addressed imbalance and quality:  
  - Encoded labels for YOLO.  
  - Normalized boxes relative to image dimensions.  
  - Applied scaling/augmentation strategies to improve balance.

---

### Phase 3: Model Training & Validation (✅ Completed)
- Configured **YOLOv8** training on the prepared dataset.  
- Trained multiple variants (e.g., **YOLOv8n**, **YOLOv8s**) for comparison.  
- Augmentations: **mosaic, mixup, flips, HSV jitter, scaling**.  
- Imbalance handling:  
  - **Oversampled** minority classes (pedestrians, cyclists).  
  - (Optionally) **weighted loss**.  
- Tracked metrics: **mAP, precision, recall, F1**.  
- Visualized results:  
  - **Confusion matrices**, PR/RC/F1 curves.  
  - Example predictions with bounding boxes on KITTI images.  
- Exported trained models and logs:  
  - `best.pt`, `best.onnx`, `best_float32.tflite`, `best_float16.tflite`, `best_int8.tflite`, `best.torchscript`, `saved_model/`, `ncnn/`.  
- Selected the **best configuration** for deployment (FP16 TFLite recommended on Android).

---

### Phase 4: Mobile Deployment (✅ Completed)
- Built a **Flutter Android** app with:  
  - **Live camera preview (CameraX)** and **continuous inference** (process every *N*-th frame for smooth UI).  
  - **YOLO letterbox** pre-processing and reverse mapping to preview coordinates.  
  - **On-device NMS** and overlay rendering (boxes, labels, confidences).  
- Android config highlights:  
  - `compileSdk=36`, `minSdk=26`.  
  - Keep `.tflite` **uncompressed** for fast mmap loads.  
  - Optional **TFLite GPU** dependency + keep rules when using GPU delegate.  
- Produced **debug** and **release** APKs.
