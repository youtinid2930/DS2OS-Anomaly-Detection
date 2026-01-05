# DS2OS Anomaly Detection

Machine Learning and Deep Learning models for binary anomaly detection using the DS2OS IoT Traffic Traces dataset. The dataset captures application-layer traffic from simulated IoT environments with devices like light controllers, thermostats, smart doors, and movement sensors. The project focuses on detecting anomalies while handling concept drift in IoT behavior over time.

## Table of Contents
- [Dataset](#dataset)
- [Features](#features)
- [Project Structure](#project-structure)
- [Installation](#installation)
- [Usage](#usage)
- [References](#references)

## Dataset
The dataset was collected from four simulated IoT sites with varying organization and service types, designed to evaluate adaptive anomaly detection algorithms in smart spaces.
## Features
- Application-layer IoT traffic traces
- Binary labels: Normal vs Anomalous
- Concept drift handling for adaptive anomaly detection
- Preprocessed features include:
  - Device types and location
  - Operations and value semantics
  - Time-based features
  - Frequency metrics
  - Privacy scores

## Project Structure
```
DS2OS-Anomaly-Detection
├─ 0- Data_Pretraitement.ipynb
├─ 1- Random_Forest_Model.ipynb
├─ 2- SVM_model.ipynb
├─ 3- DNN_model.ipynb
├─ data
│  ├─ dataPreprocessed.csv
│  ├─ mainSimulationAccessTraces.csv
├─ models
│  ├─ dnn_model.pkl
│  ├─ rf.pkl
│  └─ svm_model.pkl
├─ pyproject.toml
├─ README.md
└─ requirements.txt
```

## Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/youtinid2930/DS2OS-Anomaly-Detection.git
   cd DS2OS-Anomaly-Detection
   ```
2. **Create a virtual environment (recommended)**
   ```
   python -m venv venv
   # Activate it
   # Windows
   venv\Scripts\activate
   # macOS/Linux
   source venv/bin/activate
   ```
3. **Install dependencies**
   ***Option 1: Using requirements.txt***
   ```
   pip install -r requirements.txt
   ```
   ***Option 2: Using pyproject.toml***
   ```
   pip install .
   ```
4. **Install Data**
Go to [DS2OS Traffic Traces on Kaggle](https://www.kaggle.com/datasets/francoisxa/ds2ostraffictraces) and download the mainSimulationAccessTraces.csv
and place it in the folder data.
## Usage
1. **Data Preprocessing**
   ```
   # Run preprocessing notebook
   # Generates `data/dataPreprocessed.csv` from raw DS2OS dataset
   ```
2. **Training & Evaluating Models**

***Random Forest***: 1- Random_Forest_Model.ipynb

***SVM***: 2- SVM_model.ipynb

***Deep Neural Network***: 3- DNN_model.ipynb

3. **Loading Saved Models**
   ```
   import joblib
   
   # Load Random Forest or SVM
   rf_model = joblib.load("models/rf.pkl")
   svm_model = joblib.load("models/svm_model.pkl")
   
   # Load DNN
   from tensorflow.keras.models import load_model
   dnn_model = load_model("models/dnn_model.pkl")
   ```
## References
- **Paper**: [IEEE Xplore Publication](https://ieeexplore.ieee.org/document/8529192) (Aubet & Pahl, 2018)
- **Dataset**: [DS2OS Traffic Traces on Kaggle](https://www.kaggle.com/datasets/francoisxa/ds2ostraffictraces)