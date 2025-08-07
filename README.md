# README: Fall Detection Using Supervised and Unsupervised Methods

## 📘 Overview

This project investigates whether the unsupervised Isolation Forest algorithm can achieve performance comparable to supervised models (Random Forest, SVM, MLP) for fall detection using wearable sensor data. It uses a publicly available dataset containing over 8,900 activities from 29 subjects, including accelerometer, gyroscope, temperature, and altitude data.

---

## 📂 Dataset

The dataset is publicly hosted on Figshare and includes 8,953 activities collected from 29 subjects. Activities include 2,791 falls and 6,162 ADLs, with each CSV file capturing ~8 seconds of 100Hz sensor data. Columns include:

- AccX, AccY, AccZ
- Magnitude
- GyroX, GyroY, GyroZ
- Temperature
- Altitude

---

## 📁 Project Structure

- `FallDetection.ipynb` – Main Jupyter notebook implementing all supervised and unsupervised models
- `Data_Science_Report.pdf` – Full technical report including background, methodology, results, and discussion
- `Link_to_dataset.pdf` – Contains the citation and access link to the fall detection dataset used

---

## ⚙️ Methodology

1. **Feature Engineering**: 48 statistical features per file extracted; reduced to 32 using Pearson correlation filtering.
2. **Supervised Models**: Random Forest, SVM (RBF), and MLP with stratified 5-fold cross-validation.
3. **Unsupervised Model**: Isolation Forest evaluated with varying contamination levels.
4. **Class Imbalance Handling**: SMOTE applied to training data to address fall/ADL imbalance.
5. **Evaluation Metrics**:
   - Supervised: Balanced Accuracy
   - Unsupervised: ROC AUC Score

---

## 📊 Results Summary

- 🥇 **Random Forest** achieved the highest supervised performance  
  - Best Balanced Accuracy: **0.9827**
- ❄️ **Isolation Forest** peaked at **ROC AUC 0.6720** at contamination = 0.50
- 🔍 **KMeans clustering** on PCA and autoencoder-reduced data produced limited separability (ARI ≈ 0.18–0.19)
- ⭐ **Top Features**: 
  - `AccX range`
  - `AccZ min`
  - `GyroX range`

---

## ⚠️ Disclaimer

This project is a student research submission and should not be used for clinical deployment without further validation.
