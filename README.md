# Deep Vision: YOLO Model Exploration for Plastic Shampoo Bottle Defect Detection

Comparison of five YOLO-family object detectors for detecting defects on plastic shampoo bottles from product images.

Project for the *Deep Vision* course, Ostbayerische Technische Hochschule Amberg-Weiden (Summer 2026). Supervised by Prof. Dr. Tatyana Ivanovska.

## Problem

Automatic detection and classification of product defects helps industrial quality control. This project trains and compares detectors on one task so that accuracy, model size and computational cost can be judged side by side.

## Models compared

- YOLOv8n
- YOLOv9-C
- YOLOv10n
- YOLO11n
- YOLOX-Nano

## Dataset

The dataset has **10 defect classes**: adhesion, dent, pob, scuff and tear, each in a `marg` and an `unacc` variant. Every model is trained, validated and tested on the same split. The dataset is not included in this repository.

## Metrics

Precision, recall, F1 score and mAP50. The report also compares layers, parameter counts, GFLOPs, optimizers, activation functions and fine-tuning settings.

## Summary of findings

From the report's abstract:

- **YOLO11n** gave the best F1 score and mAP50.
- **YOLOv8n** offered a good balance of accuracy and training time.
- **YOLOv9-C** was accurate but needed the most computation.
- **YOLOv10n** was very fast with reasonably good accuracy.
- **YOLOX-Nano** had the fewest parameters but the weakest detection accuracy of the five.

See [`report.pdf`](report.pdf) for the full methodology, training curves and results tables.

## Repository structure

```
.
├── report.pdf                         # Full project report (24 pages)
└── source_code/
    ├── YOLOv8n.ipynb                  # Training and evaluation notebook for YOLOv8n
    ├── YOLOv9-c.ipynb                 # ... for YOLOv9-C
    ├── YOLOv10n.ipynb                 # ... for YOLOv10n
    ├── YOLOv11n.ipynb                 # ... for YOLO11n
    ├── YOLOX-n.ipynb                  # ... for YOLOX-Nano
    ├── YOLO_MODELS_COMPARISON.ipynb   # Side-by-side comparison of the results
    ├── train_dual.py                  # Training script for the YOLOv9 dual-assignment setup
    └── loss_tal.py                    # Task-aligned assignment loss
```

## Running the notebooks

Each notebook is self-contained and is meant to be run in Jupyter. Install the Ultralytics package for the YOLOv8/10/11 notebooks, and clone the YOLOX and YOLOv9 code bases for the other two. Point the dataset path variables in each notebook at your own copy of the dataset.

## Authors

- Dhruvin Gopani
- Khushalkumar Variya

Ostbayerische Technische Hochschule Amberg-Weiden, Department of Electrical Engineering, Media and Computer Science.
