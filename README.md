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

  ## Mernjalankan Sistem Machine Learning
Sistem prediksi status dropout mahasiswa yang telah dikembangkan menggunakan algoritma machine learning (Random Forest) dan diintegrasikan ke dalam antarmuka pengguna berbasis Streamlit dapat dijalankan secara lokal maupun online. Pada bagian ini akan dijelaskan secara detail cara menjalankan sistem baik di lingkungan pengembangan lokal maupun di lingkungan produksi berbasis cloud.
1. Menjalankan Sistem Secara Lokal
Menjalankan sistem secara lokal merupakan tahap awal dalam pengembangan dan pengujian aplikasi sebelum dilakukan deployment ke server online.
- Persiapan Lingkungan
Sebelum menjalankan aplikasi secara lokal, pastikan perangkat yang digunakan telah memiliki:
  -  Python versi 3.8 atau lebih tinggi
  -  Pip (Python package manager)
  -  Koneksi internet
- Instalasi Dependensi
Buka terminal (Command Prompt atau Terminal Linux/macOS) dan jalankan perintah berikut untuk menginstal library yang dibutuhkan:
pip install streamlit pandas numpy matplotlib seaborn scikit-learn
- Menjalankan Aplikasi
  streamlit run student_performance.py
Aplikasi akan berjalan dan terbuka secara otomatis di browser pada alamat:
(http://localhost:8501)
- Menjalankan Sistem Secara Online
  Agar aplikasi dapat diakses oleh pengguna lain tanpa perlu menjalankan secara lokal, sistem dapat di-deploy menggunakan layanan Streamlit Cloud.
- Upload Kode ke GitHub
  Langkah pertama adalah mengunggah seluruh kode proyek ke repository GitHub. File yang harus disiapkan antara lain:
  - student_performance.py (kode utama aplikasi)
  - requirements.txt (daftar library)
  - README.md (opsional, dokumentasi proyek)
- Deploy ke Streamlit Cloud
     - Masuk ke situs https://streamlit.io/cloud
     - Login menggunakan akun GitHub
     - Klik tombol "New app"
     - Pilih repository dan branch tempat file student_performance.py berada
     - Klik Deploy
  - Mengakses Aplikasi
    Setelah proses deployment selesai, aplikasi akan tersedia di alamat seperti:
     https://studentsperformancegitdcs.streamlit.app/
  - Fitur Aplikasi yang Dijalankan
     - Visualisasi eksplorasi data (EDA)
     - Evaluasi model machine learning (confusion matrix, classification report)
     - Visualisasi feature importance
     - Prediksi individu berdasarkan input pengguna


**Kesimpulan:**
Sistem prediksi status dropout mahasiswa telah berhasil dibangun dan dapat dijalankan secara lokal maupun online. Proses deployment menggunakan Streamlit Cloud memudahkan distribusi dan penggunaan aplikasi oleh pengguna akhir tanpa memerlukan instalasi tambahan. Sistem ini dapat menjadi alat bantu pengambilan keputusan dalam mengidentifikasi risiko dropout mahasiswa secara lebih dini dan berbasis data. Proyek analisis data ini bertujuan untuk mengidentifikasi faktor-faktor utama yang memengaruhi status mahasiswa di Jaya Jaya Institut, khususnya terkait risiko dropout. Berdasarkan hasil eksplorasi data dan pemodelan, ditemukan bahwa sekitar 32,1% mahasiswa mengalami dropout, dengan proporsi lebih tinggi terjadi pada program studi tertentu seperti Advertising and Marketing Management serta Animation and Multimedia Design. Selain itu, mahasiswa yang mengikuti kursus persiapan tes memiliki kecenderungan lebih tinggi untuk lulus, sementara latar belakang pendidikan orang tua dan gender juga menunjukkan pola yang berpengaruh terhadap status akademik mahasiswa.  Model klasifikasi yang dibangun, seperti Decision Tree dan Random Forest, mampu memprediksi status mahasiswa dengan performa yang baik, dan dapat dijadikan alat bantu dalam proses deteksi dini mahasiswa berisiko tinggi. Visualisasi interaktif yang disusun dalam dashboard Metabase memberikan gambaran menyeluruh tentang pola dropout dan dapat digunakan sebagai dasar pengambilan keputusan strategis. Secara keseluruhan, hasil proyek ini merekomendasikan perlunya penguatan dukungan akademik pada program studi dengan tingkat dropout tinggi, peningkatan akses terhadap program pembekalan akademik, serta penerapan sistem monitoring prediktif untuk mengurangi angka putus studi secara efektif.
## Rekomendation acation item

Berdasarkan hasil eksplorasi data, pelatihan model prediksi dropout, dan evaluasi performa model, beberapa pola signifikan telah ditemukan terkait karakteristik mahasiswa yang memiliki risiko tinggi mengalami dropout. Temuan ini dapat dijadikan dasar untuk menyusun langkah-langkah konkret yang dapat diambil oleh institusi pendidikan guna mengurangi angka dropout. Berikut adalah rekomendasi tindakan (action items) yang bersifat praktis dan berbasis data:
-  Intervensi Dini Berdasarkan Usia Masuk Kuliah
   Temuan: Mahasiswa dengan usia masuk kuliah yang lebih tinggi dari rata-rata (di atas 25 tahun) cenderung memiliki risiko dropout lebih tinggi.
   rekomendasi:
   - Sediakan program orientasi atau adaptasi khusus untuk mahasiswa usia dewasa.
   - Fasilitasi dukungan akademik dan konseling karier yang relevan dengan kebutuhan mereka (misalnya, jadwal fleksibel, kelas malam, atau pembelajaran online).
- Pendampingan Akademik untuk Mahasiswa Tahun Pertama
  Temuan: Model menunjukkan bahwa mahasiswa dengan performa rendah pada semester awal memiliki probabilitas lebih tinggi untuk dropout.
  Rekomendasi:
  - Implementasi program pendampingan akademik sejak semester pertama.
  - Gunakan sistem early warning berbasis data (seperti sistem ini) untuk mengidentifikasi mahasiswa dengan performa rendah dan segera memberikan intervensi.
-  Pendekatan Personal Berdasarkan Gender dan Status Pernikahan
    Temuan: Visualisasi menunjukkan perbedaan pola dropout berdasarkan gender dan status pernikahan.
   Rekomendasi:
   - Lakukan survei tambahan untuk memahami tantangan yang dihadapi oleh masing-masing kelompok (misalnya, tanggung jawab keluarga pada mahasiswa yang sudah menikah).
   - Rancang program dukungan yang inklusif, seperti child care support, peer mentoring berbasis gender, dan pelatihan manajemen waktu.
- Evaluasi dan Penyesuaian Kurikulum Kursus Tertentu
  Temuan: Beberapa jenis program studi (courses) memiliki tingkat dropout lebih tinggi dari yang lain.
  Rekomendasi:
  - Lakukan evaluasi kurikulum dan beban studi program studi dengan dropout tinggi.
  - Pertimbangkan desain ulang kurikulum yang terlalu berat di awal semester atau memiliki tingkat kesulitan tinggi.
  - Sediakan pelatihan tambahan (bridging course) untuk mahasiswa baru di jurusan tersebut.
- Integrasi Sistem Prediksi ke Dalam Sistem Akademik
   Temuan: Model Random Forest yang dikembangkan mampu mengklasifikasikan mahasiswa berdasarkan risiko dropout dengan akurasi yang baik.
   Rekomendasi:
  - Integrasikan sistem ini ke dalam sistem akademik kampus untuk digunakan oleh bagian akademik dan konselor mahasiswa.
  - Lakukan pembaruan model secara berkala berdasarkan data terbaru untuk menjaga akurasi dan relevansi prediksi.
- Monitoring dan Evaluasi Berkala
  Rekomendasi:
  - Buat tim khusus untuk memantau efektivitas intervensi berdasarkan hasil sistem prediksi.
  - Terapkan proses continuous improvement melalui umpan balik dari mahasiswa dan dosen pembimbing.
- Sosialisasi dan Pelatihan Staf Akademik
  Rekomendasi:
  - Lakukan pelatihan kepada dosen wali dan bagian akademik agar memahami penggunaan sistem prediksi dan dapat menindaklanjuti hasilnya secara tepat.
  - Dorong budaya pengambilan keputusan berbasis data di lingkungan akademik.

**Akses akun metabase**

**Email : dickysaragih050901@gmail.com**

**Password : dickycandidsaragih5**
link dahsboard Metabase: https://localhost:3000/public/dashboard/6afde98e-58a7-4227-967d-7ecc1fe2ec24

**link streamlit:** https://studentsperformancegitdcs.streamlit.app/



