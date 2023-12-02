# Unsupervised Learning Clustering
Data set : Kendaraaan

## Formulasi Masalah
Task : Tugas untuk unsupervised learning adalah memprediksi apakah pelanggan tertarik untuk membeli kendaraan baru atau tidak berdasarkan data pelanggan di dealer.

## Explorasi dan Persiapan Data
Clustering dilakukan dengan menggunakan algoritma K-Nearest Neighbors (K-NN). Secara singkat algoritma ini membuat cluster dengan anggotanya merupakan yang terdekat dari salah satu sampel tengah yang biasa disebut centroid.
Terdapat dua data yang akan digunakan pada penelitian kali ini, datanya sebagai berikut;
a. kendaraan_train.csv 
b. kendaraan_test.csv

Beberapa langkah yang harus dilakukan untuk mempersiapkan data, antara lain;
1. Menghapus data dengan value NaN/Kosong, data tersebut dihapus karena merupakan noise yang akan mengganggu model saat belajar.
2. Merubah data kategorikal seperti Jenis_Kelamin, Umur_Kendaraan, dan Kendaraan_Rusak menjadi data numerikal. Hal ini diperlukan karena model tidak bisa membaca tipe data string.
3. Data dengan beberapa fitur tersebut kemudian diubah ke bentuk Principal component analysis (PCA), hal ini dilakukan agar mengefesiensikan proses clustering, dan juga agar bisa divisualisasikan.

 ## Pemodelan
Algoritma yang dipakai untuk clustering adalah K-Nearest Neighbors. Karena task dari rancangan ini adalah untuk memprediksi apakah pelanggan tertarik atau tidak, maka dibutuhkan label dengan value 0 dan 1. Maka dari itu jumlah cluster yang dibutuhkan adalah k=2.
Hasil dari algoritma tersebut adalah 2 centroid yang merupakan titik tengah dari 2 cluster yang ada.

 ## Evaluasi
Hasil dari model K-NNyang dibuat adalah 2 centroid sebagai berikut

<img width="646" alt="Screenshot 2023-12-02 at 12 58 57" src="https://github.com/athirahrifdha/Unsupervised-Learning-Clustering-/assets/139842516/d876f957-a30d-42c6-8a45-f48e0c2ac450">

Centroid tersebut digunakan untuk mencari tetangga terdekat dari titik tersebut ke data train yang ada, secara visual akan terlihat seperti gambar di samping.

<img width="449" alt="Screenshot 2023-12-02 at 12 59 45" src="https://github.com/athirahrifdha/Unsupervised-Learning-Clustering-/assets/139842516/37dd52c6-d01c-4eb5-9e24-e9bd9f909de0">

Dengan demikian didapatkan akurasi label prediksinya adalah 0.7360640213248533.
Centroid yang didapatkan dari pelatihan model pada data train digunakan ke data test. Data test ini sudah dilakukan preprocess sama seperti data train. Centroid yang diterapkan ke data test akan terlihat seperti di bawah;

<img width="494" alt="Screenshot 2023-12-02 at 13 00 30" src="https://github.com/athirahrifdha/Unsupervised-Learning-Clustering-/assets/139842516/d6da3c5d-6e06-4b42-9adc-4be16c82b6e6">

Hasil akurasi dari prediksi data test adalah 0.7364554251768509

 ## Eksperimen
Dilakukan 2 percobaan untuk melatih model K-NN. percobaannya adalah;
1. Melatih model menggunakan dataset PCA
2. Melatih model menggunakan dataset asli tanpa PCA
Setelah dilakukan 2 percobaan tersebut, model menghasilkan akurasi yang
sama pada kedua percobaan, namun waktu yang dibutuhkan untuk mencari centroid final, dataset PCA lebih cepat diproses. Hal ini dikarenakan PCA mengurangi dimensi dataset menjadi lebih kecil, sehingga model bisa lebih cepat memproses data.

    ## Kesimpulan
Principal component analysis (PCA) merupakan teknik mereduksi dimensi data yang mampu mempercepat proses algoritma K-NN.
Hasil dari evaluasi centroid terhadap data train dan data test sebagai berikut;
a. Data train: 0.7360640213248533
b. Data test: 0.7364554251768509
Akurasi yang didapatkan tidak terlalu berbeda.
