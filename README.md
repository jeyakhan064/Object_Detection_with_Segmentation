# 🎯 Object Segmentation Project (YOLO11-Seg)

This repository contains a complete workflow for training, validating, and running inference using **Ultralytics YOLO11-Seg** for object detection and segmentation.  
The project includes image segmentation, video processing, and evaluation of custom-trained models.

---

## 🚀 Features

- ✔️ Custom training using **YOLO11n-seg**
- ✔️ High-accuracy segmentation on 5 classes  
  (`bag`, `charger`, `keyboard`, `laptop`, `screen`)
- ✔️ Image inference support  
- ✔️ Video inference support  
- ✔️ Automatic saving of annotated outputs  
- ✔️ Model evaluation with mAP scores  
- ✔️ Clean, structured workflow for reproducibility  

---

## 📁 Project Structure

project/
│── train/ # Training dataset
│── valid/ # Validation dataset
│── runs/segment/Project/ # Training results + weights
│ ├── best.pt # Best model – used for inference
│ └── last.pt # Last epoch model
│── infer.py # Image & video inference scripts
│── README.md # Documentation

yaml
Copy code

---

## 🔧 Installation

Install Ultralytics:

```bash
pip install ultralytics
🧠 Training Details
Model: YOLO11n-seg

Epochs: 270

EarlyStopping Best Epoch: 170

Classes: 5

Validation Instances: 19

📊 Final Model Performance (best.pt)
Metric	Value
mAP50 (Boxes)	0.985
mAP50-95 (Boxes)	0.956
mAP50 (Masks)	0.985
mAP50-95 (Masks)	0.921

All classes performed with high precision and recall, showing strong generalization.

🖼️ Image Inference
python
Copy code
model = YOLO("runs/segment/Project/weights/best.pt")
results = model("image.jpg")
Outputs are automatically saved.

🎥 Video Inference
bash
Copy code
yolo predict model="runs/segment/Project/weights/best.pt" \
     source="your_video.mp4" save=True
Annotated video is saved inside:
runs/predict/

📦 Included Utility Scripts
infer_image() → Image inference

infer_video() → Video inference

Automatic mask + bounding box overlays

Saves output as .jpg or .mp4

📝 Notes
The repository is built for clean and reproducible execution.

Outputs can be deleted anytime; you can rerun the workflow from scratch.

Ideal for demos, academic projects, or lightweight segmentation pipelines.

🧑‍💻 Author
Javeria Younus
Custom YOLO11 segmentation pipeline • Model training • End-to-end workflow

⭐ Support
If you use this project, please ⭐ star the repo!

