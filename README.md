# 🏗 GSO-YOLO: Global Stability Optimization YOLO for Construction Site Detection

This repository contains an implementation of the paper:  
**_GSO-YOLO: Global Stability Optimization YOLO for Construction Site Detection_**  
[arXiv:2407.00906](https://arxiv.org/abs/2407.00906)

GSO-YOLO extends YOLOv8 to better handle complex and dynamic environments on construction sites by integrating:

-  **GOM** (Global Optimization Module) — based on Global Attention Mechanism (GAM)
-  **SCM** (Steady Capture Module) — introduces temporal smoothing via EMA
-  **AIoU Loss** — combines CIoU and EIoU for enhanced localization precision

---

## 📊 Ablation Study Variants

We implemented all key variants described in the paper for ablation experiments:

| Variant            | Modules Used             |
|--------------------|--------------------------|
| `YOLOv8`           | Baseline model           |
| `YOLOv8 + SCM`     | With steady capture only |
| `YOLOv8 + GOM`     | With global attention only |
| `YOLOv8 + SCM + GOM` | Both modules combined     |
| `GSO-YOLO`         | Final model with AIoU    |

Each version is available and tested. You can train any of them by selecting the appropriate `.yaml` config.

---

## 🚀 How to Train

```bash
yolo task=detect mode=train model=yolov8-gso-variant.yaml data=your_dataset.yaml epochs=50 imgsz=640
