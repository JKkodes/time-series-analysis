# Time Series Classification and Anomaly Detection

Classification, clustering, nearest-neighbor methods, and Matrix Profile analysis on time series data, using **tslearn** and **stumpy** in Python.

## What this project does
- Compares 1-nearest-neighbor with Euclidean distance and Dynamic Time Warping (DTW), and a kernel SVM, on the GunPoint and ECG200 datasets from the UCR/UEA archive
- Clusters time series with k-means (DTW) and k-Shape and scores the result with the Adjusted Rand Index
- Uses the tslearn `MatrixProfile` class, which runs stumpy underneath
- Finds motifs and anomalies with the Matrix Profile
- Applies the same methods to ECG heartbeats from Kaggle, including an experiment that hides one abnormal beat among normal ones and checks whether the Matrix Profile finds it

## Key findings
- [Fill in: Euclidean vs DTW results]
- [Fill in: clustering results]
- [Fill in: whether the Matrix Profile found the inserted abnormal beat]

## Data
- GunPoint and ECG200 come from the UCR/UEA Time Series Archive and are downloaded automatically by tslearn when the notebook runs.
- ECG Heartbeat Categorization Dataset by Shayan Fazeli on [Kaggle](https://www.kaggle.com/datasets/shayanfazeli/heartbeat). The data is not included in this repo.    Download `mitbih_test.csv`, place it in the same folder as the notebook, and set `DATA_DIR`. I used this file and split it into train and test sets myself (60/40,   stratified).

## Tools
Python, tslearn, stumpy, NumPy, pandas, Matplotlib, Google Colab

## Files
- `time_series_analysis.ipynb`: the full analysis
