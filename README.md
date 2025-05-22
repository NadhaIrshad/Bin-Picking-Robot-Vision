# 🦾 Bin Picking Robot Vision System

This project focuses on developing a computer vision pipeline for a bin picking robot to detect and differentiate between **non-linear objects**—such as *L-bend pipes*—that are randomly spread in a container. The objective is to accurately localize and separate individual objects for robotic manipulation.

## 🧠 Task Description

In robotic bin picking, especially with non-linear and overlapping objects like pipes, accurate perception is critical. The system must:

- Detect and distinguish **individual instances** of objects.
- Handle **random orientations and overlaps**.
- Be efficient enough to run on **edge hardware** (e.g., Jetson Nano).

## 🔍 Techniques Explored

### 📌 Semantic Segmentation

Semantic segmentation labels each pixel by category but does **not distinguish between instances**. Tested model:

- **DeepLabV3** – Provided good object contour mapping but couldn't differentiate overlapping objects, making it less ideal for robotic picking tasks.

### 📌 Instance Segmentation

Instance segmentation is more suitable, as it separates each object individually. Tested models:

- **Mask R-CNN** – High accuracy but slower inference.
- **YOLO with segmentation** – Faster inference, good for real-time applications.

### ⚙️ Traditional Methods

Also explored classical computer vision approaches:

- **Adaptive Thresholding + Contour Analysis** – Useful for basic shapes; lacks robustness for overlapping or complex geometries.
- **Gabor Filter + MLP Classifier** – Used texture-based segmentation, but not suitable for precise object isolation.

### 📊 Performance Testing

- Tested **FPS** and **inference time** on several deep learning models.
- Benchmarks guided the selection of a model suitable for real-time operation on edge devices.

## ✅ Conclusion

For the **bin picking of non-linear, overlapping objects**, **instance segmentation** was the preferred approach. It provided clear differentiation between individual objects, which is essential for robotic grasping tasks.

## 🚀 Deployment

- The final model was deployed on an **NVIDIA Jetson Nano**.
- A custom interface was built to visualize detections and integrate with the robotic control system.

## 📂 Folder Structure (Optional)

```bash
├── data/                 # Sample images and annotations
├── models/               # Pretrained weights and configs
├── scripts/              # Training, inference, and evaluation scripts
├── interface/            # Code for Jetson Nano interface
└── README.md             # Project description
