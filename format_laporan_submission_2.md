# Laporan Proyek Machine Learning - Dede Husen
## Project Overview
![aa-monthyear-halloweenmovies2024-standard-hero-v1-600kb-2000x1125](https://github.com/user-attachments/assets/aa921fbf-6d09-4a7d-8fad-7fcf0030128b)
## Latar Belakang
Dalam era digital saat ini, industri hiburan mengalami transformasi besar melalui platform streaming seperti Amazon Prime Video. Dengan ribuan judul film dan acara televisi yang tersedia, pengguna sering kali mengalami kebingungan dalam memilih tontonan yang sesuai dengan preferensi mereka. Fenomena ini dikenal sebagai *information overload*, di mana terlalu banyak pilihan justru menyebabkan ketidakpastian dalam pengambilan keputusan [1].

Amazon Prime Video [2], sebagai salah satu penyedia layanan streaming terkemuka secara global, menghadapi tantangan dalam menjaga kepuasan pengguna dengan menyediakan **konten yang relevan dan personal**. Oleh karena itu, pengembangan sistem rekomendasi (*recommender system*) menjadi sangat penting untuk meningkatkan pengalaman pengguna, memperpanjang waktu menonton, serta meningkatkan loyalitas pelanggan.

## Mengapa Masalah Ini Perlu Diselesaikan

Masalah utama yang ingin diselesaikan dalam proyek ini adalah **ketidakmampuan pengguna dalam menemukan film atau acara TV yang sesuai dengan selera mereka secara efisien**. Berdasarkan riset oleh Gómez-Uribe dan Hunt, sistem rekomendasi memiliki kontribusi besar dalam meningkatkan retensi pengguna pada layanan streaming seperti Netflix — lebih dari 80% aktivitas menonton pengguna berasal dari hasil rekomendasi [3]. Ini menunjukkan bahwa sistem rekomendasi memiliki potensi besar untuk mendorong interaksi pengguna dan meningkatkan kepuasan layanan.

Dengan membangun sistem rekomendasi berbasis data untuk Amazon Prime Video, kita dapat membantu pengguna menemukan konten yang lebih relevan berdasarkan histori penilaian (rating), genre favorit, dan popularitas film. Hal ini juga berdampak pada bisnis, seperti meningkatkan *engagement*, mendorong monetisasi lebih tinggi, dan memperkuat daya saing layanan streaming dalam industri yang sangat kompetitif.

## Bagaimana Masalah Ini Akan Diselesaikan

Proyek ini akan mengimplementasikan *recommender system* menggunakan pendekatan berbasis konten (*content-based filtering*) dengan memanfaatkan data dari film dan TV show yang tersedia di platform Amazon Prime. Data tersebut mencakup informasi seperti genre, aktor, rating pengguna, tahun rilis, dan lain-lain.

Model yang dibangun akan memproses informasi tersebut untuk memberikan rekomendasi yang bersifat personal kepada pengguna, misalnya dengan merekomendasikan film sejenis dengan film yang sebelumnya disukai atau dinilai tinggi oleh pengguna. Dengan demikian, sistem ini akan berperan sebagai asisten cerdas dalam pengalaman menonton pengguna.

## Business Understanding
Pengembangan sistem rekomendasi pada platform streaming seperti Amazon Prime Video memainkan peran yang sangat penting dalam meningkatkan kualitas layanan dan pengalaman pengguna. Dengan jumlah konten yang terus bertambah, pengguna sering kali mengalami kesulitan dalam menemukan film atau acara TV yang sesuai dengan preferensi pribadi mereka. Sistem rekomendasi yang efektif dapat mengurangi waktu pencarian, meningkatkan kepuasan pengguna, serta mendorong mereka untuk terus menggunakan layanan secara berkala.

Tidak hanya bermanfaat bagi pengguna, sistem rekomendasi juga memberikan keuntungan strategis bagi platform. Rekomendasi yang relevan dapat meningkatkan tingkat keterlibatan (*engagement*), memperpanjang waktu menonton, dan pada akhirnya berdampak positif terhadap retensi pelanggan dan pendapatan platform. Hal ini telah dibuktikan oleh berbagai studi yang menunjukkan bahwa sebagian besar konten yang dikonsumsi pengguna berasal dari hasil sistem rekomendasi [4], [5].

Dengan memanfaatkan algoritma seperti *collaborative filtering*, *content-based filtering*, dan *K-Nearest Neighbors (KNN)*, sistem rekomendasi dapat mengolah data interaksi pengguna secara optimal untuk menghasilkan saran yang bersifat personal dan adaptif terhadap preferensi pengguna yang berubah dari waktu ke waktu.



### Program Statement
1. Pengguna kesulitan menemukan film atau acara TV yang sesuai dengan preferensi mereka karena banyaknya pilihan konten yang tersedia.
2. Sistem rekomendasi bawaan sering kali memberikan hasil yang tidak personal atau kurang relevan dengan minat pengguna.
3. Kurangnya pemanfaatan data historis pengguna, seperti rating atau genre favorit, dalam proses pemberian rekomendasi.

## Goals
Untuk menjawab pernyataan masalah di atas, proyek ini memiliki tujuan-tujuan sebagai berikut:

1. Mengembangkan sistem rekomendasi yang dapat membantu pengguna menemukan film atau acara TV yang sesuai dengan preferensi mereka secara otomatis sebanyak Top-N.
2. Meningkatkan relevansi rekomendasi dengan memanfaatkan metode berbasis konten (*content-based filtering*) dan/atau *collaborative filtering*.
3. Membuat model sistem rekomendasi Cosine Similarity dan K-Nearest Neighbor berdasarkan fitur yang telah dipilih dari dataset
4. Mengukur perfoma model sistem rekomendasi dengan menggunakan metrik evaluasiMenggunakan data historis seperti rating dan genre yang disukai untuk menghasilkan rekomendasi yang lebih akurat dan personal.

## Solution Approach

Untuk mencapai tujuan-tujuan tersebut, pendekatan solusi yang digunakan dalam proyek ini meliputi beberapa algoritma sistem rekomendasi yang telah terbukti efektif secara akademik dan praktis:

### Solution Statement 1: Content-Based Filtering
Pendekatan ini akan memanfaatkan metadata dari film dan acara TV seperti genre, tahun rilis, dan deskripsi untuk merekomendasikan item yang mirip dengan konten yang sebelumnya disukai oleh pengguna. Sistem ini bekerja dengan menghitung kesamaan antar item menggunakan metode seperti cosine similarity.

### Solution Statement 2: Collaborative Filtering
Menggunakan pendekatan berbasis pengguna atau item yang serupa dengan pengguna lainnya. Model ini tidak bergantung pada metadata film, tetapi pada interaksi antar pengguna dan item (misalnya: rating). Model berbasis matrix factorization seperti Singular Value Decomposition (SVD) akan digunakan untuk menemukan pola tersembunyi dari data rating.

### Solution Statement 3: K-Nearest Neighbors (KNN)
Algoritma KNN digunakan dalam pendekatan collaborative filtering untuk menemukan *k* pengguna atau item yang paling mirip dengan pengguna atau item target. Kemiripan dihitung menggunakan metrik seperti cosine similarity atau Pearson correlation. Pendekatan ini sangat efektif dalam memberikan rekomendasi berbasis kesamaan perilaku pengguna lain.


## Data Understanding
Amazon Prime adalah salah satu platform media dan streaming video yang paling populer didunia. platform ini  memiliki hampir 10.000 judul film dan acara TV yang tersedia di platform mereka. Hingga pertengahan tahun 2021, Amazon Prime memiliki lebih dari 200 juta pelanggan di seluruh dunia. Dataset ini terdiri dari 9668 baris data dengan 12 kolom diantaranya adalah kolom show_id, type, title, director, cast, country, date_added, release_year,rating, duration, listed_in & descripstion. Dataset ini bersumber dari repositori publik di kaggle (https://www.kaggle.com/datasets/shivamb/amazon-prime-movies-and-tv-shows/data) yang diungga oleh shival Banshal (https://www.kaggle.com/shivamb) 

Berikut detail dari dataset tersebut: 
| **Nama Kolom**   | **Tipe Data (Pandas)** | **Deskripsi**                                                                 |
|------------------|------------------------|-------------------------------------------------------------------------------|
| `show_id`        | object                 | ID unik untuk setiap entri film atau acara TV dalam dataset.                 |
| `type`           | object                 | Jenis konten, misalnya *Movie* atau *TV Show*.                               |
| `title`          | object                 | Judul dari film atau acara TV.                                               |
| `director`       | object                 | Nama sutradara dari film atau acara TV. Dapat kosong pada beberapa entri.    |
| `cast`           | object                 | Daftar aktor/aktris yang terlibat. Biasanya berupa string yang dipisah koma. |
| `country`        | object                 | Negara tempat produksi konten dilakukan. Banyak nilai kosong.                |
| `date_added`     | object                 | Tanggal konten ditambahkan ke Amazon Prime (belum dalam format datetime).   |
| `release_year`   | int64                  | Tahun rilis asli dari film atau acara TV.                                    |
| `rating`         | object                 | Klasifikasi usia (contoh: PG, R, TV-MA, dll.).                               |
| `duration`       | object                 | Durasi film (dalam menit) atau jumlah musim jika *TV Show*.                 |
| `listed_in`      | object                 | Genre atau kategori konten. Bisa lebih dari satu genre.                      |
| `description`    | object                 | Deskripsi singkat tentang konten.                                            |


## Exploratory Data Analisys

### Visualisasi Persentase Konten Movie dan TVshow
![image](https://github.com/user-attachments/assets/c66eb680-b599-43c2-932e-6046a58b0bc6)
Bisa lihat pada grafik diatas Jumlah konten Movie (80.8%) jauh lebih banyak dari konten TV Show (19.2%) 

### Distribusi Rating 
![image](https://github.com/user-attachments/assets/19230010-6322-4b80-b9ac-737866ef3406)
Dari grafik diatas kita dapat melihat bahwa rating konten movie dan tv show di dominasi oleh ratin 13+, 16+, 18+ dan R. akan tetapi terdapat beberapa rating yang sepertinya mempunyai kemiripan dan dapat disatukan.

### Top 10 Genre 
![image](https://github.com/user-attachments/assets/fba42371-ca91-4c48-8030-08fc1c09458b)
Konten dengan type Drama, komedi dan action menempati 3 besar konten yang di produksi dan dapat dikatakan 3 type inilah yang banyak disukai pengguna

### Distribusi rilis konten movie dan tv show dalam 20 tahun terakhir
![image](https://github.com/user-attachments/assets/e320385d-b7d1-4811-939d-bda0bac9b38d)
Dari chart diatas kita dapat melihat distribsusi konten yang di sajikan di platform amazon dalam 20 tahun terakhir meningkat terus menerus setiap tahunnya, dalam 3 tahun terakhir produksi konten movie memperlihatkan peningkatan  yang sangat siginifikan.  

## Data Preparation
Pada tahapan ini saya melakukan beberapa metode data preprocessing diantarannya adalah sebagai berikut: 
### Data Cleaning 
- Cek Duplikasi Data
   - ![image](https://github.com/user-attachments/assets/66a1ba56-b153-4b7e-9e6f-3e88a8465ced)
   - hasil dari cek duplikasi data tidak terdapat duplikasi data

- cek missing value
  ![image](https://github.com/user-attachments/assets/724d8904-ab91-4aa9-bb8f-dcd08b780971)
![image](https://github.com/user-attachments/assets/32087f4d-be13-4638-acee-09acab44f0b5)
Hasil dari pengecekan diatas kita dapat melihat persentase missing value pada beberapa fitur, berikut persentase dan perlakuan yang akan dilakukan terhadap fitur tersebut 
1. director (21.5%)
 - fitur ini dapat dijadikan bagian dari sistem rekomendasi.
 - nilai yang kosong akan diisi dengan kata "*unknown*"

2. Cast (kosong 12.7%)
 - bisa dijadikan fitur untuk rekomendasi juga
 - nilai kosong akan di isi dengan kata "*unknown*"
3. Country (kosong 93%)
 - karna hampir seluruh baris datanya kosong, saya akan menghapus kolom ini)

4. date_added (kosong 98%)
  -  hampir seluruhnya kosong, kita akan menghapus data ini)

5. rating(kosong 3.5%)
   - kita akan menghapus yang mempunyai nlai kosong

Berikut hasil dari perlakuan data diatas: 
![image](https://github.com/user-attachments/assets/bb9f169f-6ef0-43c1-9998-687028e78218)
bisa kita lihat, kita telah menangani missing value, dan semua data terisi

### Menyeragamkan value rating
![image](https://github.com/user-attachments/assets/d94f9537-7813-43c3-abae-ec09e9393bb9)
kita bisa liat nilai dalam rating terdapat nilai  yang sama, ini juga terllihat dalam grafik rating diatas. sebagai contoh rating 16 dan AGES_16_ itu adalah sama. maka saya akan menyeragamkan itu.
![image](https://github.com/user-attachments/assets/14fa1f87-8d10-468d-9828-5a7c0d918978)
Kita bisa lihat hasil penyeragaman rating dalam kotak merah diatas.

### Menghapus fitur yang tidak digunakan 
dalam kasus rekomender system ini kita perlu mengeliminasi kolom-kolom yang tidak diperlukan yaitu kolom show_id, release_yaear dan duration sehingga hasil akhir sebelum modeling data frame yang akan dioleh adalah sebagai berikut: 
![image](https://github.com/user-attachments/assets/cbff9f62-e25c-478f-926e-a20438256a15)

### Pembuatan fitur gabungan (combined_features)
Proses ini merupakan strategi dalam sistem rekomendasi berbasis konten (Content-Based Filtering). Tujuan dari penggabungan ini adalah untuk membentuk representasi deskriptif dari setiap item (film atau acara TV) dalam satu string yang bisa diproses pada tahapan selajutnya yaitu TF-IDF atau CountVectorizer. dalam kasus ini fitur yang akan digabungkan adalah _director, cast, listed_in, description_ dan _title_ yang akan di simpan dalam ftur baru  yaitu _combined_features_. Berikut hasil penggabungan fitur tersebut: 
![image](https://github.com/user-attachments/assets/cca40324-729d-45e5-9308-09eaad8b429b)


### TF-IDF vectorization
Tahap ini adalah dalam proses data preparation dimana TF-ID sendiri adalah kependekan dari _Term Frequency-Inverse Document Frequency_ yang merupakan  metode statistik yang digunakan untuk mengevaluasi seberapa penting sebuah kata dalam dokumen relatif terhadap kumpulan dokumen. TF mengukur seberapa sering sebuah kata muncul dalam dokumen, sedangkan inverse dokumen adalah mengukur seberapa jarang sebuah kata dalam sebuah dokumen.
Dalam kasus ini saya akan melakukan proses TF-IDF ke dalam fitur gabungan baru yaitu _conmbined_features_.  


### CountVectorizer
Pada tahap ini, kita menggunakan _CountVectorizer_ untuk mengubah teks pada kolom _combined_features _menjadi bentuk vektor numerik. Kita juga menghilangkan kata-kata umum dalam bahasa Inggris _(stop words)_ agar hasil lebih fokus pada kata-kata penting yang merepresentasikan konten film.

## Modeling

pada tahapan modeling, saya melakukan 2 jenis teknik modelling: 

### 1. Cosine Similiriarity

**Cosine Similarity** adalah ukuran kesamaan antara dua vektor dalam ruang fitur berdimensi tinggi yang dihitung berdasarkan **sudut kosinus** di antara keduanya. Dalam konteks **sistem rekomendasi berbasis konten (Content-Based Filtering)**, cosine similarity digunakan untuk mengukur sejauh mana dua item (misalnya, film atau acara TV) serupa berdasarkan atribut konten yang telah direpresentasikan sebagai vektor teks (misalnya melalui TF-IDF).
Semakin kecil sudut antara dua vektor, semakin besar nilai cosine similarity-nya (mendekati 1), yang berarti semakin mirip kedua item tersebut.

![image](https://github.com/user-attachments/assets/eeeabd2b-aa53-46b0-9f8f-7dbc6a8d4f70)


Nilai hasil cosine similarity berkisar antara:
- **0** = tidak mirip sama sekali (sudut 90°)
- **1** = identik (sudut 0°)

#### Penerapan dalam Sistem Rekomendasi
Dalam sistem rekomendasi:
- Setiap item (misalnya film) direpresentasikan sebagai vektor (biasanya menggunakan TF-IDF).
- Kemudian cosine similarity digunakan untuk menghitung seberapa mirip satu item dengan item lain.
- Item-item yang memiliki nilai similarity tertinggi akan direkomendasikan kepada pengguna.

berikut hasil penerapan model dengan teknik cosine similarity
```python
content_based_recommendations("Maradona: Blessed Dream")
```
hasilnya: 
![image](https://github.com/user-attachments/assets/7c6c0f84-4dbf-43bd-9af1-034dfd99a1ba)



### 2. K-Nearest Neighbor (KNN) 
K-Nearest Neighbor (KNN) merupakan salah satu algoritma yang paling sederhana dalam proses klasifikasi data. Prinsip kerjanya mudah dipahami, yakni dengan menentukan kelompok suatu data berdasarkan kedekatannya dengan data lain di sekitarnya. Dalam penerapannya, algoritma ini mempertimbangkan sejumlah data tetangga terdekat—yang jumlahnya ditentukan oleh nilai parameter K—untuk memprediksi kelas atau label data yang belum diketahui. Jika K=1, maka hanya satu data terdekat yang dijadikan acuan untuk menentukan kelas dari data tersebut.
Berikut Rumus K-Nearest Neighbor :

 $$Euclidean Distance (P, Q) = sqrt(∑(Pi - Qi)^2)$$

dimana:
- Pi mewakili fitur ke-i dari titik data P.
- Qi mewakili fitur ke-i dari titik data Q (titik data dari kumpulan data D).
- ∑ merupakan simbol penjumlahan pada semua fitur titik data.


Berikut hasil dari model rekomendasi menggunakan model KNN 
![image](https://github.com/user-attachments/assets/fb73acb7-6b70-49c7-90cb-a7bfe11c0d4e)

### 📊 Perbandingan Content-Based Filtering dan K-Nearest Neighbors (KNN) dalam Konteks Amazon Prime Video

| Aspek                         | Content-Based Filtering (Cosine Similarity)                                        | K-Nearest Neighbors (KNN)                                                         |
|------------------------------|-------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------|
| **Jenis Rekomendasi**        | Berdasarkan kemiripan konten (judul, genre, deskripsi, direktur, aktor, dll.)      | Berdasarkan kedekatan antar item atau pengguna dalam ruang fitur                  |
| **Contoh Penerapan**         | Menyarankan film dengan genre dan deskripsi mirip dengan film yang pernah ditonton | Mencari film terdekat (berdasarkan fitur) dari film yang baru saja ditonton      |
| **Kelebihan**                | Personalisasi tinggi, cocok untuk pengguna baru, tetap bekerja tanpa rating        | Sederhana, dapat digunakan untuk user-based dan item-based filtering              |
| **Kekurangan**               | Rentan filter bubble, tergantung kualitas metadata                                 | Tidak efisien untuk dataset besar seperti Amazon Prime (~10.000+ film/show)       |
| **Masalah Cold Start**       | Bisa menangani item baru (selama metadata tersedia)                                | Sulit menangani item atau user baru jika tidak ada cukup tetangga                 |
| **Skalabilitas**             | Relatif baik jika dikombinasikan dengan indexing (misal: TF-IDF + Cosine)          | Buruk untuk data besar, karena butuh menghitung jarak ke semua item/user          |
| **Kecepatan Prediksi**       | Cepat setelah vektor fitur dibuat                                                  | Lambat karena harus menghitung jarak ke semua tetangga secara langsung            |
| **Ketergantungan pada Data** | Bergantung pada fitur konten                                                       | Bergantung pada struktur tetangga dalam ruang fitur                               |


## Evaluation

### 1. Content Based Filterig dengan Cosine Similarity
Cosine similarity menunjukkan kemiripan arah antara dua vektor teks, bukan panjangnya. Nilainya berada di antara -1 hingga 1: 
Rumus Cosine Similarity

![image](https://github.com/user-attachments/assets/79f0d3d0-0f2e-4a20-baf5-bbb64bd26375)


### Nilai Cosine Similarity:

- `1` : Sangat mirip (arah vektor sama)
- `0` : Tidak mirip sama sekali (arah tegak lurus)
- `-1` : Berlawanan arah (jarang terjadi dalam konteks teks)

Beriut hasil dari penghitungan nilai kemiripan dengan cosine similrarity
![image](https://github.com/user-attachments/assets/8384eba9-c662-4134-abe9-b24c7979e58e)
Berdasarkan hasil perhitungn diatas kita dapat melihat nilai dari setiap rekomendasi yang diberikan di susun berdasarkan nilai dari score similariti nya, dimana triassic Hunt,virus, The Z Virus, dan  'Virus' mempunyai score kemiripan tinggi.
berikut score similarity untuk setiap rekoendasinya
![image](https://github.com/user-attachments/assets/de902b65-a881-4a82-9268-e47b4b198587)



### 2. Evaluasi Model KNN dengan Precisiion
Metrik evaluasi yang digunakan pada konteks rekomender sistem ini adalah dengan menggunakan precision, Precision adalah rasio antara jumlah item relevan yang berhasil diprediksi terhadap jumlah total item yang diprediksi sebagai relevan. dimana 
rumus precision adalah sebagai berikut: 
![image](https://github.com/user-attachments/assets/860794d4-ddce-4e9d-9b4e-53a3eb17145e)

Keterangan:
- **True Positive (TP):** Item yang relevan dan berhasil direkomendasikan/diprediksi dengan benar
- **False Positive (FP):** Item yang tidak relevan tapi tetap dimasukkan dalam hasil rekomendasi

Berikut hasil evaluasi dari model  knn
![image](https://github.com/user-attachments/assets/12bd4aed-4f79-4d31-9137-e045a49c2dd4)


![image](https://github.com/user-attachments/assets/5ef9d32e-ca97-43fd-b8d8-3d0bb344f022)

-  Hasil dari rekomendasu dari dari model knn tersebut terdapat nilai True Positif (TP) =4 dan False Posisitif (FP) = 1, sehingga kita dapat menghitung nilai presisi sebagai berikut:

Precisision = 4/(4+1) = 4/5 = 0.8 = 80%

Berarti nilai dari presisi dari model KKN tersebut adalah 80%





#Referensi
1.  Bawden, D., & Robinson, L. (2009). The dark side of information: Overload, anxiety and other paradoxes and pathologies. Journal of Information Science, 35(2), 180–191. https://doi.org/10.1177/0165551508095781

2. Amazon Prime Video. (2023). About Prime Video. [Online]. Available: https://www.primevideo.com/

3. Gómez-Uribe, C. A., & Hunt, N. (2015). The Netflix Recommender System: Algorithms, Business Value, and Innovation. ACM Transactions on Management Information Systems (TMIS), 6(4), 13. https://doi.org/10.1145/2843948

4. C. A. Gómez-Uribe and N. Hunt, "The Netflix Recommender System: Algorithms, Business Value, and Innovation," *ACM Transactions on Management Information Systems (TMIS)*, vol. 6, no. 4, pp. 1–19, Dec. 2015. doi:10.1145/2843948

5. F. Ricci, L. Rokach, and B. Shapira, "Recommender Systems Handbook," 2nd ed., Springer, 2015.

6.  D. Jannach, M. Jugovac, "Measuring the business value of recommender systems," *ACM Transactions on Management Information Systems (TMIS)*, vol. 10, no. 4, pp. 1–23, 2019. doi:10.1145/3309540

7. H. Chen, X. Zhou, and G. Wang, "Recommender Systems for Streaming Services: Challenges and Research Opportunities," *IEEE Access*, vol. 9, pp. 127984–127998, 2021. doi:10.1109/ACCESS.2021.3112135

8. Asep Maulana Ismail. (2018). Cara Kerja Algoritma k-Nearest Neighbor (k-NN). Published in Bee Solution Partners. Tersedia: [tautan.](https://medium.com/bee-solution-partners/cara-kerja-algoritma-k-nearest-neighbor-k-nn-389297de543e) 

