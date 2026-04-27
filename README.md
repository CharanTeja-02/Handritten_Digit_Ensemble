# Handwritten Digit Ensemble — MNIST

## Neural Networks & Deep Learning Project

---

## Project Overview
This project focuses on improving handwritten digit classification accuracy using Ensemble Learning (Bagging) on the MNIST dataset.

Instead of relying on a single neural network, we combine predictions from three different Multi-Layer Perceptron (MLP) models to achieve better performance.

Additionally, Model Compression techniques such as Weight Pruning and 8-bit Quantization are applied to make the model efficient for real-world deployment.

---

## Objectives
- Build multiple MLP models with different architectures  
- Improve accuracy using ensemble learning  
- Apply regularization techniques to prevent overfitting  
- Reduce model size using pruning and quantization  
- Evaluate performance using metrics and visualizations  

---

## Dataset Details
- Dataset: MNIST  
- Total Samples: 70,000  
  - Training: 60,000  
  - Testing: 10,000  
- Image Size: 28 × 28 (Grayscale)  
- Input Size: 784 (Flattened)  
- Classes: 10 (Digits 0–9)  

---

## Model Architectures

### MLP-1 (Wide Model)
- Layers: 512 → 256  
- Features: Batch Normalization, Dropout, L2 Regularization  

### MLP-2 (Deep Model)
- Layers: 256 → 128 → 64 → 32  
- Features: Dropout, RMSProp optimizer  

### MLP-3 (Pyramid Model)
- Layers: 512 → 256 → 128  
- Features: L1 + L2 Regularization  

---

## Ensemble Method
We use Bagging via Probability Averaging:

- Each model outputs softmax probabilities  
- Final prediction = average of probabilities  
- Weighted ensemble uses validation accuracy  

---

## Training Details
- Epochs: 50  
- Batch Size: 256  
- Optimizers: Adam, RMSProp  
- Loss Function: Categorical Crossentropy  
- Validation Split: 80/20  
- Callbacks:
  - EarlyStopping  
  - ReduceLROnPlateau  

---

## Performance Results

| Model | Accuracy |
|------|---------|
| MLP1_Wide | 98.58% |
| MLP2_Deep | 97.82% |
| MLP3_Pyramid | 98.50% |
| Ensemble (Weighted) | 98.63% |

---

## Visualizations
- Loss vs Epoch curves  
- Accuracy vs Epoch curves  
- Confusion matrices  
- Sample predictions  

---

## Model Compression

### Weight Pruning
- 60% weights removed  
- Accuracy maintained (~98.54%)

### 8-bit Quantization (TFLite)
- Original Size: 2095 KB  
- Compressed Size: 537 KB  
- Reduction: 74.4%  

---

## Performance Improvement

| Metric | Before | After |
|------|--------|-------|
| Model Size | 2095 KB | 537 KB |
| Inference Time | 0.148 ms | 0.035 ms |
| Speedup | — | 4.19× |

---

## Key Insights
- Ensemble improves accuracy  
- Different architectures increase diversity  
- Pruning removes redundant weights  
- Quantization reduces model size significantly  
- Suitable for mobile and edge devices  

---

## Conclusion
This project successfully improves accuracy using ensemble learning and enhances efficiency using model compression techniques, making it suitable for real-world deployment.

---

## Technologies Used
- Python  
- TensorFlow / Keras  
- NumPy, Pandas  
- Matplotlib, Seaborn  
- Scikit-learn  

---

## Author
CHARAN TEJA

---

## Final Statement
This project combines accuracy improvement (ensemble learning) with efficiency optimization (model compression).
