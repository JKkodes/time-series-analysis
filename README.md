# Time Series Classification and Anomaly Detection

Classification, clustering, nearest-neighbor methods, and Matrix Profile analysis on time series data, using **tslearn** and **stumpy** in Python.

## What this project does
- Compares 1-nearest-neighbor with Euclidean distance and Dynamic Time Warping (DTW), and a kernel SVM, on the GunPoint and ECG200 datasets from the UCR/UEA archive
- Clusters time series with k-means (DTW) and k-Shape and scores the result with the Adjusted Rand Index
- Uses the tslearn `MatrixProfile` class, which runs stumpy underneath
- Finds motifs and anomalies with the Matrix Profile
- Applies the same methods to ECG heartbeats from Kaggle, including an experiment that hides one abnormal beat among normal ones and checks whether the Matrix Profile finds it

## Key findings
- **Euclidean vs DTW:** The better distance depended on the dataset. Euclidean was slightly better on GunPoint (0.913 vs 0.907) and clearly better on ECG200 (0.880 vs 0.770), while DTW was better on the 5-class Kaggle ECG subset (0.765 vs 0.715). A kernel SVM (GAK) scored 0.767 on GunPoint and 0.860 on ECG200.
- **Clustering:** Clusters matched the true classes poorly. On GunPoint both k-means (DTW) and k-Shape had an ARI of -0.019 (about random). On ECG200 k-Shape (0.168) beat k-means (0.092), and k-means on the Kaggle ECG subset scored 0.157.
- **Matrix Profile:** On ECG200 it found a motif pair at positions 32 and 223 (repeated heartbeat shape). In the anomaly experiment, with one abnormal beat hidden among nine normal ones, the highest peak (position 1387) did not fall inside the abnormal beat (935 to 1122) at window length 60, so this setup did not detect it.

  
## Data
- GunPoint and ECG200 come from the UCR/UEA Time Series Archive and are downloaded automatically by tslearn when the notebook runs.
- ECG Heartbeat Categorization Dataset by Shayan Fazeli on [Kaggle](https://www.kaggle.com/datasets/shayanfazeli/heartbeat). The data is not included in this repo.    Download `mitbih_test.csv`, place it in the same folder as the notebook, and set `DATA_DIR`. I used this file and split it into train and test sets myself (60/40,   stratified).

## Tools
Python, tslearn, stumpy, NumPy, pandas, Matplotlib, Google Colab

## Files
- `time_series_analysis.ipynb`: the full analysis
