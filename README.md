# DeltaGroup_JC_DS_FT_JKT_19_FinalProject

# Dashboard
Google Looker Studio: https://lookerstudio.google.com/reporting/e19a8dff-8f8f-4cf3-bb56-c8f1e8437fad

# Business Understanding

### Konteks  

Olist merupakan sebuah perusahaan E-Commerce yang dapat dikatakan baru beroperasi, dan dalam konteks ini kami sebagai seorang Data Scientist diberikan tugas untuk mengumpulkan informasi terkait karakteristik dari customer agar dapat menghasilkan strategi marketing yang tepat. Tahapan awal yang dapat dilakukan adalah dengan mengumpulkan data pelanggan yang dapat digunakan seperti demografi, histori pembelian, perilaku pembelian, dan lainnya. Data yang sudah terkumpul dapat dilakukan analisa dengan berbagai terknik seperti customer segmentation, clustering dan lain-nya untuk menghasilkan kelompok-kelompok / segmentasi customer berdasarkan pola pembelian. Setelah mendapatakan segmentasi customer, selanjutnya dapat dikembangkan strategi marketing yang disesuaikan dengan kebutuhan atau preferensi dari masing-masing segmentasi customer. Dengan memahami karakteristik customer, perusahaan dapat meningkatkan efektivitas strategi marketing serta mempertahankan retensi yang sudah ada.

### Latar Belakang  
Brazilian E-Commerce Olist merupakan perusahaan baru dan saat ini sedang mengalami masalah yakni rendahnya customer retention, dalam artian perusahaan kesulitan untuk mempertahankan pelanggan yang ada. Masalah ini dapat muncul karena tidak adanya strategi marketing untuk menjaga retensi customer yang efektif serta kurangnya pemahaman mengenai perliaku pelanggan. Dampak dari permasalahan ini adalah berpotensi kehilangan pelanggan yang sudah ada dan meningkatkan biaya pemasaran untuk menarik pelanggan baru. Selain itu, masalah tambahan adalah dataset yang tidak berisikan customer segmentation, yaitu pembagian pelanggan ke dalam kelompok yang berbeda berdasarkan perilaku mereka. Hal ini menyulitkan Olist untuk memahami perilaku pelanggan dan membuat strategi pemasaran yang efektif. Oleh karena itu, solusi yang diusulkan adalah membuat strategi pemasaran berdasarkan customer segmentation dengan langkah-langkah membuat sistem atau proses untuk membagi pelanggan ke dalam kelompok yang berbeda, melakukan analisis perilaku pelanggan untuk masing-masing kelompok, dan membuat strategi pemasaran yang sesuai untuk masing-masing kelompok. Dengan adanya solusi ini, diharapkan dapat meningkatkan efektivitas strategi pemasaran dan retensi pelanggan serta menurunkan biaya pemasaran secara keseluruhan.

### Tujuan  
Tujuan akhir dari project ini adalah menghasilkan segmentasi customer yang dapat membantu dalam pembuatan strategi marketing yang akan diimplementasikan adalah untuk meningkatkan penjualan dan retensi pelanggan di perusahaan e-commerce Olist. Hal ini dapat dicapai dengan mengembangkan strategi marketing yang sesuai untuk masing-masing kelompok pelanggan berdasarkan data yang telah dianalisis. Dengan mengoptimalkan strategi marketing dan memonitor kinerja strategi secara berkala, diharapkan dapat meningkatkan efektivitas pemasaran dan mempertahankan pelanggan yang sudah ada. Dalam jangka panjang, hal ini dapat membantu perusahaan untuk bertahan di tengah persaingan yang semakin ketat.

### Batasan Masalah  
- Project ini akan memfokuskan pada perusahaan Brazilian E-Commerce Olist dan tidak akan membandingkan dengan perusahaan E-Commerce lainnya.
- Project ini akan memfokuskan pada masalah rendahnya retensi pelanggan dan strategi marketing yang efektif berdasarkan segementasi customer.
- Project ini akan berfokus pada pengembangan strategi marketing yang efektif untuk meningkatkan penjualan dan retensi pelanggan.


### Metrik Evaluasi
Karena disini kita akan melakukan segmentasi customer dengan demikian machine learning yang digunakan adalah unsupervised learning dan berikut adalah metrik evaluasi yang dapat digunakan pada permasalahan ini:
- Silhouette Coefficient: metrik ini mengukur seberapa baik setiap sampel cocok dengan kelompoknya sendiri dibandingkan dengan kelompok lain dalam dataset. Nilai Silhouette Coefficient berkisar antara -1 hingga 1, dimana nilai yang lebih tinggi menunjukkan kelompok yang lebih terdefinisi dengan baik.

- Elbow Method: metrik ini digunakan untuk menemukan jumlah klaster optimal dalam data. Dalam metrik ini, nilai inertia (jarak rata-rata setiap titik ke pusat klaster terdekat) digambar melawan jumlah klaster, dan titik siku dalam grafik ini menunjukkan jumlah klaster yang optimal.


# Data Understanding
Dataset ini berisi informasi dari 100 ribuan lebih pesanan dari tahun 2016 hingga 2018. Pada dataset ini terdapat beberapa fitur diantaranya adalah sebagai berikut:



<img src="https://i.imgur.com/HRhd2Y0.png" width="500" height="500">


Data ini adalah data komersial yang sebenarnya (asli), namun data ini telah di-anonimisasi dan referensi ke perusahaan dan mitra dalam teks ulasan telah diganti dengan nama-nama rumah besar di Game of Thrones.

Untuk memahami data lebih dalam lagi maka kita akan menggabungkan seluruh tabel dari dataset ini menjadi satu tabel agar mudah dalam melakukan EDA.

Dataset dapat diunduh pada link berikut:  
https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce


# Kesimpulan

Berdasarkan hasil yang telah kita lakukan maka dapat disimpulkan sebagai berikut:

1. Meskipun Olist memiliki banyak pelanggan baru setiap bulan, tingkat retensi pelanggan sangat rendah dengan hanya sekitar 1% pelanggan yang menggunakan layanan Olist setiap bulannya.

2. **Pembagian Cluster**: Berdasarkan analisis RFM, kita melakukan pembagian pelanggan ke dalam beberapa cluster. Cluster ini mencerminkan karakteristik dan perilaku pelanggan yang berbeda.
    - `*Big Spenders*`: Pelanggan yang melakukan pembelian dengan nilai tertinggi (Recency rendah, Frequency tinggi, Monetary Value tinggi).
    - `*Sleeping Giant*`: Pelanggan yang belum melakukan pembelian baru-baru ini (Recency tinggi), tetapi memiliki nilai pembelian yang tinggi di masa lalu (Frequency tinggi, Monetary Value tinggi).
    - `*Loyalist*`: Pelanggan yang secara konsisten melakukan pembelian (Recency rendah, Frequency tinggi, Monetary Value cenderung tinggi).
    - `*Newcomers*`: Pelanggan baru yang baru saja melakukan pembelian (Recency rendah, Monetary Rendah, Frequency rendah).
    - `*Lost Customers*`: Pelanggan yang sudah lama tidak melakukan pembelian (Recency tinggi) dan memiliki nilai pembelian rendah (Frequency rendah, Monetary Value rendah).
    - `*Churn Risk*`: Pelanggan yang berisiko beralih atau tidak melakukan pembelian lagi (Recency tinggi, Frequency rendah, Monetary Value rendah).

3. **Metode Evaluasi Cluster**: Untuk memilih jumlah cluster yang optimal, kita menggunakan metode silhouette score. Silhouette score memberikan gambaran seberapa baik pemisahan antara cluster dan seberapa homogen data dalam setiap cluster.

4. **Hasil Evaluasi**: Meskipun cluster terbaik berdasarkan silhouette score adalah 4 cluster dengan score 0.38, kita memilih menggunakan 7 cluster dengan score 0.36. Ini dikarenakan pembagian dengan 5-6 cluster memberikan tingkat detail yang lebih baik daripada 4 cluster yang terlalu umum.

5. **Hasil Rekomendasi**: Berdasarkan hasil dari RFM Analisis dan K-Means kita dapat menentukan rekomendasi yang tepat untuk melakukan strategi marketing, dan diharapkan dari terbentuknya segmentasi ini dapat meminimalisir loss yang terjadi pada biaya strategi marketing, serta diharapkan dengan rekomendasi yang diberikan mampu untuk meningkatkan retensi serta sales dari Olist.

**Kesimpulan berdasarkan Bisnis**
1. Terdapat banyak customer baru tiap bulan, tetapi retention rate nya sangat tinggi (hanya sekitar 1% customer yang memakai olist tiap bulannya). (Berhubungan dengan tujuan)
2. Product terbaik dari Olist adalah Furniture, sementara product terburuk adalah Food & Beverages. (Kesimpulan utk di EDA)
3. Majoritas customer Olist menggunakan credit card dengan jangka waktu pembayaran adalah 1 bulan. (Kesimpulan utk di EDA)
4. State yang paling ramai transaksi adalah Sao Paulo, dengan total customer 20.000+ dan total seller 20.000+. (Kesimpulan utk di EDA) 
5. Sau Paulo menjadi state yang paling ramai bisa dikarenakan harga jual dan harga freight nya yang sangat terjangkau. Rata-rata dan median dari harga jual dan freight price di Sau Paulo adalah yang termurah dibandingkan dengan state lainnya. (Kesimpulan utk di EDA)

