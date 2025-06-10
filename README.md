# Kelompok 8 Project UAS Penambangan Data (Data Mining)
1. Dea Kurnia Wati (23031554001)
2. Reiviena Bellia Agitha (23031554143)
3. Reva Deshinta Isyana (23031554153)
4. Zahra Zaskia Nabila (23031554222)
   
# Judul
Perbandingan Prediksi Harga Dua Saham (BBCA &amp; ANTM) Menggunakan Metode Forecasting LSTM dan Evaluasi Akurasinya

# Latar Belakang
Pasar saham merupakan instrumen investasi yang populer, namun pergerakan harganya sangat dinamis dan sulit diprediksi. Untuk membantu investor dalam pengambilan keputusan, dibutuhkan metode prediksi yang andal. Model Long Short-Term Memory (LSTM) sebagai bagian dari deep learning memiliki kemampuan memahami pola waktu dan tren historis, sehingga potensial untuk digunakan dalam prediksi harga saham.
# Rumusan Masalah:
1. Apakah model LSTM dapat digunakan untuk memprediksi harga saham BBCA dan ANTM?
2. Seberapa akurat prediksi harga saham menggunakan model LSTM berdasarkan data historis?
# Tujuan:
1. Menerapkan model LSTM untuk memprediksi harga saham BBCA dan ANTM.
2. Mengevaluasi kinerja model menggunakan metrik MAE, MSE, dan RMSE.

# Metode
Forecasting menggunakan LSTM
# Dataset
Dari Yahoo Finance dengan rentang 5 Mei 2023 sampai 5 Mei 2025 maka data yang kami pakai adalah data historis (historical data) bukan real-time. Data ini mencerminkan pergerakan harga saham harian dan digunakan sebagai dasar untuk pelatihan dan evaluasi model prediksi.
# Langkah-langkah
1. Data Collecting
2. EDA
3. Preprocessing
4. Scaling Data
5. Splitting Data
7. Windowing Data
8. Modeling
9. Evaluasi Model

# Hasil dan Analisis
1. Hasil Pelatihan Model
Setelah melakukan proses pelatihan model LSTM terhadap data historis harga saham BBCA dan ANTM yang telah dinormalisasi dengan metode MinMax Scaling dan diolah menggunakan teknik windowing, diperoleh hasil evaluasi sebagai berikut:
- BBCA:
  MAE (Mean Absolute Error): 0.07441948354244232
  MSE (Mean Squared Error): 0.008251288905739784
  RMSE (Root Mean Squared Error): 0.09083660553840497
- ANTM:
  MAE (Mean Absolute Error): 0.06108522042632103
  MSE (Mean Squared Error): 0.007287565618753433
  RMSE (Root Mean Squared Error): 0.08536723972785716
Dari nilai-nilai tersebut, dapat dilihat bahwa model LSTM mampu memberikan error yang relatif kecil dalam memprediksi harga saham yang telah diskalakan. Nilai RMSE yang mendekati nol menunjukkan bahwa perbedaan antara nilai aktual dan prediksi cukup kecil.
2. Visualisasi Hasil Prediksi
Grafik hasil prediksi dan nilai aktual dari harga saham BBCA dan ANTM menunjukkan bahwa model dapat mengikuti tren umum dari harga saham. Pola naik dan turun yang terjadi secara historis dapat ditangkap dengan cukup baik oleh model, terutama pada saham ANTM. Namun, terdapat deviasi kecil pada beberapa titik ekstrem yang umum terjadi dalam data pasar finansial.
3. Perbandingan Prediksi Saham BBCA dan ANTM
Meskipun model yang digunakan sama, performa prediksi pada saham ANTM sedikit lebih baik daripada BBCA, terlihat dari nilai MAE dan RMSE yang lebih rendah. Hal ini bisa disebabkan oleh:
- Volatilitas saham: BBCA sebagai saham blue chip cenderung lebih stabil, sedangkan ANTM memiliki volatilitas yang lebih tinggi, yang terkadang justru membuat pola jangka pendeknya lebih mudah dipelajari oleh model.
- Pola tren historis: Saham ANTM kemungkinan memiliki pola historis yang lebih konsisten dalam jendela waktu tertentu, sehingga model dapat belajar lebih efektif.
4. Analisis Model
Model LSTM cukup efektif digunakan untuk memodelkan data time series karena mampu mengingat informasi dari urutan sebelumnya (melalui memory cell dan mekanisme gating). Model ini dilatih menggunakan dua lapisan LSTM dengan jumlah unit masing-masing 64 dan 32, serta satu output layer untuk memprediksi harga di masa depan. Namun, hasil ini masih terbatas pada data yang telah diskalakan dan belum dikembalikan ke harga aktual (inverse scaling), sehingga interpretasi angka-angka prediksi tetap berada pada skala [0,1]. Untuk aplikasi nyata seperti pengambilan keputusan investasi, perlu dilakukan inverse scaling untuk mendapatkan nilai harga sebenarnya.

# Kesimpulan
Model LSTM berhasil digunakan untuk memprediksi harga saham BBCA dan ANTM berdasarkan data historis. Model memberikan performa yang cukup baik dengan nilai error yang rendah pada kedua saham. Namun, model lebih baik dalam mengikuti tren umum (seperti pada saham ANTM) dibanding menangkap fluktuasi tajam (seperti pada BBCA). Hal ini menunjukkan LSTM cocok untuk prediksi jangka pendek dengan pola musiman atau tren yang stabil.
# Saran
Penambahan variabel input seperti volume perdagangan, indikator teknikal (MACD, RSI), atau sentimen pasar dapat meningkatkan akurasi model.

