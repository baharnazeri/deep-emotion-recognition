# 😊 Facial Emotion Recognition using ResNet-50

> Deep learning-based facial emotion classification using a fine-tuned **ResNet-50** model.

---

## 🚀 Overview

This project focuses on **facial emotion recognition**, a key problem in computer vision with applications in:

- Human–Computer Interaction  
- Behavioral Analytics  
- Affective Computing  
- Assistive Technologies  

A pretrained **ResNet-50 (ImageNet)** model is fine-tuned to classify facial images into **7 emotion categories**.

---

## 🎯 Objective

To build and evaluate a robust deep learning pipeline capable of recognizing human emotions from facial images.

---

## 📊 Dataset

- **Source:** Kaggle Facial Expression Recognition Dataset  
- **Classes (7):**
  - Angry  
  - Disgust  
  - Fear  
  - Happy  
  - Neutral  
  - Sad  
  - Surprise  

### Data Split:
- Train: 28,821 images  
- Validation: 3,533 images  
- Test: 3,533 images  

---

## 🧠 Model Architecture

- Backbone: **ResNet-50 (pretrained on ImageNet)**  
- Modified final layer → 7 output classes  
- Trainable parameters: ~23.5M  

---

## ⚙️ Training Setup

- Loss Function: Weighted Cross-Entropy  
- Optimizer: Adam (lr = 1e-4)  
- Batch Size: 128  
- Epochs: 25  
- Metrics:
  - Accuracy  
  - F1-score  

---

## 🔄 Preprocessing & Augmentation

- Resize to **224×224**
- Random horizontal flip  
- Small rotation (±10°)  
- Normalization using ImageNet statistics  

---

## 📈 Results

| Phase       | Accuracy | F1-score |
|------------|---------|---------|
| Train      | ~99%    | ~99%    |
| Validation | ~71%    | ~71%    |
| Test       | ~69%    | ~69%    |

📌 Observation:
- High training accuracy indicates strong learning  
- Lower validation/test performance suggests **overfitting**  

---

## ⚠️ Key Issue Identified

A critical issue in the training loop caused **gradient accumulation**, leading to:

- Extremely low training loss  
- Poor generalization  

Fixing this is essential for improving performance. :contentReference[oaicite:0]{index=0}

---

## 🔍 Analysis

### Main Challenges:
- Class imbalance  
- Overfitting  
- Data variability (pose, lighting, occlusion)

### Observations:
- Large gap between training and validation performance  
- Model memorization instead of generalization  

---

## 🧪 Future Improvements

### Immediate:
- Fix gradient handling bug  
- Add early stopping  

### High-impact:
- Stronger data augmentation (CutMix, MixUp)  
- Regularization (Dropout, Weight Decay)  
- Learning rate scheduling  

### Advanced:
- Try modern architectures:
  - EfficientNet  
  - Vision Transformers (ViT)  
- Use Grad-CAM for interpretability  
- Improve dataset balance  

---

## 🧩 Project Structure

```
.
├── notebook.ipynb     # Main training & evaluation notebook
├── data/              # Dataset (not included)
├── models/            # Saved checkpoints
├── results/           # Metrics and outputs
└── README.md
```

---

## ▶️ How to Run

1. Install dependencies:
```bash
pip install torch torchvision numpy pandas matplotlib scikit-learn opencv-python
```

2. Run the notebook:
```bash
jupyter notebook
```

3. Open:
```
notebook.ipynb
```

---

## 📌 Key Concepts

- Transfer Learning  
- Convolutional Neural Networks (CNNs)  
- Image Classification  
- Overfitting & Generalization  
- Model Evaluation Metrics  

---

## ⚖️ Ethical Considerations

- Bias across demographics (age, gender, skin tone)  
- Privacy concerns with facial data  
- Risk of misuse in sensitive applications  



## ⭐️ Notes

This project demonstrates:
- Practical deep learning pipeline design  
- Model evaluation and error analysis  
- Critical debugging of training issues  

