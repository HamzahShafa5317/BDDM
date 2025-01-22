PROJEK AKHIR UAS
BIG DATA AND DATA MINING (ST168)

Prediksi Obesitas Menggunakan Metode Random Forest dan XGBClassifier

![1.png](1.png)













Disusun oleh
22.11.5317
Hamzah Shafa Tandyayudha
[BIG DATA AND DATA MINING 07]


PROGRAM STUDI S1 INFORMATIKA
FAKULTAS ILMU KOMPUTER
UNIVERSITAS AMIKOM YOGYAKARTA
2025



1.	PENDAHULUAN
Obesitas adalah masalah kesehatan yang terpaku pada penimbunan lemak yang berlebih di jaringan tubuh manusia yang dapat mengakibatkan gangguan kesehatan sampai menyebabkan kematian[1]. Faktor-faktor yang mempengaruhi penyakit obesitas ini seperti faktor lingkungan, pelayanan kesehatan, faktor genetik, dan faktor perilaku[2]. Orang-orang yang memiliki resiko tinggi terkena obesitas adalah orang yang memiliki asupan gizi makro berlebih, sering mengkonsumsi fast food, rendahnya aktivitas fisik, dan riwayat orang tua yang gemuk[3]. Di Penelitian ini menggunakan data mining karena di dalam penelitian medis teknologi ini menjadi bidang terdepan karena kinerja yang sangat baik dalam mengevaluasi risiko dan prediksi penyakit pasien untuk membantu pengambilan keputusan klinis[4]. 
Metode yang digunakan pada penelitian ini adalah Random Forest dan XGBClassifier, Random Forest adalah kumpulan hirarkis dari klasifikasi pada pohon terstruktur dengan dataset yang berjumlah besar dan tidak relevan, hanya atribut penting yang informatif untuk model pengklasifikasi[5]. Selain itu metode XGBClassifier digunakan karena efisiensi nya yang tinggi dan kemampuan beradaptasi untuk data yang diolah tinggi[6]. Tujuan dari penelitian ini adalah dapat mempermudah prediksi obesitas pada manusia dengan menggunakan teknologi machine learning atau data mining untuk mengurangi jumlah orang yang terkena obesitas.

2.	PROFILE DATASET 

Dataset di penelitian ini mencakup informasi tentang demografi, kebiasaan makan, aktivitas fisik, dan klasifikasi obesitas. Dataset ini memiliki delapan kolom numerik seperti Age, Height, dan Weight yang berisi data berbasis angka, serta sembilan kolom kategorikal seperti Gender, family_history, dan Obesity yang berisi data berbasis kategori atau pilihan tertentu. Kualitas data cukup baik karena tidak terdapat nilai yang hilang. Namun, fitur kategorikal memerlukan konversi ke format numerik untuk dapat dianalisis oleh model, dan variabel numerik memiliki skala yang beragam sehingga normalisasi diperlukan untuk menghindari ketidakseimbangan dalam analisis.

dataset ini diambil dari kaagle https://drive.google.com/file/d/1nOZDTX3ddB_dEl8dBZbsKlVtOkxv64Fc/view?usp=drive_link

3.	DATA PREPROCESSING 
 

Karena tidak ada nilai kosong dalam dataset, tidak diperlukan langkah imputasi.

 

Fitur kategorikal seperti Gender dan MTRANS dikonversi menggunakan one-hot encoding agar dapat direpresentasikan dalam format numerik yang dapat dipahami oleh model. Selain itu, target variabel Obesity diubah menjadi representasi numerik menggunakan label encoding untuk memastikan model dapat memprosesnya dengan baik.
   
Variabel numerik seperti Height dan Weight dinormalisasi menggunakan Min-Max Scaling untuk memastikan setiap fitur memiliki skala yang sebanding. Data dibagi menjadi set pelatihan dan pengujian dengan rasio 80:20 untuk melatih dan mengevaluasi model.	


Pemilihan metode Random Forest dan XGBoost Classifier dilakukan karena kedua algoritma ini unggul dalam menangani berbagai jenis data. Random Forest dipilih karena fleksibilitasnya dalam menangani fitur numerik dan kategorikal tanpa banyak penyesuaian, serta kemampuannya memberikan interpretasi melalui skor pentingnya fitur. Selain itu, algoritma ini tahan terhadap noise dan memberikan hasil yang stabil.
XGBoost Classifier dipilih karena efisiensinya dalam menangani dataset yang kompleks dan kemampuannya menangkap hubungan non-linear antar fitur. Algoritma ini dilengkapi dengan fitur regulasi bawaan yang mencegah overfitting, membuatnya sangat cocok untuk dataset yang memiliki ketidakseimbangan kelas. Kedua metode ini saling melengkapi, memungkinkan analisis yang akurat sekaligus dapat diinterpretasikan dengan baik.

4.	EXPLORATORY DATA ANALYSIS 

 
 
  

 

 

Hasil dari analisis eksplorasi data menunjukkan adanya korelasi yang kuat antara variabel Weight dan Height terhadap tingkat obesitas. Distribusi beberapa fitur kategorikal, seperti moda transportasi (MTRANS), terlihat tidak merata, yang dapat memengaruhi kinerja model. Selain itu, ditemukan outlier pada variabel Weight dan Height, yang berpotensi memengaruhi performa model jika tidak ditangani dengan tepat.

5.	SELEKSI FITUR 
 

Pada Gambar diatas adalah untuk memastikan tidak ada data yang berulang, yang dapat menyebabkan bias dalam analisis. 

 

Pada Gambar tersebut adalah untuk menghapus kolom-kolom yang didasarkan pada korelasi tinggi dengan target atau tidak relevan. 

 

One-hot encoding adalah langkah standar untuk menangani variabel kategorikal. Namun, memutuskan untuk menggunakan drop_first=True mengurangi multikolinearitas, tetapi penting untuk memastikan bahwa informasi yang dibuang tidak relevan untuk model.

 
Pada Gambar diatas untuk memisahkan fitur (independen) dari target (dependen) adalah langkah penting dalam pipeline machine learning. 

Disini menggunakan metode RFE atau feature importance karena efektif untuk data dengan berbagai tipe fitur terutama yang terdapat paka kode yaitu numerik/kategorikal.

6.	MODELING 
 
 
 
Link GitHub		: https://github.com/HamzahShafa5317/BDDM.git
Link Launchinpad	: https://launchinpad.com/project/prediksi-diabetes-menggunakan-random-forest-dan-xgbclassifier-f53cc34
Link ipynb		: https://colab.research.google.com/drive/1gehtPy3SQifDwDm_WwdvWTtKtS5oaX9D?authuser=0#scrollTo=sxd3XMCIam1N
7.	EVALUASI MODEL (10 point)
Random Forest
 
   



XGBClassifier
 
   

8.	ANALISA DAN PEMBAHASAN (15 point)
Performa kedua model menunjukkan kelebihan dan kekurangannya masing-masing. Random Forest memberikan hasil yang stabil dengan interpretasi yang baik melalui skor pentingnya fitur, tetapi performanya sedikit tertinggal pada dataset dengan ketidakseimbangan kelas. Di sisi lain, XGBoost Classifier unggul dalam menangkap pola kompleks antar fitur, terutama dalam memprediksi kelas minoritas. Kemampuan bawaan XGBoost membantu mengurangi risiko overfitting, membuatnya lebih adaptif terhadap tantangan dataset ini. Secara keseluruhan, ketidakseimbangan kelas menjadi tantangan utama yang memengaruhi performa model, tetapi XGBoost menunjukkan kemampuan adaptasi yang lebih baik dibandingkan Random Forest.

9.	KESIMPULAN (5 point)
Dataset ini memiliki karakteristik yang beragam, baik dari sisi fitur numerik maupun kategorikal, sehingga preprocessing yang cermat sangat penting. Random Forest memberikan interpretasi hasil yang lebih mudah dipahami, sedangkan XGBoost unggul dalam hal performa, terutama pada metrik F1-Score. Ketidakseimbangan kelas menjadi tantangan utama yang memengaruhi performa model, dan pendekatan seperti oversampling atau algoritma adaptif dapat membantu meningkatkan hasil. Kombinasi kedua model memberikan hasil yang dapat diandalkan untuk memprediksi obesitas, dengan wawasan yang berharga tentang pentingnya setiap fitur dalam analisis.

10.	 Referensi (5 point)

[1]	T. G. A. D. Pemayun, A. A. G. Budhitresna, dan P. A. N. K. Permatananda, “Gambaran Tingkat Aktivitas Fisik dan Kejadian Obesitas pada Civitas Akademika Universitas Warmadewa, Bali,” Jurnal Pendidikan Tambusai, vol. 6, no. 2, hlm. 8526–8532, 2022.
[2]	S. K. Saraswati dkk., “Literature Review: Faktor Risiko Penyebab Obesitas,” Media Kesehatan Masyarakat Indonesia, vol. 20, no. 1, hlm. 70–74, 2021.
[3]	I. Telisa, Y. Hartati, dan A. D. Haripamilu, “Faktor risiko terjadinya obesitas pada remaja SMA,” Faletehan Health Journal, vol. 7, no. 03, hlm. 124–131, 2020.
[4]	W.-T. Wu dkk., “Data mining in clinical big data: the frequently used databases, steps, and methodological models,” Mil Med Res, vol. 8, hlm. 1–12, 2021.
[5]	V. Jackins, S. Vimal, M. Kaliappan, dan M. Y. Lee, “AI-based smart prediction of clinical disease using random forest classifier and Naive Bayes,” J Supercomput, vol. 77, no. 5, hlm. 5198–5219, 2021.
[6]	S. N. Raj, R. S. Vani, B. Raja, T. S. Harsha, T. Drakshayani, dan R. Charith, “HEART DISEASE DETECTION USING XGB-CLASSIFIER AND FAILURE PREDICTION USING GRADIENT BOOSTING,” Journal of Nonlinear Analysis and Optimization, vol. 15, no. 1, 2024.
 
