# Olist-Data-Wrangling

## Pendahuluan
Lalu-lintas data pada perusahaan E-Commerce termasuk yang cukup padat. Pada skala besar, perusahaan Amazon contohnya dapat melakukan 1,6 juta transaksi dalam sehari. Tentunya ini adalah ladang data sangat banyak dan berharga yang dapat digunakan untuk penentuan pengembangan bisnis kedepannya.

E-Commerce Olist yang berbasis di Brazil juga memiliki hal yang serupa. Frekuensi transaksi harian yang besar maupun banyaknya data yang bisa di mining membuat peluang penelitian dan pengembangan perusahaan menjadi eksponensial. Dalam report kali ini, saya akan berusaha untuk memberikan beberapa insight yang berasal dari pengolahan data yang ada di database yang dimiliki oleh Olist.

Harapannya report ini dapat menjadi tambahan pertimbangan kepada perusahaan terkait keputusan bisnis yang akan dijalankan kedepannya. Juga menambah wawasan dan mengasah kemampuan saya dalam mengolah data mentah yang sifatnya masih berantakan dan "kotor".

## Objektif
Report ini berusaha menjawab dan menjelaskan pertanyaan-pertanyaan dibawah ini
1. Perusahaan ingin mengkaji kemungkinan pengembangan lini bisnis logistik memanfaatkan pola belanja dari customer saat ini. Untuk itu perusahaan perlu untuk mengetahui:
    - Jumlah transaksi setiap bulannya
    - Total transaksi keseluruhan

  Adapun, perusahaan mempertimbangkan lini bisnis diantara Otomotif, Perlengkapan Bayi, Minuman, Elektronik, Makanan, Perkakas Rumah, Alat Musik, Alat Tulis Kantor dan     Mainan Anak sebagai pilot project awal.

2. Perusahaan ingin menelaah transaksi yang terjadi berdasarkan States (Provinsi). Yang mana akan dijadikan landasan dalam mengembangkan lini bisnis ekspedisi.
3. Perusahaan ingin melihat kelengkapan review berdasarkan kategori barang. Kategori barang dengan kelengkapan review rendah akan menjadi target dalam A/B testing campaign “Review for freebies”.

## Sumber Data
Data berasal dari database Olist yang telah dipublikasikan di Internet. Data tersebut memiliki tabel-tabel sebagai berikut:
![image](https://user-images.githubusercontent.com/59790033/205489493-4454a799-1ee3-4aa4-8f68-a726a5c08554.png)

## Hasil Analisa
- **Objective 1**

Jumlah transaksi dari setiap kategori ditampilkan pada tabel dan grafik berikut:
![image](https://user-images.githubusercontent.com/59790033/205489938-868caf45-cbaa-4b2b-8052-90c2c75ca452.png)
![image](https://user-images.githubusercontent.com/59790033/205489962-57949c74-c839-4d71-98fb-b687d20d3b93.png)
Grafik menunjukkan adanya siklus tahunan pada mayoritas kategori. Dimana pada bulan September frekuensi transaksi turun cukup drastis dan mengalami peningkatan yang tidak signifikan hingga akhir tahun. Namun untuk kategori perlengkapan bayi (baby), tidak ditemukan penurunan drastis di bulan September, malah puncak frekuensi transaksi terjadi di bulan November diikuti Desember. Hal ini bisa jadi dikarenakan kebutuhan akan perlengkapan bayi adalah kebutuhan yang terus menerus sehingga frekuensi transaksi tidak mengalami fluktuasi yang tajam.

Adapun dari segi nilai $ keseluruhan transaksi, urutannya adalah sebagai berikut:

![image](https://user-images.githubusercontent.com/59790033/205490281-4540d7d0-0e33-4a60-87d0-7e04635910f4.png)

Perkakas rumah tangga (houseware) menjadi kategori dengan nilai transaksi terbesar diikuti Otomotif (auto) dan mainan (toys). Sementara perlengkapan bayi berada di urutan keempat. 
Berdasarkan faktor fluktuasi dan nilai transaksi, saya merekomendasikan lini bisnis perlengkapan bayi untuk dijadikan pilihan perusahaan. Dengan demand yang relatif stabil dan nilai transaksi >$500.000 dalam setahun dapat menjadikan ini sebuah pilihan yang relatif lebih aman dibanding yang lain.

- **Objective 2**

Dalam menganalisa lokasi, saya membagi pertimbangan kedalam 2 kategori, yaitu total frekuensi transaksi dan nilai per transaksi. Apabila kita mempertimbangkan total frekuensi transaksi, maka tabel dibawah ini perlu dianalisa lebih lanjut:

Top 5 State dalam frekuensi pembelian:
![image](https://user-images.githubusercontent.com/59790033/205490894-22627644-4e3c-411b-b492-f74570ac2e39.png)

Top 5 State dalam frekuensi penjualan:
![image](https://user-images.githubusercontent.com/59790033/205490919-22e7c830-0950-4f7e-8c31-0365468f9f53.png)

Dapat terlihat bahwa State SP (Sao Paulo) memiliki traffic pembelian dan penjualan yang sangat tinggi, hampir 3 kali lipat daripada State RJ yang ada di peringkat 2. Dengan pertimbangan ini, maka apabila perusahaan ingin menjalankan bisnis ekspedisi, maka State SP dapat dijadikan Hub Central yang mampu mengelola arus pengiriman yang banyak. Sementara pada State yang lain, perusahaan hanya perlu membuka cabang yang lebih kecil untuk efisiensi.


- **Objective 3**

Pemetaan review dilakukan dengan memperhitungkan kelengkapan daripada judul dan isi dari review yang diberikan customer. Sekilas data menunjukkan 42,3% dari pembelian memiliki teks review sementara untuk judul review hanya ditemukan pada 11,9% pembelian.

Dari sebaran tersebut, ketika dipetakan berdasarkan kategori produk, maka dapat ditemukan kategori produk dengan jumlah kelengkapan review paling sedikit sebagai berikut:

![image](https://user-images.githubusercontent.com/59790033/205491377-bc1dbbba-17de-46a5-a364-3b659b64ae2b.png)

Terlihat jelas dari kolom review completeness bahwa fashion olahraga dan fashion anak adalah dua kategori yang paling sedikit kelengkapan reviewnya. Maka apabila perusahaan ingin menjalankan campaign meningkatkan kelengkapan review, dua kategori tersebut dapat dipertimbangkan lebih awal.


## Rekomendasi
Dalam analisa yang telah dijalankan, masih terdapat berbagai ruang peningkatan untuk mencapai konklusi yang lebih baik. Misalnya pada objective 1 dapat dilakukan analsis lebih mendalam terhadap produk yang lebih spesifik dalam kategori yang ada. Pada objective 2 dapat dilakukan analisa trafik yang lebih mendalam dengan mentracking movement keluar masuk setiap state sehingga data yang didapat bukan summary in dan out tetapi arah daripada pergerakan trafik. Pada objective 3 perlu dianalisa frekuensi transaksi dari kategori produk, karena dalam testing diperlukan high volume agar hasil lebih cepat didapatkan.

## Penutup
Demikian analisa dipaparkan dengan ringkas dan to the point menyelesaikan objective yang disematkan. Tentunya proses analisa data yang 'kotor' menjadi insight membutuhkan perjalanan yang lebih panjang dibalik layar. Apabila anda tertarik untuk melihat proses dibalik layar maka anda dapat melihat raw file wrangling.ipynb dalam repository ini.

