# Real-Time Object Detection for Autonomous Vehicles  

## 📌 Project Description  
This project focuses on building a deep learning–based real-time object detection system for autonomous vehicles. The aim is to reliably detect and classify key objects on the roads, such as pedestrians, vehicles, and cyclists, to support safe navigation under diverse environmental conditions.  

The model is trained on the **KITTI Object Detection Dataset**. In **Phase 1**, a subset of 100 cleaned images was used to establish the pipeline. In **Phase 2**, the work expanded to the **full KITTI dataset (~12 GB)** to perform a comprehensive Exploratory Data Analysis (EDA) and feature engineering. Deployment will involve a lightweight demo application that can process live video streams and display bounding boxes in real time.  

---

## 🚀 Project Phases  

### **Phase 1: Data Preparation (✅ Completed)**  
- Collected and uploaded a **subset of the KITTI dataset** (100 images + labels).  
- Cleaned the dataset:  
  - Removed images without labels.  
  - Excluded empty label files.  
  - Detected and removed duplicate images.  
  - Filtered out invalid/outlier bounding boxes.  
- Converted annotations from **KITTI format** to **YOLO format**.  
- Split dataset into **80% training** and **20% validation** sets.  
- Generated a `data.yaml` file for YOLO training.  
- Exported a `cleaning_report.json` documenting excluded files.  
- Packaged the final dataset as `kitti_yolo_prepared.zip`.  

---

### **Phase 2: EDA & Feature Engineering (✅ Completed)**  
- Scaled up to the **full KITTI dataset (~12 GB)** for analysis.  
- Conducted **descriptive statistics** on bounding boxes, labels, and image distributions.  
- Visualized dataset patterns:  
  - Class frequency distributions (vehicles, pedestrians, cyclists).  
  - Bounding box size and aspect ratio distributions.  
  - Heatmaps showing object density across image regions.  
- Identified dataset imbalances (e.g., cars being dominant vs. rare classes like pedestrians/cyclists).  
- Applied **feature engineering**:  
  - Encoded class labels in YOLO-compatible format.  
  - Normalized bounding box coordinates relative to image size.  
  - Introduced scaling/augmentation strategies to improve class balance.  
- Prepared the **final cleaned + analyzed dataset** for training, ready for Phase 3.  

---

### **Phase 3: Model Training & Validation (Upcoming)**  

### **Phase 4: Deployment (Upcoming)**  

---
