# Two-Stage Anomaly Detection in Personalized Healthcare using SVM & SVR

This repository contains the implementation of a two-stage anomaly detection model for wireless body area networks (WBANs), designed for personalized healthcare monitoring. The approach leverages **Support Vector Machines (SVM)** for anomaly classification and **Support Vector Regression (SVR)** for contextual anomaly detection. The method effectively distinguishes between sensor malfunctions and actual medical emergencies, ensuring high accuracy in anomaly detection.

## 📌 Key Features

### Two-stage anomaly detection:
- **SVM** for point anomaly classification  
- **SVR** for contextual anomaly detection  

### Feature Engineering:
- **Average Heart Rate**
- **Heart Rate Difference**
- **ECG Rolling Mean & Standard Deviation**
- **MinMax Scaling** for feature normalization
- **Dynamic thresholding** based on machine learning techniques

✔ Achieves **up to 99.59% accuracy** in anomaly detection  
✔ Handles real-world physiological data for **early medical intervention**  

## 📂 Dataset

The dataset consists of **72,000 physiological readings** from **16 individuals** (12 healthy participants and 4 patients), recorded **thrice daily over five days**. Data includes:

- **Physiological attributes:** Body Temperature, Heart Rate (from two sensors), SpO₂, ECG.  
- **Anomaly labels:**  
  - `anomaly` (overall anomaly classification)  
  - `first` (point anomalies)  
  - `second` (contextual anomalies)  

## 📊 How It Works

### 1️⃣ Data Preprocessing  
- Reads the `modified_output.csv` dataset.  
- Assigns unique `Person_IDs`.  
- Labels individuals as **Healthy** (`Person_ID ≤ 12`) or **Patient** (`Person_ID > 12`).  
- Splits data into **training (healthy individuals)** and **testing (patients + remaining healthy individuals)**.  

### 2️⃣ Feature Engineering  
Extracts relevant health metrics such as:  
- **Heart Rate Average & Difference**  
- **ECG Rolling Mean & Standard Deviation**  

### 3️⃣ Anomaly Detection  
The two-stage detection process includes:  

- **SVM Classification:** Initially classifies anomalies using a **radial basis function (RBF) kernel**.  
- **SVR-Based Contextual Analysis:** Builds **regression models** for physiological attributes and detects anomalies based on residual errors.  

### 4️⃣ Evaluation  
- **Overall anomaly detection**  
- **Point anomaly detection**  
- **Contextual anomaly detection**  

## 📈 Performance Metrics  

| Model                   | Accuracy (%) |
|-------------------------|-------------|
| **Proposed (SVM + SVR)** | **99.59%**  |
| DBSCAN + KMeans         | 60.01%      |
| SVM (Standalone)        | 69.29%      |
| Linear Regression       | 60.00%      |

## 🏛 Funding Agency  

This research is supported by **BITS Bio-CyTiH Foundation** and the **Department of Science and Technology (DST), Government of India**. Their contributions have been instrumental in the development of this anomaly detection framework for **wireless body area networks (WBANs)** in personalized healthcare.
