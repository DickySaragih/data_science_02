# Proyek Akhir: Menyelesaikan Permasalahan Perusahaan Edutech

## Business Understanding
Jaya Jaya Institut, institusi pendidikan tinggi yang telah berdiri sejak tahun 2000, mengalami tantangan serius terkait jumlah mahasiswa yang tidak menyelesaikan pendidikannya (dropout). Tingginya angka dropout dapat berdampak pada reputasi institusi, menurunkan akreditasi, serta efisiensi penggunaan sumber daya.
Institusi ingin memanfaatkan data yang dimiliki untuk mendeteksi lebih awal mahasiswa yang berisiko mengalami dropout agar dapat diberikan intervensi lebih cepat dan tepat sasaran.

### Permasalahan Bisnis
1. Bagaimana karakteristik siswa yang paling berisiko mengalami dropout?
   - Apakah ada pola berdasarkan faktor seperti usia, status pernikahan, pekerjaan, atau performa akademik?
2. Apakah kita dapat membangun model prediktif yang akurat untuk mendeteksi potensi dropout sejak dini?
   - Model ini akan digunakan sebagai alat bantu untuk memantau siswa secara proaktif.
3. Faktor apa yang paling berpengaruh terhadap kemungkinan dropout siswa?
   - nformasi ini dapat menjadi dasar dalam merancang kebijakan atau program intervensi pendidikan.


### Cakupan Proyek
Untuk menjawab permasalahan bisnis, cakupan proyek ini meliputi:
1. Analisis data mahasiswa (nilai, kehadiran, status sosial ekonomi, dll.)
2. Identifikasi variabel paling berpengaruh terhadap dropout
3 . Membangun model machine learning untuk memprediksi dropout
  dengan tahapan sebagai berikut:
- Eksplorasi dan visualisasi data (EDA): Menggali pola dropout berdasarkan demografi dan variabel akademik.
   - Jenis kelamin (gender)
   - Usia (age_at_enrollment)
   - Status pernikahan (marital_status)
   - Pekerjaan (employment_status)
   - Kebutuhan khusus (disability)
   - Beasiswa (scholarship_holder)
     
- Preprocessing & Feature Engineering:
     - Penanganan missing values
     - Encoding variabel kategorik
     - Standarisasi fitur numerik
     -  data latih dan uji.
- Modeling (Klasifikasi): Membangun model klasifikasi seperti Random Forest untuk memprediksi status siswa (Dropout, Enrolled, Graduate).\
     - menggunakan model Rendom forest
- Evaluasi Model: Mengukur performa model dengan confusion matrix dan F1-score untuk memastikan efektivitas prediksi.
     - confusion matrix f1-score
- Visualisasi Hasil: Menyediakan visualisasi seperti confusion matrix dan grafik distribusi untuk mendukung interpretasi hasil.

 
### Persiapan

Sumber data diambil dari GitHub repository [dataset](https://github.com/DickySaragih/data_science_02/blob/main/Students_Performance.csv)

1.  **Import Libraries:** Mengimpor pustaka Python yang dibutuhkan untuk analisis data, pemodelan, dan visualisasi (pandas, numpy, matplotlib, seaborn, sklearn, gspread, google.colab.auth).
2.  **Load Dataset:** Mengunduh dataset dari URL yang disediakan ke dalam pandas DataFrame.
3.  **Cek Data:** Memeriksa struktur dataset, informasi kolom, dan distribusi data target ('Target').
4.  **Cleaning Data:**
    *   Membersihkan nama kolom (menghilangkan spasi, mengubah menjadi lowercase, menghapus karakter khusus).
    *   Mengganti nama kolom 'Target' menjadi 'dropout\_status'.
    *   Menghapus baris yang mengandung nilai yang hilang (missing values).
5.  **Exploratory Data Analysis (EDA):**
    *   Menganalisis distribusi status dropout.
    *   Memeriksa pengaruh gender terhadap status dropout.
    *   Menganalisis distribusi dropout berdasarkan jenis kursus.
    *   Menganalisis hubungan status pernikahan dengan dropout.
    *   Memeriksa hubungan usia saat masuk kuliah dengan status dropout.
    *   Menyimpulkan insight dari analisis eksplorasi data.
6.  **Data Preparation/Preprocessing:**
    *   Menghapus kolom yang tidak relevan atau tidak informatif.
    *   Mengodekan (encode) variabel kategorikal menjadi format numerik (menggunakan Label Encoding).
    *   Melakukan normalisasi (scaling) pada fitur numerik menggunakan StandardScaler.
    *   Membagi data menjadi set pelatihan (training) dan pengujian (testing) menggunakan `train_test_split` dengan strategi stratified sampling untuk menangani ketidakseimbangan kelas.
    *   Menyimpulkan insight dari tahapan data preparation.
7.  **Modeling:**
    *   Menginisialisasi model klasifikasi (menggunakan RandomForestClassifier).
    *   Melatih model menggunakan data pelatihan (X\_train, y\_train).
    *   Melakukan prediksi pada data pengujian (X\_test).
    *   Menyimpulkan insight dari proses modeling.
8.  **Model Evaluation:**
    *   Membuat dan menampilkan Confusion Matrix untuk melihat performa klasifikasi.
    *   Mencetak Classification Report yang mencakup metrik Precision, Recall, F1-Score, dan Support untuk setiap kelas.
    *   Menghitung dan mencetak F1-Score rata-rata (macro average).
    *   Menyimpulkan insight dari evaluasi model, terutama mengenai ketidakseimbangan performa pada kelas minoritas (dropout).
9.  **Visualisasi Data (Feature Importance):**
    *   Menghitung pentingnya (importance) setiap fitur dalam model yang sudah dilatih.
    *   Membuat DataFrame yang berisi nama fitur dan tingkat kepentingannya.
    *   Mengurutkan fitur berdasarkan tingkat kepentingannya.
    *   Mencetak daftar fitur teratas yang paling penting.
    *   Membuat dan menampilkan bar plot untuk memvisualisasikan 10 fitur teratas yang paling memengaruhi prediksi dropout.

Setup environment:

- pip install pipenv
- pipenv installpipenv shell
- pip install -r requirements.txt

## Business Dashboard
Jaya Jaya Institut, sebuah institusi pendidikan tinggi yang telah berdiri sejak tahun 2000, menghadapi tantangan serius berupa tingginya angka siswa yang tidak menyelesaikan pendidikannya (dropout). Meskipun telah mencetak banyak lulusan dengan reputasi baik, persentase dropout yang signifikan berpotensi merusak citra institusi serta menghambat kualitas lulusan yang dihasilkan.
Sebagai langkah strategis, institusi ingin memiliki dashboard analitik yang dapat menyajikan informasi dropout siswa secara visual dan interaktif. Tujuan dari dashboard ini adalah untuk:
1. Jumlah Dropout Berdasarkan Test Preparation Course
- Visualisasi menunjukkan jumlah siswa Graduate, Dropout, dan Enrolled berdasarkan jenis kursus persiapan.
- Kategori "Other (14)" mendominasi semua status siswa, termasuk dropout.
- Tiga kursus spesifik seperti Advertising and Marketing Management, Agronomy, dan Animation and Multimedia Design memiliki dropout cukup signifikan dibanding jumlah enrolled-nya.
![image](https://github.com/user-attachments/assets/9868ec5c-f79e-4e6f-9239-45f5d721d529)

2 Melacak distribusi dropout berdasarkan gender
- Female memiliki jumlah Graduate paling tinggi, tetapi juga mendominasi dalam kategori Dropout dan Enrolled.
- Perbandingan Dropout antara laki-laki dan perempuan relatif seimbang.
  ![image](https://github.com/user-attachments/assets/93b014bf-aeec-4274-bb78-3f410e5eae49)

3. distribusi dropout
- Total siswa: 4.424
- - 49.9% lulus (Graduate)
- 32.1% dropout
- 17.9% masih terdaftar (Enrolled)
  ![image](https://github.com/user-attachments/assets/01ec5e3a-aba7-4c48-b4aa-0ba17b3cffe8)
**Kesimpulan:**
  Proyek analisis data ini bertujuan untuk mengidentifikasi faktor-faktor utama yang memengaruhi status mahasiswa di Jaya Jaya Institut, khususnya terkait risiko dropout. Berdasarkan hasil eksplorasi data dan pemodelan, ditemukan bahwa sekitar 32,1% mahasiswa mengalami dropout, dengan proporsi lebih tinggi terjadi pada program studi tertentu seperti Advertising and Marketing Management serta Animation and Multimedia Design. Selain itu, mahasiswa yang mengikuti kursus persiapan tes memiliki kecenderungan lebih tinggi untuk lulus, sementara latar belakang pendidikan orang tua dan gender juga menunjukkan pola yang berpengaruh terhadap status akademik mahasiswa.
Model klasifikasi yang dibangun, seperti Decision Tree dan Random Forest, mampu memprediksi status mahasiswa dengan performa yang baik, dan dapat dijadikan alat bantu dalam proses deteksi dini mahasiswa berisiko tinggi. Visualisasi interaktif yang disusun dalam dashboard Metabase memberikan gambaran menyeluruh tentang pola dropout dan dapat digunakan sebagai dasar pengambilan keputusan strategis.
Secara keseluruhan, hasil proyek ini merekomendasikan perlunya penguatan dukungan akademik pada program studi dengan tingkat dropout tinggi, peningkatan akses terhadap program pembekalan akademik, serta penerapan sistem monitoring prediktif untuk mengurangi angka putus studi secara efektif.

**Akses akun metabase**
**Email : dickysaragih050901@gmail.com**

**Password : dickycandidsaragih5**
link dahsboard Metabase: https://localhost:3000/public/dashboard/6afde98e-58a7-4227-967d-7ecc1fe2ec24


## Menjalankan Sistem Machine Learning
Jelaskan cara menjalankan protoype sistem machine learning yang telah dibuat. Selain itu, sertakan juga link untuk mengakses prototype tersebut.



