# Weed Detection using UAV and YOLOv5 + ECA + BottleneckCSP + GhostConv

This project improves YOLOv5s for **Weed Detection in Agricultural Fields** using drone (UAV) images. We enhance the base architecture by integrating custom modules like:

- **Conv_ECA** — Efficient Channel Attention inside convolution
- **BottleneckCSP** — Improved feature extraction
- **GhostConv** — Lightweight computation for faster inference

## Project Structure

````text
WeedDetection-YOLOv5-Custom/
├── models/
│   ├── common.py                # Custom layers (Conv_ECA, BottleneckCSP, GhostConv)
│   └── yolov5s.yaml             # Modified YOLOv5s model architecture
│
├── data/
│   └── agriweed.yaml            # Dataset config (classes, paths)
│
├── runs/
│   └── train/
│       └── yolov5s_eca/         # Training logs (plots, PR/mAP curves, weights)
│
├── detect.py                    # Inference script
└── README.md                    # Project documentation


##  Key Modifications

-  Replaced all standard Conv layers with **Conv_ECA**
-  Added **Efficient Channel Attention (ECA)** for channel-wise feature refinement
-  Integrated **BottleneckCSP** blocks
-  Maintained detection heads and neck structure as in YOLOv5s
-  Trained on the **AgriWeed Dataset** for precision weed classification

---

## Training (example)

```bash
!python train.py \
  --img 640 \
  --batch 2 \
  --epochs 1 \
  --data /content/agriweed.yaml \
  --cfg models/yolov5s.yaml \
  --weights '' \
  --name ghostconv_check




````
