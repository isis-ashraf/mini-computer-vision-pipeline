# Mini Computer Vision Pipeline - README

## Overview
This project implements a computer vision pipeline using the Fruits-360 dataset for:
- **Task 1**: Image classification with ResNet50 (transfer learning).
- **Task 2**: Object detection with YOLO (image selection done, annotation/training pending).

## Dataset
- [Fruits-360 Dataset](https://www.kaggle.com/datasets/moltean/fruits) from Kaggle, downloaded via `kagglehub`.

## Requirements
- Python 3.8+
- Libraries: `tensorflow`, `kagglehub`, `scikit-learn`, `numpy`, `matplotlib`, `glob`, `shutil`, `random`
- Install: `pip install -r requirements.txt`
- Task 2 (YOLO): Needs `ultralytics` (add later) and [LabelImg](https://github.com/HumanSignal/labelImg) for annotations.
- Hardware: GPU recommended, CPU sufficient for small datasets.

## Project Structure
```
├── classification/
│   ├── ResNet_classification_model.keras  # Trained model
│   └── classification_code.py             # Task 1 code
├── object_detection/
│   ├── images/
│   │   ├── train/                        # Train images
│   │   └── val/                          # Validation images
│   ├── labels/
│   │   ├── train/                        # Train annotations (pending)
│   │   └── val/                          # Validation annotations (pending)
│   └── object_detection_code.py          # Task 2 code
|__ README.md                             # This file
```

## How to Run
1. **Setup**:
   - Configure Kaggle API for `kagglehub`.
   - Clone repo or unzip; install dependencies.

2. **Task 1: Classification**:
   - Run: `python classification/classification_code.py`
   - Actions: Downloads dataset, trains ResNet50 (5 epochs), evaluates accuracy, plots confusion matrix, saves model.

3. **Task 2: Object Detection**:
   - Run: `python object_detection/object_detection_code.py`
   - Actions: Copies 30 images (6 classes) to `object_detection/images/`.
   - Next: Annotate with LabelImg, train YOLO (e.g., YOLOv8), evaluate detections.

## Notes
- **Dataset**: 270 classes; Task 2 uses 6 classes (30 images).
- **Outputs**: Model file, accuracy logs, confusion matrix (Task 1); images (Task 2).
