
# Food Plate Wastage Classification using YOLOv11n + Attention Mechanisms

This project proposes a deep learning-based solution to tackle the problem of food wastage in IIT Kanpur mess halls. Using cutting-edge computer vision methods, the system classifies food plate images into three categories of wastage: **Low**, **Medium**, and **High**.

## 📌 Motivation

Over 11,000 kg of food is wasted daily at IIT Kanpur. Manual or weight-sensor-based tracking of food waste is inefficient and impractical at scale. To address this, we developed a lightweight, camera-based deep learning model to estimate food waste through plate image classification.

## 🔍 Problem Statement

Traditional weight-sensor methods require weighing plates before and after meals, creating logistical bottlenecks. Our method bypasses this by using **image-based classification** powered by deep CNNs, with no hardware overhead.

## 🧠 Methodology

We formulate this as a **multi-class image classification** problem. Our primary model is a modified version of **YOLOv11n**, enhanced using:

- 📐 **Multi-Scale Edge Attention (EA)** — To detect subtle food residue boundaries.
- 🌈 **Channel Attention (CA)** — To focus on color and texture variations.
- 📍 **Spatial Attention (SA)** — To localize regions with food remnants.

We experimented with various combinations of these attention modules to evaluate their performance.

## 📊 Results

| Model Variant         | Accuracy | Precision | Recall | F1-Score |
|----------------------|----------|-----------|--------|----------|
| YOLOv11n (Baseline)  | 86.83%   | 84.68%    | 83.4%  | 84.03%   |
| Only CA              | **88.23%**   | 85.62%    | 86.12% | **85.87%**   |
| SA + EA              | 88.23%   | **88.87%** | 80.67% | 83.65%   |
| CA + SA + EA         | 87.95%   | 85.35%    | 82.01% | 83.64%   |

## 📁 Directory Structure

```
CV_PROJECT_FILES/
├── codes/
│   └── cv_test/
│       ├── cv_runs/          # Experiment results for different model variants
│       ├── data/             # Train/test split
│       └── just-normal.ipynb # Notebook for baseline and training
├── training_logs/           # .rtf logs from different experiments
├── README.md
```

## 🖼️ Dataset

- Collected ~2,570 real-world images from IIT Kanpur mess.
- Annotated into `Low`, `Medium`, and `High` food wastage classes.
- Added 1000+ background images to improve robustness.
- Augmentation: flipping, rotation, contrast adjustment, etc.

📦 [Google Drive Dataset (Public)](https://drive.google.com/drive/folders/11oUunTKyqpHTv9fFiNEe3ZrSLZPC5A0z)

## 🚀 Deployment

Future plans include integration into a mobile app to classify waste in real-time using a smartphone camera.

## 📄 License

This project is open-sourced under the MIT License.
