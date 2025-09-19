# Real-Time Object Detection for Autonomous Vehicles  

## 📌 Project Description  
This project focuses on building a deep learning–based real-time object detection system for autonomous vehicles. The aim is to reliably detect and classify key objects on the roads, such as pedestrians, vehicles, and cyclists, to support safe navigation under diverse environmental conditions.  

The model will be trained on the **KITTI Object Detection Dataset**; however, for now, it has been processed with only a subset of 100 images, which have been cleaned and reformatted for YOLO-based training. Deployment will involve a lightweight demo application that can process live video streams and display bounding boxes in real time.

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

### **Phase 2: EDA & Feature Engineering (Upcoming)**  

### **Phase 3: Model Training & Validation (Upcoming)**  

### **Phase 4: Deployment (Upcoming)**  

---
