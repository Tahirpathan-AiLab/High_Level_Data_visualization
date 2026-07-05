# High Level Data Visualization

## Code Description

This project focuses on **high-level data visualization and preprocessing** using Python. It demonstrates how to process raw wearable sensor data, extract meaningful metadata, synchronize multiple sensor streams, visualize time-series signals, detect abnormal observations, and generate clean datasets for future machine learning applications.

This repository is a continuation of my **Intermediate Level Data Visualization** project, where I worked with structured datasets and preprocessing techniques. Here, I build upon those concepts by introducing wearable sensor data processing, time-series synchronization, statistical visualization, and multiple outlier detection techniques. The processed datasets generated in this project can be directly used for advanced machine learning tasks such as exercise classification and repetition counting.

### Overview

The workflow begins by importing the required libraries, including **Pandas** for data manipulation, **NumPy** for numerical computations, **Matplotlib** for visualization, **SciPy** for statistical calculations, **Scikit-learn** for machine learning-based outlier detection, and **Glob** for automatically reading multiple sensor files.

The project uses raw accelerometer and gyroscope recordings collected using **MetaMotion wearable fitness tracking bands**. Instead of manually loading each file, the script automatically reads every CSV file from the dataset directory and extracts useful metadata such as the participant identifier, exercise label, and weight category directly from the filename.

The accelerometer and gyroscope datasets are then merged into a single time-series dataset. Sensor timestamps are converted into datetime format, allowing efficient time-based analysis. Since both sensors operate at different sampling frequencies, the signals are resampled into a common **200-millisecond** interval to ensure synchronization.

After creating the processed dataset, the project performs exploratory data visualization using box plots and histograms to better understand the distribution of sensor measurements.

To improve data quality, three different outlier detection techniques are implemented and compared: **Interquartile Range (IQR)**, **Chauvenet's Criterion**, and **Local Outlier Factor (LOF)**. These methods help identify abnormal sensor readings that could negatively impact future machine learning models.

Finally, the processed dataset and the cleaned dataset are exported as **Pickle** files, allowing them to be efficiently reused in future analysis without repeating the preprocessing pipeline.

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
