# Darrell-PWDK-Capstone-3

**Hotel Booking Demand Analysis with Machine Learning**
Oleh: Darrell Lokadeva Lim

## Tentang Notebook

[Darrell_Capstone3.ipynb](Darrell_Capstone3.ipynb) adalah proyek *machine learning* untuk **memprediksi pembatalan reservasi hotel** pada saat pemesanan dibuat. Industri perhotelan beroperasi dengan margin tipis, dan hampir **37% reservasi dibatalkan** sebelum kedatangan, sehingga kamar berpotensi kosong dan pendapatan hilang. Model ini membantu hotel mengantisipasi pemesanan mana yang berisiko dibatalkan agar bisa dikelola lebih awal (mis. *overbooking*, konfirmasi ulang, atau syarat deposit).

## Isi Notebook

Notebook disusun secara berurutan dari pemahaman masalah hingga penyimpanan model:

1. **Latar Belakang & Problem Statement** — konteks bisnis dan masalah yang diselesaikan.
2. **Metric Evaluation** — memakai **F1-score** pada kelas "Dibatalkan" karena data *imbalance* (63% tidak batal vs 37% batal) membuat *accuracy* menyesatkan.
3. **Data Understanding & EDA** — dataset ±83.573 baris, 11 kolom; mengeksplorasi sinyal seperti `deposit_type`, `market_segment`, dan asal negara tamu.
4. **Data Cleaning & Feature Engineering** — menangani *missing value*, keputusan mempertahankan baris duplikat, serta membuat fitur biner dan flag domestik.
5. **Preprocessing** — *stratified split*, `Pipeline` dengan `RobustScaler` + `OneHotEncoder`, dan `class_weight="balanced"` untuk menangani *imbalance*.
6. **Modelling & Hyperparameter Tuning** — membandingkan 4 algoritma (Logistic Regression, Decision Tree, Random Forest, HistGradientBoosting); **HistGradientBoosting** terpilih sebagai model terbaik.
7. **Model Evaluation** — evaluasi pada data uji, diagnosa *overfitting*, dan evaluasi bebas kebocoran data.
8. **Analisa Ambang Batas (Threshold)** — memilih *threshold* berbasis biaya bisnis, bukan sekadar 0,5 default.
9. **Model Interpretation & Limitations** — *permutation importance* serta keterbatasan model.
10. **Manfaat Bisnis, Kesimpulan & Penyimpanan Model** — penerapan praktis dan ekspor *pipeline* end-to-end.

## Hasil Utama

- Model terbaik: **HistGradientBoosting**, dengan **F1-score ±0,74** pada data uji (estimasi jujur tanpa kebocoran ±0,56).
- Fitur paling berpengaruh: `deposit_type`, `market_segment`, `total_of_special_requests`, `is_domestic`, dan `customer_type`.
- Menyediakan dua titik operasi: ambang **0,26** (recall ±96% untuk menekan pembatalan terlewat) dan ambang **0,48** (F1 optimal).

## File dalam Repository

- [Darrell_Capstone3.ipynb](Darrell_Capstone3.ipynb) — notebook analisis dan pemodelan.
- [Capstone_Hotel_Booking_Darrell.pptx](Capstone_Hotel_Booking_Darrell.pptx) — slide presentasi proyek.
