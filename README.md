# 🦺 Helmet Safety Detection with YOLOv10

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.8+](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/downloads/)

AI-powered construction site safety compliance system detecting workers without safety helmets using state-of-the-art YOLOv10 object detection.

## 🚀 Features

- Real-time detection of **person**, **helmet**, and **head** objects
- Multi-input support: images, videos, webcam streams, YouTube URLs
- Pre-trained COCO models & custom training capabilities
- Bounding box annotations with confidence scores
- Achieves **0.89 mAP@50** on test data

## 🧠 Custom Training

1. **Prepare Dataset:**
```python
gdown 1twdtZEfcw4ghSZIiPDypJurZnNXzMO7R
unzip Safety_Helmet_Dataset.zip -d datasets/
```

2. **Configure `data.yaml`:**
```python
train: ../datasets/train/images
val: ../datasets/valid/images
test: ../datasets/test/images

names:
  0: person
  1: helmet
  2: head
```

3. **Start Training:**
```python
model.train(
    data='data.yaml',
    epochs=50,
    imgsz=640,
    batch=32,
    optimizer='AdamW'
)
```

## 📊 Performance Metrics

| Metric                | Value   |
|-----------------------|---------|
| mAP@50                | 0.89    |
| Precision             | 0.92    |
| Recall                | 0.85    |
| Inference Speed (RTX 3090) | 45 FPS |

## 📜 License

Distributed under MIT License. See `LICENSE` for details.

## 🙏 Acknowledgements
- YOLOv10 team at THU-MIG
- [Safety Helmet Dataset](https://www.kaggle.com/datasets/andrewmvd/hard-hat-detection)
- LabelImg annotation tool
- AI Vietnam instructors
