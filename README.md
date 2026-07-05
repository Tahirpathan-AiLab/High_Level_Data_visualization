## Code Description

This project focuses on processing, visualizing, and preparing accelerometer and gyroscope sensor data collected using **MetaMotion wearable fitness tracking bands**. The goal is to transform raw sensor recordings into clean, structured, and analysis-ready datasets that can be used to build machine learning models for **barbell exercise classification** and **repetition counting**.

The original dataset was collected by **Dave Ebbelaar** and his collaborators during workout sessions involving **five participants** performing different barbell exercises with varying weight categories. My contribution begins after the data collection stage, where I designed and implemented the complete data processing pipeline using Python.

This repository demonstrates how raw sensor recordings can be transformed through data preprocessing, time-series synchronization, visualization, and statistical outlier detection to produce high-quality datasets suitable for machine learning applications.

### Overview

The workflow begins by importing the required Python libraries, including **Pandas** for data manipulation, **NumPy** for numerical computations, **Matplotlib** for visualization, **SciPy** for statistical analysis, **Scikit-learn** for machine learning-based outlier detection, and **Glob** for automatically reading multiple sensor files.

The raw accelerometer and gyroscope recordings are loaded from the MetaMotion dataset. Metadata such as the participant identifier, exercise label, and weight category are automatically extracted from the filenames, eliminating the need for manual annotation.

The accelerometer and gyroscope measurements are merged into a unified time-series dataset. Sensor timestamps are converted into datetime format, and both sensor streams are synchronized using time-series resampling to create consistent observations across different sampling frequencies.

To better understand the characteristics of the sensor data, the project includes exploratory visualizations using box plots and histograms. These visualizations help analyze data distributions and identify unusual observations before applying machine learning.

To improve dataset quality, three statistical outlier detection techniques are implemented and compared:

* **Interquartile Range (IQR)** for distribution-based outlier detection.
* **Chauvenet's Criterion** for probability-based anomaly detection.
* **Local Outlier Factor (LOF)** for density-based anomaly detection.

Finally, the processed dataset and the cleaned dataset are exported as Pickle files, providing reusable datasets for the next stages of the machine learning pipeline, including feature engineering, exercise classification, and repetition counting.

---

## Key Features

* Reads multiple accelerometer and gyroscope CSV files automatically
* Extracts participant information, exercise labels, and weight categories from filenames
* Merges accelerometer and gyroscope recordings into a unified dataset
* Converts timestamps into a structured datetime format
* Synchronizes sensor data using time-series resampling
* Performs exploratory data visualization using box plots and histograms
* Detects abnormal observations using **Interquartile Range (IQR)**
* Detects outliers using **Chauvenet's Criterion**
* Detects anomalies using **Local Outlier Factor (LOF)**
* Generates clean datasets for future machine learning applications
* Exports processed datasets as reusable Pickle files
* Organized and reusable workflow for high-level data visualization

---

## Workflow

<p align="center">
  <img src="https://img.shields.io/badge/1-Import%20Libraries-4CAF50?style=for-the-badge"/>
</p>

<p align="center">⬇️</p>

<p align="center">
  <img src="https://img.shields.io/badge/2-Load%20Raw%20Sensor%20Data-2196F3?style=for-the-badge"/>
</p>

<p align="center">⬇️</p>

<p align="center">
  <img src="https://img.shields.io/badge/3-Extract%20Metadata-FF9800?style=for-the-badge"/>
</p>

<p align="center">⬇️</p>

<p align="center">
  <img src="https://img.shields.io/badge/4-Merge%20Sensor%20Data-E91E63?style=for-the-badge"/>
</p>

<p align="center">⬇️</p>

<p align="center">
  <img src="https://img.shields.io/badge/5-Convert%20Timestamps-9C27B0?style=for-the-badge"/>
</p>

<p align="center">⬇️</p>

<p align="center">
  <img src="https://img.shields.io/badge/6-Time%20Series%20Resampling-00BCD4?style=for-the-badge"/>
</p>

<p align="center">⬇️</p>

<p align="center">
  <img src="https://img.shields.io/badge/7-Visualize%20Sensor%20Data-795548?style=for-the-badge"/>
</p>

<p align="center">⬇️</p>

<p align="center">
  <img src="https://img.shields.io/badge/8-Detect%20Outliers%20(IQR)-607D8B?style=for-the-badge"/>
</p>

<p align="center">⬇️</p>

<p align="center">
  <img src="https://img.shields.io/badge/9-Chauvenet's%20Criterion-3F51B5?style=for-the-badge"/>
</p>

<p align="center">⬇️</p>

<p align="center">
  <img src="https://img.shields.io/badge/10-Local%20Outlier%20Factor-009688?style=for-the-badge"/>
</p>

<p align="center">⬇️</p>

<p align="center">
  <img src="https://img.shields.io/badge/11-Export%20Clean%20Dataset-4CAF50?style=for-the-badge"/>
</p>

---

## Technologies Used

<p align="center">
  <img src="https://skillicons.dev/icons?i=python" alt="Python"/>
  <img src="https://skillicons.dev/icons?i=vscode" alt="VS Code"/>
  <img src="https://skillicons.dev/icons?i=git" alt="Git"/>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white"/>
  <img src="https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white"/>
  <img src="https://img.shields.io/badge/Matplotlib-11557C?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/SciPy-8CAAE6?style=for-the-badge&logo=scipy&logoColor=white"/>
  <img src="https://img.shields.io/badge/Scikit--Learn-F7931E?style=for-the-badge&logo=scikitlearn&logoColor=white"/>
  <img src="https://img.shields.io/badge/Glob-4CAF50?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Pickle-FFCA28?style=for-the-badge"/>
</p>

---

## Project Structure

```text
High_Level_Data_visualization
│
├── data
│   ├── raw
│   │   └── MetaMotion
│   │       ├── Accelerometer CSV Files
│   │       └── Gyroscope CSV Files
│   │
│   └── interim
│       ├── data_processed.pkl
│       └── outliers_removed_chauvenet.pkl
│
├── src
│   ├── data
│   │   └── make_dataset.py
│   │
│   └── features
│       └── remove_outliers.py
│
├── requirements.txt
└── README.md
```

---

## Output

After successful execution, the project generates:

* **data_processed.pkl** – Processed and synchronized accelerometer and gyroscope dataset
* **outliers_removed_chauvenet.pkl** – Clean dataset after statistical outlier removal
* Box plot visualizations for sensor comparison
* Histogram visualizations for distribution analysis
* Time-series dataset with synchronized sensor readings
* Clean and reusable datasets for future machine learning applications

This project represents the **High Level** stage of my Data Visualization learning series. It extends the concepts introduced in my **Intermediate Level Data Visualization** project by introducing wearable sensor data processing, time-series synchronization, statistical visualization, and advanced outlier detection techniques. The generated datasets provide a strong foundation for future machine learning tasks such as exercise classification, repetition counting, and human activity recognition.
