# Hotel Booking Cancellation Prediction

## Deskripsi Proyek
Proyek ini bertujuan untuk menganalisis data pemesanan kamar hotel dan membangun model prediktif yang mampu mengidentifikasi apakah seorang pelanggan berpotensi membatalkan reservasinya. Melalui analisis data eksploratif (EDA) dan pembangunan model *machine learning*, proyek ini menyediakan wawasan mendalam dan solusi berbasis data untuk mendukung pengambilan keputusan operasional hotel.

## Tujuan Analisis
1. Mengidentifikasi karakteristik pelanggan yang melakukan pembatalan pemesanan.
2. Membangun dan menguji model prediksi untuk mengklasifikasikan apakah pelanggan berpotensi melakukan pembatalan. 
3. Mengidentifikasi fitur-fitur yang berpengaruh terhadap pembatalan.

## Dataset yang Digunakan
- Sumber: https://www.kaggle.com/datasets/mathsian/hotel-bookings
- Ukuran Data: ± 83 ribu baris
- Kolom Penting:
  <ol type="1">
    <li> <code>market_segment</code> – Jenis segmen pasar pemesanan </li>
    <li> <code>previous_cancellations</code> – Jumlah pemesanan sebelumnya yang pernah dibatalkan </li>
    <li> <code>booking_changes</code> – Jumlah perubahan atau pengeditan pada pemesanan </li>
    <li> <code>total_of_special_requests</code> – Jumlah permintaan khusus yang diajukan pelanggan </li>
    <li> <code>is_canceled</code> – Nilai yang menunjukkan apakah pemesanan dibatalkan atau tidak dibatalkan </li>
  </ol>

## Alur Pembuatan Model
1. **Data Understanding**
   - Mengumpulkan data pemesanan hotel dan memeriksa struktur, tipe data, serta kualitas data.
2. **Data Cleaning & Preprocessing**
    - Menangani *missing value*, data duplikat, dan *outliers* serta *encoding* pada fitur kategorikal.
3. **Exploratory Data Analysis (EDA)**
    - Menganalisis pola pembatalan, distribusi variabel, korelasi antar fitur, serta karakteristik pelanggan yang membatalkan pemesanan.
4. **Modeling**
    - Membangun beberapa model klasifikasi sebagai *baseline* untuk membandingkan performa model. Model yang diuji antara lain:
      <ol type="1">
        <li> Decision Tree </li>
        <li> Random Forest </li>
        <li> Logistic Regression </li>
        <li> K-Nearest Neighbors (KNN) </li>
        <li> Support Vector Machine (SVM) </li>
        <li> Extreme Gradient Boosting (XGBoost) </li>
        <li> Light Gradient Boosting Machine (LightGBM) </li>
        <li> Categorical Boosting (CatBoost) </li>
      </ol>
5. **Hyperparameter Tuning**
    - Melakukan optimasi parameter model menggunakan **GridSearchCV** untuk menemukan kombinasi parameter terbaik dari model.
6. **Evaluation**
    - Membandingkan performa model hasil *hyperparameter tuning* menggunakan metrik **Recall** untuk memilih model terbaik.
7. **Feature Importance**
    - Mengidentifikasi fitur-fitur yang paling berpengaruh tehadap pembatalan pemesanan.
  
## Hasil Analisis
1. Hotel X menghadapi tingkat pembatalan pemesanan yang tinggi, yaitu sekitar 24%.
2.	Karakteristik pelanggan yang memiliki risiko tinggi melakukan pembatalan, antara lain:
    - Pelanggan yang termasuk dalam kelompok pelanggan Online Travel Agent.
    - Pelanggan yang memiliki riwayat pembatalan tinggi (previous_cancellations > 13).
    - Pelanggan dengan jumlah perubahan pemesanan rendah (booking_changes < 10).
    - Pelanggan dengan sedikit permintaan khusus.
3.	Model Light Gradient Boosting Machine (LightGBM) memberikan performa terbaik untuk memprediksi pembatalan.
4.	Fitur-fitur yang paling berpengaruh terhadap pembatalan, yaitu **total_of_special_requests**, **booking_changes**, dan **previous_cancellations**.
