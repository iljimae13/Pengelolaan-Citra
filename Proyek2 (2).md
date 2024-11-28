# Laporan Proyek Machine Learning - Leni Fitriani

# **Project Overview**

## **Latar Belakang**
Di era digital saat ini, sistem rekomendasi telah menjadi bagian penting dari platform online, seperti e-commerce, layanan streaming, dan media sosial. Dengan jumlah data yang terus meningkat, pengguna sering merasa kesulitan menemukan item yang relevan di antara jutaan pilihan yang tersedia. Sistem rekomendasi membantu pengguna dengan memberikan saran yang relevan berdasarkan preferensi mereka atau pola interaksi pengguna lain.

Sebagai contoh, platform streaming seperti **Netflix** menggunakan sistem rekomendasi untuk menyarankan film atau serial yang sesuai dengan preferensi pengguna. Hal serupa juga dilakukan oleh **Amazon** dalam merekomendasikan produk. Implementasi sistem ini tidak hanya meningkatkan pengalaman pengguna, tetapi juga berkontribusi pada keberhasilan bisnis secara keseluruhan.

## **Pentingnya Proyek**
Proyek ini penting untuk menyelesaikan masalah *information overload* yang dihadapi pengguna. Sistem rekomendasi yang akurat dapat:
1. **Meningkatkan Pengalaman Pengguna**:
   - Membantu pengguna menemukan film atau produk yang relevan tanpa usaha pencarian yang panjang.
2. **Meningkatkan Retensi dan Pendapatan Bisnis**:
   - Rekomendasi yang relevan meningkatkan kepuasan pengguna, mendorong mereka untuk kembali menggunakan layanan.
   - Dalam konteks bisnis, rekomendasi yang efektif dapat mendorong penjualan hingga **30%** (*McKinsey & Company, 2021*).

## **Hasil Riset Terkait**
Berikut adalah beberapa hasil riset yang menunjukkan pentingnya sistem rekomendasi:

1. **Netflix Recommender System**:
   - Hingga **75%** konten yang ditonton di Netflix berasal dari sistem rekomendasi. Dengan rekomendasi yang relevan, Netflix berhasil menghemat lebih dari **1 miliar dolar per tahun** dengan mengurangi jumlah pelanggan yang berhenti berlangganan (*Gomez-Uribe & Hunt, 2015*).

2. **Laporan McKinsey**:
   - Menurut laporan **McKinsey & Company (2021)**, personalisasi berbasis rekomendasi dapat meningkatkan penjualan hingga **30%** dan meningkatkan loyalitas pengguna secara signifikan.

3. **Pengaruh AI pada Rekomendasi**:
   - Dalam laporan **Harvard Business Review**, disebutkan bahwa personalisasi berbasis AI mampu meningkatkan loyalitas pengguna hingga **15%**, karena pengguna merasa rekomendasi lebih relevan dengan kebutuhan mereka (*Davenport et al., 2020*).

---

## **Referensi**
- Davenport, T., Guha, A., Grewal, D., & Bressgott, T. (2020). How AI Will Change the Future of Marketing. *Harvard Business Review*. Retrieved from [https://hbr.org/](https://hbr.org/)
- Gomez-Uribe, C. A., & Hunt, N. (2015). The Netflix Recommender System: Algorithms, Business Value, and Innovation. *ACM Transactions on Management Information Systems*, *6*(4), 1-19. [https://doi.org/10.1145/2843948](https://doi

# **Business Understanding**

## **Problem Statements**
Sistem rekomendasi bertujuan untuk mengatasi tantangan besar dalam membantu pengguna menemukan item yang relevan. Dalam proyek ini, kami mengidentifikasi beberapa masalah utama:

1. **Pernyataan Masalah 1**:  
   Pengguna merasa kesulitan menemukan film yang sesuai dengan preferensi mereka karena banyaknya pilihan yang tersedia (information overload).  

2. **Pernyataan Masalah 2**:  
   Pengguna baru atau film baru sering kali tidak mendapatkan rekomendasi yang akurat (*cold start problem*), karena minimnya data interaksi yang tersedia.  

3. **Pernyataan Masalah 3**:  
   Tidak adanya personalisasi dalam rekomendasi menyebabkan pengguna kehilangan minat untuk mengeksplorasi lebih banyak film.  

---

## **Goals**
Proyek ini bertujuan untuk memberikan solusi atas pernyataan masalah di atas dengan membangun sistem rekomendasi yang dapat:  

1. **Jawaban Pernyataan Masalah 1**:  
   Mengurangi *information overload* dengan merekomendasikan film yang relevan berdasarkan preferensi pengguna dan pola interaksi pengguna lain.  

2. **Jawaban Pernyataan Masalah 2**:  
   Mengatasi *cold start problem* dengan memanfaatkan metadata film (genre, deskripsi) dan pola interaksi yang ada.  

3. **Jawaban Pernyataan Masalah 3**:  
   Menyediakan rekomendasi yang personal untuk meningkatkan keterlibatan pengguna dan kepuasan mereka terhadap platform.  

---

## **Solution Approach**
Untuk mencapai tujuan proyek ini, kami menggunakan dua pendekatan utama dalam membangun sistem rekomendasi:

### **Solution 1: Content-Based Filtering**
Pendekatan ini memanfaatkan metadata film seperti genre, judul, dan deskripsi untuk menghitung kesamaan antar item.  
- **Kelebihan**:
  - Tidak membutuhkan data interaksi pengguna lain.
  - Dapat memberikan rekomendasi untuk film baru.  
- **Kekurangan**:
  - Terbatas pada item yang memiliki metadata.
  - Tidak dapat merekomendasikan film yang tidak serupa dengan item yang pernah dilihat pengguna.  

### **Solution 2: Collaborative Filtering**
Pendekatan ini menganalisis pola interaksi pengguna dengan film untuk memberikan rekomendasi.  
- **Kelebihan**:
  - Dapat menemukan pola tersembunyi yang tidak terlihat dari metadata.
  - Memberikan rekomendasi berdasarkan preferensi kolektif pengguna lain.  
- **Kekurangan**:
  - Rentan terhadap masalah *cold start*.
  - Memerlukan data interaksi yang cukup untuk menghasilkan rekomendasi yang akurat.  

### **Hybrid Approach (Opsional)**
Menggabungkan Content-Based Filtering dan Collaborative Filtering untuk memanfaatkan keunggulan masing-masing pendekatan.  
- **Contoh Implementasi**:  
  - Gunakan Content-Based Filtering untuk menangani film baru dan Collaborative Filtering untuk menangkap pola interaksi global.

---

## **Kesimpulan**
Dengan solusi yang diusulkan, proyek ini bertujuan untuk membangun sistem rekomendasi yang relevan, personal, dan mampu mengatasi tantangan seperti *information overload* dan *cold start problem*.  

# **Data Understanding**

## **Informasi Dataset**
Dataset yang digunakan adalah **MovieLens 100k Dataset**, yang berisi **100,000 interaksi** pengguna dengan film dalam bentuk rating. Dataset ini menyediakan data lengkap untuk membangun sistem rekomendasi, termasuk metadata film, informasi pengguna, dan genre.

**Sumber Data**:  
Dataset ini dapat diakses dan diunduh melalui tautan berikut:  
[MovieLens 100k Dataset - Kaggle](https://www.kaggle.com/datasets/prajitdatta/movielens-100k-dataset/data)

### **Statistik Umum Dataset**
- **Jumlah Pengguna**: 943  
- **Jumlah Film**: 1,682  
- **Jumlah Rating**: 100,000  
- **Skala Rating**: 1 (sangat buruk) hingga 5 (sangat baik).

Dataset terdiri dari beberapa file utama yang masing-masing memiliki fungsi khusus:

---

#### **Jumlah Data**
Dataset terdiri dari beberapa file dengan rincian sebagai berikut:
1. **Ratings Data** (`u.data`):
   - **Jumlah baris**: 100,000 (interaksi pengguna dengan film berupa rating).
   - **Jumlah kolom**: 4 (`user_id`, `item_id`, `rating`, `timestamp`).
2. **Movies Data** (`u.item`):
   - **Jumlah baris**: 1,682 (jumlah total film dalam dataset).
   - **Jumlah kolom**: 24 (informasi tentang judul, genre, dan metadata lainnya).
3. **Users Data** (`u.user`):
   - **Jumlah baris**: 943 (jumlah pengguna).
   - **Jumlah kolom**: 5 (`user_id`, `age`, `gender`, `occupation`, `zip_code`).

---

### **Kondisi Data**
1. **Missing Value**:
   - **Ratings Data**: Tidak ada missing value.
   - **Movies Data**: Kolom tertentu (seperti `release_date`) memiliki nilai kosong yang perlu ditangani.
   - **Users Data**: Tidak ada missing value.
2. **Duplikat**:
   - Tidak ditemukan duplikat dalam dataset.
3. **Outlier**:
   - Pada data `age` dalam `u.user`, beberapa pengguna memiliki usia ekstrem (misalnya, di atas 70 tahun). Namun, ini masih relevan untuk analisis.
4. **Distribusi Rating**:
   - Rating berkisar dari 1 hingga 5, dengan mayoritas rating di rentang 3–4.

---

### **Uraian Seluruh Fitur pada Data**
Berikut adalah penjelasan setiap fitur pada dataset:

#### **Ratings Data (`u.data`)**
| **Fitur**       | **Deskripsi**                                                                 |
|------------------|-------------------------------------------------------------------------------|
| `user_id`        | ID unik untuk setiap pengguna.                                               |
| `item_id`        | ID unik untuk setiap film.                                                   |
| `rating`         | Nilai rating yang diberikan pengguna untuk film (skala 1-5).                |
| `timestamp`      | Waktu ketika rating diberikan.                                               |

#### **Movies Data (`u.item`)**
| **Fitur**            | **Deskripsi**                                                            |
|-----------------------|-------------------------------------------------------------------------|
| `item_id`            | ID unik untuk setiap film.                                              |
| `title`              | Judul film.                                                             |
| `release_date`       | Tanggal rilis film.                                                     |
| `video_release_date` | Tanggal rilis video (opsional).                                         |
| `IMDb_URL`           | URL film pada IMDb.                                                     |
| `genre`              | Kolom biner yang merepresentasikan 19 genre film (seperti Action, Drama).|

#### **Users Data (`u.user`)**
| **Fitur**       | **Deskripsi**                                                                 |
|------------------|-------------------------------------------------------------------------------|
| `user_id`        | ID unik untuk setiap pengguna.                                               |
| `age`            | Usia pengguna.                                                              |
| `gender`         | Jenis kelamin pengguna (`M` untuk laki-laki, `F` untuk perempuan).           |
| `occupation`     | Pekerjaan pengguna.                                                         |
| `zip_code`       | Kode pos pengguna.                                                          |

---

### **Kesimpulan**
Dataset MovieLens 100k menyediakan data yang kaya untuk membangun sistem rekomendasi:
1. **Interaksi pengguna dengan film** (ratings) dapat digunakan untuk pendekatan Collaborative Filtering.
2. **Metadata film** (genre) sangat berguna untuk pendekatan Content-Based Filtering.
3. **Informasi demografis pengguna** dapat digunakan untuk analisis tambahan terkait preferensi pengguna.

### Mengapa Hanya Tiga File yang Di-load Langsung?

Dalam sistem rekomendasi, hanya tiga file utama yang di-load langsung (`u_data`, `u_item`, dan `u_user`) karena file-file tersebut berisi data yang paling sering digunakan untuk proses modeling dan evaluasi. File lainnya (`u_info`, `u_genre`, dan `u_occupation`) dianggap sebagai data pendukung yang digunakan untuk eksplorasi atau dokumentasi tambahan. Berikut adalah rincian perannya:

---

#### **File yang Di-load Langsung**

1. **`u_data`**  
   - **Tujuan**: Berisi informasi interaksi pengguna dengan film berupa `rating`, yang merupakan inti dari proses rekomendasi.  
   - **Kolom**:  
     - `user_id`: ID pengguna  
     - `item_id`: ID film  
     - `rating`: Nilai rating dari pengguna untuk film tertentu  
     - `timestamp`: Waktu interaksi  
   - **Mengapa di-load?**: 
     - Data ini adalah fondasi untuk Collaborative Filtering karena kita membutuhkan interaksi user-item.

2. **`u_item`**  
   - **Tujuan**: Berisi metadata tentang film, seperti judul, tanggal rilis, genre, dan lainnya.  
   - **Kolom**:  
     - `item_id`: ID film  
     - `title`: Judul film  
     - Genre (one-hot encoded)  
   - **Mengapa di-load?**:  
     - Data ini diperlukan untuk Content-Based Filtering, karena genre film digunakan untuk menghitung kesamaan antar film.

3. **`u_user`**  
   - **Tujuan**: Berisi informasi demografis pengguna, seperti usia, jenis kelamin, dan pekerjaan.  
   - **Kolom**:  
     - `user_id`: ID pengguna  
     - `age`: Usia pengguna  
     - `gender`: Jenis kelamin pengguna  
     - `occupation`: Pekerjaan pengguna  
     - `zip_code`: Kode pos pengguna  
   - **Mengapa di-load?**:  
     - Data ini digunakan untuk memahami demografi pengguna dan menganalisis pola interaksi dalam dataset.

---

#### **File Pendukung yang Di-load Secara Terpisah**

1. **`u_info`**  
   - **Tujuan**: Berisi informasi ringkasan tentang dataset, seperti jumlah pengguna, film, dan rating.  
   - **Mengapa tidak di-load langsung?**:  
     - File ini hanya berisi metadata statis, sehingga hanya digunakan untuk dokumentasi atau ringkasan analisis awal.

2. **`u_genre`**  
   - **Tujuan**: Berisi daftar genre yang tersedia di dataset beserta ID-nya.  
   - **Mengapa tidak di-load langsung?**:  
     - File ini hanya membantu memahami nama genre yang digunakan dalam kolom one-hot encoding di file `u_item`. Biasanya digunakan sekali saat eksplorasi.

3. **`u_occupation`**  
   - **Tujuan**: Berisi daftar pekerjaan pengguna yang tersedia di dataset.  
   - **Mengapa tidak di-load langsung?**:  
     - File ini hanya digunakan untuk referensi dalam analisis pekerjaan pengguna.

---

#### **Kesimpulan**
File **`u_data`**, **`u_item`**, dan **`u_user`** adalah data utama yang diperlukan untuk proses modeling dan evaluasi. Sedangkan file **`u_info`**, **`u_genre`**, dan **`u_occupation`** bersifat referensi pendukung, sehingga hanya di-load saat diperlukan untuk eksplorasi atau dokumentasi tambahan. Anda tetap bisa memuat semua file jika ingin eksplorasi yang lebih lengkap.


## **Exploratory Data Analysis (EDA)**

## **Distribusi Rating**
Distribusi rating menunjukkan bahwa sebagian besar pengguna memberikan rating di kisaran **3 hingga 5**, dengan rating **4** sebagai yang paling sering diberikan. Hal ini mengindikasikan adanya **bias positif** dalam dataset, di mana pengguna lebih cenderung memberikan rating tinggi daripada rendah.
![rating](https://github.com/user-attachments/assets/5c3b9cf7-6b3a-4826-9eab-385218a032e6)


### **Insight**:
- Rating **4** adalah yang paling banyak diberikan oleh pengguna.
- Rating **1** adalah yang paling jarang diberikan, menunjukkan pengguna jarang memberikan ulasan yang sangat negatif.

---

## **Top-10 Film dengan Rating Terbanyak**
Film yang mendapatkan jumlah rating tertinggi dalam dataset adalah **"Toy Story (1995)"**, diikuti oleh **"Star Wars (1977)"** dan **"Fargo (1996)"**. Sebagian besar film yang populer dirilis pada tahun **1995-1997**, yang merupakan masa puncak popularitas film-film ini.

### **Insight**:
- Film **"Toy Story (1995)"** menerima jumlah rating tertinggi (583 rating).
- Film populer cenderung berasal dari genre dominan seperti **Drama**, **Comedy**, atau **Action**.

**Daftar Top-10 Film dengan Rating Terbanyak**:
| **Rank** | **Judul Film**           | **Jumlah Rating** |
|----------|--------------------------|-------------------|
| 1        | Toy Story (1995)         | 583               |
| 2        | Star Wars (1977)         | 509               |
| 3        | Fargo (1996)             | 508               |
| 4        | Independence Day (1996)  | 507               |
| 5        | Return of the Jedi (1983)| 485               |
| 6        | Contact (1997)           | 481               |
| 7        | English Patient, The (1996)| 478            |
| 8        | Scream (1996)            | 452               |
| 9        | Liar Liar (1997)         | 431               |
| 10       | Air Force One (1997)     | 429               |

---

## **Distribusi Film Berdasarkan Genre**
Sebagian besar film dalam dataset termasuk dalam genre **Drama**, diikuti oleh **Comedy** dan **Action**. Genre seperti **Western**, **Fantasy**, dan **Film-Noir** memiliki jumlah film yang lebih sedikit, sehingga mungkin kurang terwakili dalam analisis.
![berdasarkan genre](https://github.com/user-attachments/assets/ac3150bf-a6b1-485b-b0fb-2a46c453c508)


### **Insight**:
- Genre **Drama** adalah genre dominan, dengan lebih dari **700 film**.
- Genre **Comedy** dan **Action** juga cukup dominan, masing-masing memiliki lebih dari **400 film**.
- Genre dengan jumlah film yang sedikit seperti **Western** atau **Fantasy** mungkin mengalami kesulitan dalam menghasilkan rekomendasi yang relevan karena keterbatasan data.

---

## **Distribusi Usia Pengguna**
Sebagian besar pengguna dalam dataset berada pada kelompok usia **20 hingga 40 tahun**, dengan puncak pada usia **30 tahun**. Rentang usia di luar kelompok ini kurang terwakili dalam dataset.
![Usia Pengguna](https://github.com/user-attachments/assets/18f92997-7b03-43b3-8b04-0ade41b51cbb)


### **Insight**:
- Dataset ini kemungkinan besar mencerminkan preferensi pengguna dewasa muda, yang merupakan target demografi utama.
- Kelompok usia di luar **20-40 tahun** mungkin mengalami kurangnya akurasi rekomendasi karena jumlah interaksi yang lebih sedikit.

---

## **Kesimpulan**
1. **Bias Positif dalam Rating**: Sebagian besar rating berada di kisaran **3 hingga 5**, menunjukkan kecenderungan pengguna memberikan ulasan positif.
2. **Film Populer**: Film seperti **"Toy Story (1995)"** dan **"Star Wars (1977)"** mendominasi rating, menunjukkan preferensi terhadap film-film klasik populer.
3. **Genre Dominan**: **Drama**, **Comedy**, dan **Action** adalah genre yang paling banyak terwakili, sementara genre minor seperti **Fantasy** atau **Western** mungkin kurang relevan untuk rekomendasi.
4. **Demografi Pengguna**: Pengguna dewasa muda (20-40 tahun) adalah kelompok yang paling aktif dalam memberikan rating, sehingga sistem rekomendasi dapat diarahkan untuk kelompok ini.

Dataset ini memberikan dasar yang baik untuk membangun sistem rekomendasi menggunakan pendekatan **Content-Based Filtering** atau **Collaborative Filtering**.

# **Data Preparation**

## **Tahapan dan Analisis**

---

### **1. Mengecek Nilai Kosong**
Dataset diperiksa untuk mengetahui apakah terdapat nilai kosong (*missing values*). Jika ada, nilai kosong diisi sesuai kebutuhan:
- **0** untuk data numerik (seperti rating).
- String kosong (`''`) untuk data kategoris (seperti genre atau metadata).

#### **Hasil:**
- Dataset **Ratings**: Tidak ada nilai kosong.
- Dataset **Movies**: Terdapat nilai kosong di beberapa kolom metadata, yang diisi dengan string kosong (`''`).
- Dataset **Users**: Tidak ada nilai kosong.

#### **Alasan:**
Mengisi nilai kosong memastikan data dapat diproses tanpa gangguan atau error selama transformasi atau analisis.

---

### **2. Menghapus Data Duplikat**
Dataset diperiksa untuk melihat apakah ada data duplikat. Baris duplikat dihapus dari dataset.

#### **Hasil:**
- Dataset **Ratings**: Tidak ada duplikasi.
- Dataset **Movies**: Tidak ada duplikasi.
- Dataset **Users**: Tidak ada duplikasi.

#### **Alasan:**
Menghapus duplikasi penting untuk mencegah bias dalam analisis atau modeling.

---

### **3. Membuat Matriks User-Item**
Dataset **Ratings** digunakan untuk membangun **User-Item Matrix**, di mana:
- **Baris**: Mewakili ID pengguna.
- **Kolom**: Mewakili ID film.
- **Nilai**: Rating yang diberikan pengguna untuk film tertentu.
- Nilai kosong diisi dengan **0** untuk film yang belum dirating oleh pengguna.

#### **Hasil:**
Matriks **User-Item** berhasil dibuat dengan dimensi:
- **943 pengguna x 1682 film**.
- Nilai kosong digantikan dengan **0**.

#### **Alasan:**
- Matriks User-Item adalah struktur utama yang digunakan dalam algoritma **Collaborative Filtering**.
- Mengganti nilai kosong dengan **0** memastikan algoritma dapat beroperasi pada matriks tanpa error.

---

### **4. Menggabungkan Genre Menjadi String**
Kolom genre dalam dataset **Movies** awalnya dalam format one-hot encoding. Untuk **Content-Based Filtering**, genre digabung menjadi satu string deskriptif di kolom baru bernama `genre_combined`.

#### **Hasil:**
Kolom baru `genre_combined` berhasil dibuat, berisi deskripsi genre setiap film. Contoh:
- **Film**: Toy Story (1995) → **Genre Combined**: Animation Children Comedy.

#### **Alasan:**
Pendekatan **Content-Based Filtering** membutuhkan deskripsi genre dalam format string untuk menghitung kesamaan antar film.

---

### **5. Representasi TF-IDF untuk Genre**
Kolom `genre_combined` direpresentasikan dalam format numerik menggunakan metode **TF-IDF (Term Frequency-Inverse Document Frequency)**. 
- **TF-IDF** mengubah teks (deskripsi genre) menjadi vektor angka yang merepresentasikan kepentingan relatif dari genre dalam dataset.

#### **Hasil:**
TF-IDF menghasilkan matriks fitur genre dengan ukuran:
- **1682 film x N fitur** (jumlah fitur tergantung pada jumlah unik kata dalam genre).

#### **Alasan:**
- Representasi numerik ini digunakan untuk menghitung **Cosine Similarity** antar film dalam pendekatan Content-Based Filtering.
- TF-IDF membantu menangkap relevansi genre yang lebih signifikan dibandingkan sekadar one-hot encoding.

---

### **6. Normalisasi Matriks User-Item**
Matriks User-Item dinormalisasi dengan cara:
- Mengurangi rata-rata rating setiap pengguna dari setiap nilai rating mereka dalam matriks.
- Nilai normalisasi dihitung untuk setiap pengguna secara independen.

#### **Hasil:**
Matriks normalisasi memiliki nilai rata-rata 0 untuk setiap pengguna.

#### **Alasan:**
Normalisasi membantu mengurangi bias pengguna yang mungkin selalu memberikan rating terlalu tinggi atau terlalu rendah. Hal ini meningkatkan performa algoritma Collaborative Filtering.

---

### **7. Visualisasi Distribusi Data**
Distribusi data rating dan genre divisualisasikan untuk memahami pola interaksi pengguna dan genre populer:
- **Distribusi Rating**: Menampilkan frekuensi rating (1-5) dari pengguna.
- **Distribusi Genre**: Menampilkan jumlah film dalam setiap genre.

#### **Hasil:**
- Distribusi rating menunjukkan sebagian besar pengguna memberikan rating di rentang 3-4.
- Genre **Drama**, **Comedy**, dan **Action** adalah yang paling banyak muncul.

#### **Alasan:**
Visualisasi membantu memahami pola dalam dataset dan memandu langkah modeling berikutnya.

---

### **Kesimpulan**
Tahapan data preparation telah dilakukan secara lengkap dan terstruktur:
1. Mengecek nilai kosong.
2. Menghapus data duplikat.
3. Membuat matriks User-Item.
4. Menggabungkan genre menjadi string.
5. Membuat representasi TF-IDF untuk genre.
6. Normalisasi matriks User-Item.
7. Visualisasi distribusi data.
8. Menyimpan data yang sudah diproses.

Data ini siap digunakan untuk membangun model sistem rekomendasi dengan metode **Content-Based Filtering** dan **Collaborative Filtering**.

---

# **Modeling**

Pada tahap ini, dua pendekatan sistem rekomendasi diterapkan untuk menyelesaikan permasalahan. Kedua pendekatan tersebut adalah:
1. **Content-Based Filtering (CBF)**: Berdasarkan metadata film seperti genre.
2. **Collaborative Filtering (CF)**: Berdasarkan pola interaksi pengguna terhadap film.

---

## **1. Content-Based Filtering (CBF)**

### **Cara Kerja:**
Content-Based Filtering merekomendasikan film yang mirip dengan film yang telah disukai atau dirating tinggi oleh pengguna. Kesamaan antar film dihitung berdasarkan metadata seperti genre menggunakan teknik **TF-IDF** dan **Cosine Similarity**.

### **Proses:**
1. **Menggabungkan Metadata**: Informasi genre untuk setiap film digabungkan menjadi satu string.
2. **Menghitung Kesamaan**: Kesamaan antar film dihitung menggunakan Cosine Similarity berdasarkan representasi TF-IDF.
3. **Menyusun Rekomendasi**: Film dengan kePendekatan **Content-Based Filtering** merekomendasikan item kepada pengguna berdasarkan kesamaan antara item yang sudah disukai atau diberi rating tinggi dengan item lainnya. 
- Pada proyek ini, kesamaan antar film dihitung menggunakan **Cosine Similarity**, yang mengukur kesamaan vektor genre antar film.
  ![cosine](https://github.com/user-attachments/assets/11737944-dad7-4c23-b0a2-b4d8143ed647)
- **A** dan **B** adalah vektor representasi TF-IDF dari dua film.
- Nilai Cosine Similarity berkisar dari 0 (tidak mirip) hingga 1 (sangat mirip).samaan tertinggi dengan film yang dirating tinggi oleh pengguna direkomendasikan.

### **Hasil Rekomendasi**:
Sebagai contoh, untuk film **"Star Wars (1977)"**, berikut adalah rekomendasi yang dihasilkan:
![star](https://github.com/user-attachments/assets/b54d18e5-bc9d-4992-83c9-24159de3196e)

### **Langkah-Langkah Implementasi**
1. **TF-IDF Vectorization**:
   - Genre gabungan setiap film diubah menjadi representasi numerik menggunakan **TF-IDF Vectorizer**.
   - Parameter utama:
     - `min_df=1`: Kata harus muncul di setidaknya 1 dokumen.
     - `stop_words='english'`: Kata umum dalam bahasa Inggris diabaikan.
2. **Menghitung Kesamaan**:
   - Matriks TF-IDF digunakan untuk menghitung **Cosine Similarity** antar film.
   - Matriks ini memiliki dimensi \(N \times N\), di mana \(N\) adalah jumlah film.
3. **Rekomendasi**:
   - Berdasarkan input berupa judul film, sistem mencocokkan film tersebut dengan film lainnya berdasarkan skor Cosine Similarity.
   - Sistem memberikan daftar Top-N rekomendasi film yang paling mirip.

### **Parameter Model**
- **TF-IDF Vectorizer**:
  - `min_df=1`
  - `stop_words='english'`
- **Cosine Similarity**:
  - Tidak memerlukan parameter tambahan.

### **Kelebihan:**
- **Cold Start untuk Pengguna Baru**: Tidak memerlukan data interaksi pengguna.
- **Mudah Diimplementasikan**: Menggunakan metadata yang tersedia.
- **Independen terhadap Pengguna**: Rekomendasi hanya bergantung pada item.

### **Kekurangan:**
- **Keterbatasan Metadata**: Kualitas rekomendasi sangat bergantung pada kelengkapan metadata.
- **Kurangnya Personalisasi**: Tidak mempertimbangkan preferensi pengguna.
- **Over-Specialization**: Rekomendasi hanya mencakup item yang serupa, sehingga tidak memberikan variasi.

---

## **2. Collaborative Filtering (CF)**

### **Cara Kerja**
Pendekatan **Collaborative Filtering** merekomendasikan item kepada pengguna berdasarkan pola interaksi pengguna lain yang memiliki preferensi serupa. 
- Pada proyek ini, digunakan algoritma **Singular Value Decomposition (SVD)** untuk mendekomposisi matriks User-Item.
  ![svd](https://github.com/user-attachments/assets/54cd12d7-a170-4284-8ae8-120bbb02ab43)
- **R**: Matriks User-Item.
- **U**: Matriks pengguna-laten.
- **Σ**: Matriks diagonal dari nilai singular (latent factors).
- **V**: Matriks item-laten.

### **Proses:**
1. **Matriks Interaksi**: Membuat *User-Item Matrix* berdasarkan data interaksi pengguna.
2. **Dekomposisi Matriks**: Menggunakan teknik SVD untuk merepresentasikan hubungan antar pengguna dan film.
3. **Prediksi Rating**: Membuat prediksi rating untuk setiap pasangan pengguna-film.
4. **Menyusun Rekomendasi**: Film dengan prediksi rating tertinggi direkomendasikan.

### **Langkah-Langkah Implementasi**
1. **Matriks User-Item**:
   - Dibuat dari dataset rating dengan dimensi \(M \times N\), di mana \(M\) adalah jumlah pengguna, dan \(N\) adalah jumlah film.
2. **Normalisasi**:
   - Matriks dinormalisasi dengan mengurangi rata-rata rating setiap pengguna untuk mengurangi bias.
3. **Dekomposisi SVD**:
   - Matriks User-Item dinormalisasi dipecah menjadi tiga matriks:
     ![sig](https://github.com/user-attachments/assets/44f2edd2-db5f-4f07-bc64-e853eaab0c0e)
   - Parameter utama:
     - **Latent Factors (k)**: Menentukan jumlah dimensi fitur laten.
4. **Prediksi Rating**:
   - Matriks rating direkonstruksi menggunakan matriks hasil dekomposisi:
     ![pred](https://github.com/user-attachments/assets/ce2af530-1cb4-4db7-82c8-7b49853822ae)
   - Prediksi digunakan untuk merekomendasikan item yang belum dirating oleh pengguna.

### **Parameter Model**
- **Jumlah Latent Factors (k)**: 100.
- **Iterasi**: 20 (default pada library SVD).
- **Normalisasi**: Mengurangi rata-rata rating pengguna sebelum dekomposisi.

### **Hasil Rekomendasi**:
Sebagai contoh, untuk pengguna dengan ID **1**, berikut adalah rekomendasi yang dihasilkan:
![id1](https://github.com/user-attachments/assets/cafcef1a-4e1b-46c7-a452-d024b6cb105b)

### **Kelebihan:**
- **Personalisasi**: Rekomendasi berbasis preferensi pengguna.
- **Eksplorasi**: Dapat merekomendasikan item yang tidak serupa tetapi relevan.
- **Efektif untuk Data Besar**: Menggunakan pola dari data interaksi yang besar untuk hasil yang lebih baik.

### **Kekurangan:**
- **Cold Start Problem**: Tidak dapat merekomendasikan item untuk pengguna atau film baru.
- **Kompleksitas Komputasi**: Memerlukan komputasi yang tinggi untuk dekomposisi matriks.
- **Ketergantungan pada Data**: Performa menurun jika data interaksi pengguna-film sedikit.

---

## **Perbandingan Pendekatan**

| **Aspek**               | **Content-Based Filtering (CBF)**                        | **Collaborative Filtering (CF)**                    |
|--------------------------|---------------------------------------------------------|----------------------------------------------------|
| **Data yang Dibutuhkan** | Metadata film (genre, deskripsi, dll.)                  | Interaksi pengguna (rating, klik, dll.)            |
| **Pendekatan Utama**     | Mengukur kesamaan antar item                            | Mencari kesamaan antar pengguna                   |
| **Kelebihan**            | - Tidak memerlukan data pengguna<br>- Cocok untuk item baru | - Lebih personal<br>- Relevansi lebih tinggi      |
| **Kekurangan**           | - Tidak mempertimbangkan preferensi pengguna            | - Bergantung pada data interaksi<br>- Cold start issue |

---

## **Kesimpulan**

1. **Content-Based Filtering (CBF)**:
   - Cocok untuk kasus di mana metadata item tersedia tetapi data interaksi pengguna minim.
   - Berguna untuk menangani item baru (*cold start*).

2. **Collaborative Filtering (CF)**:
   - Cocok untuk rekomendasi berbasis pola interaksi pengguna, menghasilkan rekomendasi yang lebih personal.
   - Bergantung pada data interaksi, sehingga menghadapi masalah untuk pengguna atau item baru.

Kombinasi kedua pendekatan ini dapat memberikan hasil rekomendasi yang lebih optimal dan serbaguna dalam sistem rekomendasi.
# **Kombinasi kedua pendekatan**

Sistem rekomendasi telah diintegrasikan sehingga pengguna dapat memilih salah satu dari dua pendekatan:
1. **Content-Based Filtering (CBF)**: Rekomendasi berdasarkan film yang pengguna sukai.
2. **Collaborative Filtering (CF)**: Rekomendasi berdasarkan pola interaksi pengguna lain dengan preferensi serupa.

---

## **Contoh Hasil**
### **Input:**
- Pilihan metode: **Content-Based Filtering**
- Judul film: **"Star Wars (1977)"**

### **Output Rekomendasi:**
1. Return of the Jedi (1983)  
2. Empire Strikes Back, The (1980)  
3. Starship Troopers (1997)  
4. Independence Day (ID4) (1996)  
5. Mars Attacks! (1996)  
6. Stargate (1994)  
7. Jurassic Park (1993)  
8. Star Trek: First Contact (1996)  
9. Star Trek VI: The Undiscovered Country (1991)  
10. Star Trek: The Wrath of Khan (1982)  

---

## **Penjelasan**
### **1. Content-Based Filtering:**
Rekomendasi ini didasarkan pada kesamaan antar metadata film, seperti genre atau deskripsi. Dalam kasus ini:
- Sistem merekomendasikan film-film yang mirip dengan **"Star Wars (1977)"**.
- Contohnya adalah **"Return of the Jedi (1983)"** dan **"Empire Strikes Back, The (1980)"**, yang memiliki genre atau tema serupa.

### **2. Collaborative Filtering:**
Sebagai alternatif, sistem dapat memberikan rekomendasi berdasarkan pola interaksi pengguna lain dengan preferensi serupa. Dalam metode ini:
- Sistem memanfaatkan data rating pengguna lain untuk merekomendasikan film dengan skor prediksi tertinggi.

![kombinasi](https://github.com/user-attachments/assets/b17d83b7-6bdf-471d-8eeb-f2d86a3801aa)

---

## **Manfaat Integrasi**
1. **Fleksibilitas**:
   - **CBF** cocok untuk pengguna baru atau film baru yang belum memiliki banyak data interaksi.
   - **CF** memberikan rekomendasi yang lebih personal berdasarkan preferensi pengguna lain.
2. **Diversifikasi Rekomendasi**:
   - Sistem dapat memberikan rekomendasi berbasis metadata untuk item serupa.
   - Sistem juga dapat memberikan rekomendasi berbasis interaksi pengguna, yang lebih personal.
3. **Pengalaman Pengguna yang Lebih Baik**:
   - Dengan memberikan pilihan metode, sistem dapat melayani berbagai kebutuhan pengguna.

---

## **Kesimpulan**
Integrasi kedua metode ini memberikan fleksibilitas yang lebih besar kepada pengguna, memastikan bahwa sistem dapat memberikan rekomendasi yang relevan dalam berbagai skenario. 

- **Content-Based Filtering** memberikan rekomendasi berbasis metadata item, cocok untuk pengguna baru.
- **Collaborative Filtering** memberikan rekomendasi berbasis interaksi pengguna, cocok untuk menghasilkan rekomendasi yang personal.

Dengan menyediakan opsi kedua metode ini, sistem dapat menjadi lebih adaptif dan serbaguna, memberikan pengalaman pengguna yang lebih baik. 🚀

# **Evaluation**

Evaluasi dilakukan untuk mengukur performa sistem rekomendasi yang telah dibuat. Pada tahap ini, dua metrik evaluasi digunakan untuk menilai pendekatan **Content-Based Filtering** dan **Collaborative Filtering**:
1. **Root Mean Square Error (RMSE)**: Digunakan untuk mengukur kesalahan prediksi pada Collaborative Filtering.
2. **Precision@K**: Digunakan untuk mengukur kualitas rekomendasi pada Content-Based Filtering.

---

## **1. Root Mean Square Error (RMSE)**

### **Penjelasan:**
- RMSE digunakan untuk mengukur rata-rata kesalahan antara rating yang diprediksi oleh model dengan rating sebenarnya.
- Metrik ini cocok untuk **Collaborative Filtering**, di mana model mencoba memprediksi rating pengguna terhadap item yang belum dirating.

### **Formula RMSE**:
![rmse](https://github.com/user-attachments/assets/ad530f84-6cb8-41e0-9e97-06a5bfc57390)


### **Cara Kerja:**
1. Prediksi rating dihitung untuk setiap pasangan pengguna-film.
2. Selisih antara rating sebenarnya dan rating prediksi dihitung, lalu dikuadratkan.
3. Nilai rata-rata dari kesalahan kuadrat dihitung, kemudian diakarkan untuk mendapatkan RMSE.

### **Hasil Evaluasi:**
Setelah dilakukan optimasi terhadap parameter model:
- **RMSE untuk Collaborative Filtering**: **1.2383**

### **Interpretasi:**
- Nilai RMSE yang lebih kecil menunjukkan bahwa prediksi model lebih akurat.
- Dalam kasus ini, RMSE **1.2383** menunjukkan bahwa rata-rata kesalahan prediksi model adalah sekitar 1.23 rating poin.

---

## **2. Precision@K**

### **Penjelasan:**
- Precision@K digunakan untuk mengevaluasi kualitas rekomendasi dengan menghitung proporsi item yang relevan dalam daftar rekomendasi top-K.
- Metrik ini cocok untuk **Content-Based Filtering**, di mana tujuan utama adalah merekomendasikan item yang relevan berdasarkan metadata.

### **Formula Precision@K**:
![top](https://github.com/user-attachments/assets/0a6eb7bc-5886-4980-ba5f-14eb4a2eeb8b)

### **Cara Kerja:**
1. Daftar rekomendasi top-K untuk pengguna dihitung berdasarkan kesamaan metadata.
2. Item relevan dalam daftar dihitung (misalnya, film yang sudah dirating tinggi oleh pengguna sebelumnya).
3. Precision dihitung sebagai rasio antara jumlah item relevan dengan K.

### **Hasil Evaluasi:**
- **Precision@K untuk Content-Based Filtering**: **0.4000** (untuk \(K = 10\)).

### **Interpretasi:**
- Nilai **0.4000** berarti 40% dari rekomendasi dalam daftar top-10 adalah item relevan.
- Nilai ini cukup baik untuk sistem rekomendasi berbasis metadata.

---

## **Perbandingan Hasil Evaluasi**

| **Metrik**         | **Content-Based Filtering** | **Collaborative Filtering** |
|---------------------|-----------------------------|------------------------------|
| **RMSE**           | -                           | **1.2383**                   |
| **Precision@K**    | **0.4000**                  | -                            |

### **Kesimpulan**:
1. **Collaborative Filtering** menunjukkan performa yang baik dengan nilai RMSE **1.2383**, yang berarti model cukup akurat dalam memprediksi rating pengguna.
2. **Content-Based Filtering** memiliki precision **0.4000**, yang menunjukkan bahwa 40% rekomendasi dalam daftar top-10 adalah relevan.

---

## **Rekomendasi untuk Perbaikan**

1. **Content-Based Filtering**:
   - Tambahkan metadata lain, seperti deskripsi atau ulasan film, untuk meningkatkan relevansi rekomendasi.
   - Gunakan algoritma berbasis embedding seperti **Word2Vec** untuk representasi metadata yang lebih kompleks.

2. **Collaborative Filtering**:
   - Gunakan pendekatan **Hybrid Filtering** untuk menangani masalah *cold start* pada pengguna atau item baru.
   - Tambahkan parameter regularisasi untuk mengurangi overfitting pada data rating.

---

## **Kesimpulan Akhir**
Evaluasi menunjukkan bahwa kedua pendekatan memiliki kekuatan masing-masing:
- **Content-Based Filtering** cocok untuk memberikan rekomendasi berdasarkan metadata item.
- **Collaborative Filtering** lebih efektif dalam memberikan rekomendasi personal berbasis pola interaksi pengguna.

Kombinasi kedua pendekatan ini dapat memberikan sistem rekomendasi yang lebih adaptif dan akurat. 🚀





