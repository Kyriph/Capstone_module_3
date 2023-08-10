# Capstone_module_3 Hotel Cancelation

# **Bussiness Understanding** 

**Context**

Kita merupakan Data Scientist yang baru direkrut oleh perusahaan Hotel bintang 5. Tanggung jawab kita adalah untuk memprediksi kecenderungan pelanggan yang akan membatalkan pemesanan mereka di hotel kita atau tidak melalui fitur-fitur tertentu. Sebelum menunjuk kita sebagai Data Science, Hotel sering mengalami kerugian pendapatan karena pelanggan tiba-tiba membatalkan pemesanan kamar mereka sehingga kamar menjadi kosong dan tidak dapat ditempati oleh pelanggan lain.

**Problem Statement :**

Pembatalan dapat berdampak buruk pada hotel. Hilangnya pendapatan terjadi sebagai akibat dari kamar yang tidak terjual. No-show adalah pembatalan tanpa pemberitahuan.

Ketika sebuah hotel dihadapkan dengan pembatalan menit terakhir dan kemudian check-in menit terakhir, hotel tidak bisa berbuat banyak selain menjual kamar dengan harga yang jauh lebih rendah, jadi peluang untuk mendapatkan revenue yang maksimal sangat minim.

Dan kemudian, ada juga biaya penggunaan layanan Online Travel Agent (OTA) untuk check-in menit terakhir. Hotel harus membayar biaya tertentu kepada OTA karena OTA bertindak sebagai perantara mereka, sehingga menurunkan keuntungan.

Tetapi jika hotel tidak bergantung pada OTA atau tidak memiliki unduhan otomatis pemesanan dan pembatalan, maka waktu pemesanan dan pembatalan tinggi, dan lebih banyak waktu berarti biaya lebih tinggi.

**Goals :**

Bagaimana kita dapat memprediksi dan meminimalkan pembatalan pemesanan kamar oleh pelanggan sehingga hotel bisa mendapatkan keuntungan yang maksimal dan pendapatan tambahan dari Makanan dan Minuman dari pelanggan yang menginap di hotel, serta meningkatkan demand agar kamar hotel dapat terisi semua.

**Analytic Approach :**

Kita akan menganalisis faktor apa saja yang mempengaruhi pembatalan pemesanan kamar hotel dan menentukan pola pelanggan yang akan membatalkan pemesanan atau tidak.

Lalu kita akan coba untuk membangun model klasifikasi yang akan membantu perusahaan untuk dapat memprediksi probabilitas pelanggan yang akan membatalkan pesanannya atau tidak

**Metric Evaluation**

True-Positive : Kita memperkirakan bahwa pelanggan akan membatalkan pemesanan mereka dan ternyata benar mereka membatalkan pemesanannya
Konsekuensi: Kita dapat memaksimalkan keuntungan kita dengan mengisi kamar kita sepenuhnya, serta mendapatkan keuntungan tambahan dari layanan F&B.

False-Negative : Kita memperkirakan bahwa pelanggan tidak akan membatalkan pemesanan mereka dan ternyata mereka membatalkan pemesanan mereka
Konsekuensi: Kamar yang dibatalkan pelanggan akan tetap kosong dan hotel akan kehilangan keuntungan di kamar ini, sementara sebenarnya kita dapat mengisinya dengan pelanggan lain.

False Positive : Kita memperkirakan bahwa pelanggan akan membatalkan pemesanan mereka dan sebenarnya mereka tidak membatalkan pemesanan mereka
Konsekuensi: Kita akan kehilangan pelanggan,dan revenue yang di peroleh perusahaan akan berkurang karena kita salah memprediksi pelanggan yang berpotensial untuk menginap.

True-Negative : Kita memperkirakan bahwa pelanggan tidak akan membatalkan pemesanan mereka dan sebenarnya mereka tidak membatalkan pemesanan mereka
Konsekuensi: Mayoritas karakteristik pelanggan yang memesan kamar hotel.


## **Conclution**
- Diketahui hasil dari hyperparameter tuning bahwa parameter terbaik yang dapat digunakan dengan benchmark **model Ada boost** adalah :
                - **model__n_estimators: 219**
                - **model__learning_rate: 0.05**
                - **model__algorithm: 'SAMME'**
                
- Berdasarkan dari pemodelan yang sudah dilakukan , feature `customer_type_transient`, dan `required_parking_space` menjadi feature yang paling berpengaruh terhadap Target
- Metric evaluasi yang digunakan pada model ini adalah recall score. Jika dilihat bahwa hasilnya adalah 1 itu menandakan bahwa model ini berhasil membaca bahwa jumlah calon pelanggan tidak akan membatalkan pemesanan mereka dan ternyata mereka membatalkan pemesanan mereka menjadi 0.

## **Recomendation**

- Sebaiknya cancellation policy hotel bisa lebih di perketat lagi agar para customer tidak seenaknya untuk melakukan pembatalan.
- Jika ada pelanggan yang membatalkan pemesanan kamar, sebaiknya pihak hotel langsung follow up ke pelanggan lain bahwa ada kamar kosong yang bisa di pesan agar perusahaan tidak kehilangan pendapatan.
- Pihak perusahaan juga dapat melakukan diskon terhadap kamar tertentu karena para pelanggan pasti cenderung memilih kamar yang termurah
- Menambahkan kolom price per room agar kita bisa mengetahui tipe room apa aja yang paling banyak di cancel agar kita bisa menyusun strategi bisnis dan marketing yang baik
- Kebijakan seperti apa yang perusahaan gunakan agar kita bisa menganalisa lebih lanjut mengenai turun naiknya revenue perusahaan
- Model Machine Learning ini tidak disarankan jika demand terhadap hotel rendah, dikarenakan nanti kita akan cenderung menolak pelanggan yang berpotensial untuk menginap.

