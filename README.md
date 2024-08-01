# **California Median House Price** : Linear Regression Model 

By [Dito Wicaksana P.](https://github.com/ditoowp) | Data Resource: [Kaggle](https://www.kaggle.com/datasets/shibumohapatra/house-price/data)

<center><img src="https://imgtr.ee/images/2024/07/27/2688680e64de44d23c082a45db7887f7.jpeg"/></center>

---

## Introduction
<p style="text-align: justify;">
Pasar perumahan di California dikenal dengan volatilitas dan harga tinggi, dipengaruhi oleh faktor seperti pertumbuhan ekonomi, urbanisasi, dan tren demografis. Memahami pola-pola ini dapat memberikan wawasan tentang faktor-faktor yang mendorong perubahan harga, membantu para pemangku kepentingan seperti pembuat kebijakan, investor, dan calon pemilik rumah untuk membuat keputusan yang tepat.
</p>
<p style="text-align: justify;">
Nilai median disini yang dicari karena ingin melihat nilai tengah dari seluruh harga rumah dalam blok. Apabila menggunakan mean maka harga rata-rata rumah dalam blok akan jauh lebih tinggi ketimbang menggunakan median.
</p>

---

## Objective
<p style="text-align: justify;">
Tujuan dari proyek ini adalah mengembangkan model prediksi yang dapat secara akurat memperkirakan harga rumah median berdasarkan fitur yang ada. Dengan memanfaatkan teknik pembelajaran mesin, model ini bertujuan untuk:
</p>

* Mengidentifikasi faktor utama yang mempengaruhi harga rumah
* Memberikan prediksi harga yang akurat untuk membantu dalam pengambilan keputusan.
* Mengeksplorasi bagaimana perubahan dalam fitur tertentu mempengaruhi keterjangkauan dan ketersediaan perumahan.

<p style="text-align: justify;">
Tujuan utamanya adalah menawarkan <em>tools<em> yang dapat mendukung analisis <em>real estate</em> dan perencanaan strategis di sektor perumahan.
</p>

---

## Conclusion
### Exploratory Data Analysis (EDA)
<p style="text-align: justify;">
Pilihan rumah yang ada cukup bervariasi, mulai dari usia rumahnya ada yang masih tergolong baru dan lama walaupun rata-rata rumah berusia 30-40 tahun. Mayoritas rumah yang dijual sepertinya rumah yang kecil, diketahui dari jumlah ruangan dan jumlah kamar tidurnya yang tidak terlalu banyak pada suatu blok. Selain itu, populasi yang banyak pada suatu blok maka akan mempengaruhi juga nilai median rumah. Ini terjadi dikarenakan tingkat populasi yang tinggi membuat *demand* yang tinggi terhadap *housing properties* dan apabila *demand*-nya tinggi maka akan semakin terbatas barang yang di-*demand* membuat harga menjadi naik (*). *Landscape* rumah juga mempengaruhi harga rumah, rumah yang termasuk dekat dengan pantai cenderung akan lebih mahal dibandingkan dengan harga rumah yang berada di-*inland*. 
</p>
(*) Reference : [UNECE](https://unece.org/fileadmin/DAM/hlm/archive/Key%20note%20population%20and%20housing.pdf)

### Model Analysis

**Support Vector Regressor (SVR)**
<p style="text-align: justify;">
Performa model yang kurang baik pada *train* dan *test*, **R2 Score** juga negatif yang menunjukkan model gagal dalam menangkap varians yang ada pada data. Model ini dirasa tidak cocok untuk dataset ini dikarenakan data yang mungkin terlalu kompleks untuk model **SVR**.
</p>
**Decision Tree Regressor (DTR)**
<p style="text-align: justify;">
Skor yang sangat sempurna pada *train*, namun pada *test* skor-nya berbeda jauh. Menandakan *over fit*.
</p>
**K-Neighbors Regressor (KNR)**
<p style="text-align: justify;">
Performa yang lumayan baik namun menurun performanya dari *train* ke *test*. Menandakan *over fit* juga.
</p>
**Random Forest Regressor (RFR)**
<p style="text-align: justify;">
Performa yang cukup baik pada *train* dan *test*. **R2 Score** juga baik yang menandakan model dapat menangkap pola data dengan baik. 
</p>
**Extreme Gradient Boosting (XGBoost)**
<p style="text-align: justify;">
Dari kelima model, model ini merupakan yang paling baik **R2 Score**-nya. Karena model ini merupakan model yang terbaik, maka dilakukan *hyperparameter tuning* untuk meningkatkan lagi **R2 Score**-nya. Setelah dilakukan *hyperparameter tuning* **R2 Score** naik walaupun tidak terlalu signifikan.
</p>
### Best Model Analysis
<p style="text-align: justify;">
Dalam kasus prediksi harga median rumah di California, model XGBoost yang telah dioptimalkan menunjukkan kinerja terbaik dibandingkan dengan model lain. Dengan skor R² sebesar 0.78 setelah tuning hyperparameter, model ini mampu menangkap variasi dalam data dan memberikan prediksi yang akurat. Peningkatan dari skor R² 0.77 sebelum tuning menunjukkan bahwa proses optimasi ini penting untuk meningkatkan akurasi model.
</p>
<p style="text-align: justify;">
Dengan model XGBoost yang dioptimalkan, kita dapat lebih percaya diri dalam menggunakan prediksi harga median rumah untuk berbagai aplikasi, seperti penentuan harga jual, analisis investasi, dan perencanaan pembangunan. Model ini memberikan alat yang kuat dan dapat diandalkan bagi stakeholder untuk membuat keputusan yang lebih tepat dan didasarkan pada analisis data yang akurat.
</p>