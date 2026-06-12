# Lung Cancer Classification Using Random Forest

## Project Overview

Project ini merupakan project machine learning untuk melakukan klasifikasi indikasi kanker paru-paru berdasarkan beberapa fitur kesehatan dan riwayat pasien. Model yang digunakan adalah **Random Forest Classifier** dengan pendekatan klasifikasi biner, yaitu memprediksi apakah seseorang **terindikasi** atau **tidak terindikasi** kanker paru-paru.

Pada project ini, terdapat dua skenario model yang dibandingkan:

1. **Baseline Random Forest Model**
   Model Random Forest yang dibuat tanpa hyperparameter tuning.

2. **Tuned Random Forest Model**
   Model Random Forest yang telah melalui proses hyperparameter tuning untuk mencari kombinasi parameter yang lebih optimal.

Tujuan utama dari project ini adalah membandingkan performa model Random Forest sebelum dan sesudah dilakukan hyperparameter tuning.

## Dataset

Dataset yang digunakan berisi data terkait kondisi dan gejala yang berhubungan dengan indikasi kanker paru-paru. Beberapa fitur yang digunakan dalam dataset antara lain:

* Age
* Gender
* Smoking
* Finger Discoloration
* Mental Stress
* Exposure to Pollution
* Long Term Illness
* Energy Level
* Immune Weakness
* Breathing Issue
* Alcohol Consumption
* Throat Discomfort
* Oxygen Saturation
* Chest Tightness
* Family History
* Smoking Family History
* Stress Immune

Target pada project ini adalah **Pulmonary Disease**, yang menunjukkan apakah seseorang terindikasi atau tidak terindikasi kanker paru-paru.

## Project Workflow

Tahapan yang dilakukan dalam project ini adalah sebagai berikut:

1. Import library yang dibutuhkan
2. Load dataset
3. Data understanding
4. Exploratory Data Analysis
5. Data preprocessing
6. Encoding data kategorikal
7. Split data menjadi data training dan testing
8. Pembuatan model baseline Random Forest
9. Evaluasi model baseline
10. Hyperparameter tuning pada Random Forest
11. Evaluasi model hasil tuning
12. Perbandingan hasil kedua model

## Data Preprocessing

Pada tahap preprocessing, data disiapkan agar dapat digunakan dalam proses pemodelan machine learning. Beberapa tahapan yang dilakukan meliputi pengecekan missing values, pengecekan tipe data, encoding data kategorikal, serta pemisahan fitur dan target.

Dataset kemudian dibagi menjadi data training dan data testing untuk melatih dan mengevaluasi performa model.

## Modeling

Algoritma yang digunakan pada project ini adalah **Random Forest Classifier**. Random Forest merupakan algoritma ensemble learning yang membangun banyak decision tree dan menggabungkan hasil prediksinya untuk menghasilkan prediksi akhir yang lebih stabil.

Pada project ini dibuat dua model:

### 1. Baseline Random Forest

Model pertama dibuat menggunakan Random Forest tanpa proses hyperparameter tuning. Model ini digunakan sebagai pembanding awal untuk mengetahui performa dasar algoritma Random Forest pada dataset.

### 2. Random Forest with Hyperparameter Tuning

Model kedua dibuat dengan melakukan hyperparameter tuning pada Random Forest. Tujuan dari proses tuning adalah mencari kombinasi parameter terbaik agar model dapat menghasilkan performa yang lebih optimal.

## Evaluation Metrics

Evaluasi model dilakukan menggunakan beberapa metrik klasifikasi, yaitu:

* Accuracy
* Precision
* Recall
* F1-Score
* Confusion Matrix

Dalam konteks klasifikasi kesehatan, nilai **False Negative** menjadi salah satu hal penting untuk diperhatikan. False Negative berarti data yang sebenarnya terindikasi, tetapi diprediksi sebagai tidak terindikasi oleh model.

## Model Comparison

### Baseline Random Forest

Hasil confusion matrix dari model baseline Random Forest:

| Actual / Predicted | Tidak Terindikasi | Terindikasi |
| ------------------ | ----------------: | ----------: |
| Tidak Terindikasi  |               531 |          40 |
| Terindikasi        |                49 |         380 |

Berdasarkan confusion matrix tersebut:

* True Negative (TN): 531
* False Positive (FP): 40
* False Negative (FN): 49
* True Positive (TP): 380

### Random Forest with Hyperparameter Tuning

Hasil confusion matrix dari model Random Forest setelah hyperparameter tuning:

| Actual / Predicted | Tidak Terindikasi | Terindikasi |
| ------------------ | ----------------: | ----------: |
| Tidak Terindikasi  |               531 |          40 |
| Terindikasi        |                46 |         383 |

Berdasarkan confusion matrix tersebut:

* True Negative (TN): 531
* False Positive (FP): 40
* False Negative (FN): 46
* True Positive (TP): 383

## Result

Berdasarkan hasil confusion matrix, model Random Forest hasil hyperparameter tuning menunjukkan performa yang sedikit lebih baik dibandingkan model baseline. Hal ini terlihat dari:

* Jumlah True Positive meningkat dari 380 menjadi 383.
* Jumlah False Negative menurun dari 49 menjadi 46.
* True Negative dan False Positive tetap sama.

Penurunan False Negative menunjukkan bahwa model hasil tuning lebih baik dalam mengenali data yang benar-benar terindikasi. Dalam konteks kesehatan, hal ini menjadi penting karena model yang memiliki False Negative lebih rendah dapat mengurangi kemungkinan kasus terindikasi yang salah diprediksi sebagai tidak terindikasi.

## Performance Summary

| Model                                 |  TN | FP | FN |  TP | Accuracy |
| ------------------------------------- | --: | -: | -: | --: | -------: |
| Random Forest                         | 531 | 40 | 49 | 380 |   91.10% |
| Random Forest + Hyperparameter Tuning | 531 | 40 | 46 | 383 |   91.40% |

Berdasarkan hasil tersebut, model Random Forest dengan hyperparameter tuning menghasilkan peningkatan performa kecil dibandingkan model baseline.

## Conclusion

Project ini berhasil membangun model klasifikasi biner untuk memprediksi indikasi kanker paru-paru menggunakan algoritma Random Forest. Perbandingan antara model baseline dan model hasil hyperparameter tuning menunjukkan bahwa tuning dapat memberikan peningkatan performa, terutama dalam menurunkan jumlah False Negative dan meningkatkan jumlah True Positive.

Meskipun peningkatannya tidak terlalu besar, model hasil hyperparameter tuning dapat dianggap lebih baik karena mampu mengenali lebih banyak data yang benar-benar terindikasi.

## Tools and Libraries

Project ini dibuat menggunakan:

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* Jupyter Notebook

## Disclaimer

Project ini dibuat untuk tujuan pembelajaran dan pengembangan portofolio machine learning. Model ini tidak dapat digunakan sebagai alat diagnosis medis. Pemeriksaan dan diagnosis penyakit tetap harus dilakukan oleh tenaga medis profesional.

## Author

Patrick Jonox Sihombing
