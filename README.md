HEROCS – An on‐device mobile computer vision assessment System for Hazard Detection in Household Environments

A Thesis Research Project

# HEROCS Technical & Developer Manual

## Overview
HEROCS (HomeHazard Evaluation and Risk Object Classification System) is an on-device mobile computer vision system for household hazard detection, specifically designed for Filipino home environments. The system integrates Flutter (with ARCore), a YOLOv8-based object detection model deployed with TensorFlow Lite, robust multi-label risk classification, and an annotated culturally contextual dataset hosted on Hugging Face.

This manual provides:
- Project and codebase structure
- Dataset and annotation protocols
- Model training & deployment guidelines
- App architecture and main components
- Technical references for extension & maintenance

---

## Repository and Codebase Structure
The HEROCS project is organized following best software engineering and open-source practices. The [GitHub repository](https://github.com/riggsybanez/Projects) contains:
- `lib/` – All Dart source files
   - `main.dart`: Flutter app entry point, initializes provider and theme
   - `home_screen.dart`: Main menu and navigation
   - `camera_scan_screen.dart`, `ar_camera_screen.dart`: Real-time AR scanning UI and logic
   - `image_detection_screen.dart`: Static image scan and reporting
   - `object_detection_service.dart`: Loads and manages the YOLOv8 TFLite model; inference logic
   - Models: `hazard_object.dart`, `risk_classification.dart`, `household_danger_index.dart`
   - `bounding_box_painter.dart`: Custom render of bounding boxes
- `assets/` – Models and label files
   - `models/`: `yolov8sherocs.tflite`, label map txt
- `pubspec.yaml`: Dependencies and assets

## Dataset Reference
- [HEROCS Hugging Face Dataset](https://huggingface.co/datasets/riggsybanez/HEROCS_Dataset/tree/main)
  - Over 1,500 original images, expanded to 5,373 after constrained augmentation
  - 24 annotated hazard classes (chokingobject, sharpobject, toxicchemical, etc.)
  - YOLO-format bounding box CSVs and multi-label tags per object
  - Prioritized for cultural/contextual accuracy (Philippine households)
  - Curation and augmentation strategies documented in manuscript

## Model Training & Augmentation
- **Model:** YOLOv8s (11.2M parameters), trained in Ultralytics pipeline, exported as TFLite
- **Hardware:** Uses Google Colab Pro (T4, A100 GPUs)
- **Training:**
  - 
    - 5,373 images, 24 classes
    - Constrained augmentation (Albumentations, limit 3x per image, dynamic early stopping)
    - Class balancing with target instance thresholds (300-600/class)
  - Loss functions: CIoU/regression loss, binary cross-entropy for classification
  - Class weights for minority categories
- **Deployment:**
  - Export trained model as TFLite: `yolov8 export tflite`
  - Place in `assets/models/` and reference in `pubspec.yaml`
- **Label Alignment:** Class list in model config, label order must match `labels.txt`

## App Architecture & Key Components

**Flutter Entry Point**
- `main.dart` initializes `ObjectDetectionService` via Provider, enforces portrait orientation
  - Theme customization for accessibility and branding
- `home_screen.dart` provides mode selection (AR camera, Image Scan)
- `camera_scan_screen.dart` and `ar_camera_screen.dart` handle real-time detection, periodic inference every 1s, overlays, and HDI score UI
- `image_detection_screen.dart` allows gallery/camera import, invokes detection, overlays bounding boxes, provides recommendations and HDI report

**Object Detection Service**
- Loads YOLOv8 TFLite model on start
- Runs inference on each frame/image
- Multi-label outputs for each bounding box; uses risk classification
- Performs temporal smoothing (3-frame window) in AR modes
- Outputs risk score, bounding box, and category–consumed by the UI

**HDI Calculation**
- Implemented in `household_danger_index.dart` and `risk_classification.dart`
- Each detected object assigned category (choking, toxic, sharp, etc.), positional (within reach, floor, elevated), and contextual labels
- Scoring per object, aggregate as environment HDI (mean averaging); 0.1-0.5 range with safety tiers

**Augmented Reality (AR)**
- Integrates ARCore via `arcore_flutter_plugin` package
- Real-world alignment of bounding boxes with detected objects

**Dependencies**
- Major: `flutter`, `camera`, `arcore_flutter_plugin`, `tflite_flutter`, `provider`, `image`, `sensors_plus`, `permission_handler`, etc.
- Reference `pubspec.yaml` for full version specs

## Dataset and Annotation Guidelines
- Each image is annotated via Roboflow/LabelImg for:
  - Bounding box (YOLO format)
  - Label(s): category, positional, contextual
  - Minimum 300-600 instances per class post-augmentation; classes below this threshold are flagged
  - Multi-label co-occurrence rules: single object may have multiple hazardous attributes; e.g., sharp + withinreach
- Data augmentation: Albumentations, horizontal/rotation/brightness/noise, label-aware transforms
- Dataset splits: follow 80/10/10 for train/val/test

## Extension and Maintenance
- For retraining: expand dataset, repeat augmentation strategy, match label list
- For new labels/classes: update label map, dataset, and retrain model
- To update AR experience: edit AR widget logic in Dart; align anchor points and update custom painters
- For performance tuning: profile with Flutter DevTools, model quantization/pruning for speed

## References and Technical Links
- GitHub: https://github.com/riggsybanez/Projects
- Hugging Face dataset: https://huggingface.co/datasets/riggsybanez/HEROCS_Dataset/tree/main
- Roboflow: https://roboflow.com/
- YOLOv8 Docs: https://docs.ultralytics.com/
- Flutter: https://flutter.dev/

---

For bug reports or contributions, submit GitHub issues or follow pull request guidelines. See README for up-to-date build/run instructions and CI details.
