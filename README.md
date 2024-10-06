# Laporan Proyek Machine Learning - Rendika Nurhartanto Suharto
## Domain Proyek

Permintaan kredit merupakan salah satu aspek penting dalam industri perbankan dan keuangan. Setiap pengajuan kredit membawa risiko, baik bagi pemberi pinjaman maupun peminjam. Pemberi pinjaman perlu menilai apakah pemohon memiliki kemampuan untuk memenuhi kewajiban pembayaran pinjaman sesuai dengan jangka waktu yang ditentukan. Oleh karena itu, keputusan apakah suatu pinjaman disetujui atau ditolak sangat bergantung pada evaluasi risiko yang akurat.

Untuk mencapai evaluasi yang tepat, pemberi pinjaman seringkali bergantung pada berbagai indikator keuangan dan data historis pemohon. Beberapa faktor utama yang biasanya dipertimbangkan adalah pendapatan, status pekerjaan, jumlah utang, rasio utang terhadap pendapatan (Debt-to-Income Ratio), skor kredit, dan riwayat pembayaran. Namun, keputusan pemberian pinjaman juga bisa terpengaruh oleh faktor non-keuangan seperti status pernikahan dan jumlah tanggungan.

Dalam konteks ini, **Predictive Analysis for Loan Approval** bertujuan untuk mengembangkan model prediktif yang mampu menilai kemungkinan persetujuan pinjaman berdasarkan profil keuangan dan demografis pemohon. Dengan menggunakan data sintetik yang terdiri dari 20.000 catatan, proyek ini memungkinkan analisis komprehensif untuk menentukan apakah seorang pemohon berisiko rendah atau tinggi dalam menerima pinjaman.

### Mengapa dan Bagaimana Masalah Ini Harus Diselesaikan
Proses penilaian kelayakan pinjaman sering kali memerlukan analisis manual yang panjang dan kompleks. Pendekatan tradisional tidak selalu cukup untuk mengatasi volume besar aplikasi pinjaman atau untuk memberikan penilaian risiko yang tepat dengan akurasi tinggi. Kesalahan dalam menilai risiko dapat menyebabkan kerugian finansial yang signifikan bagi lembaga pemberi pinjaman atau, di sisi lain, penolakan pinjaman bagi individu yang layak.

Dengan memanfaatkan analitik prediktif berbasis data, proses evaluasi risiko dapat diotomatisasi dan disempurnakan. Algoritme pembelajaran mesin (machine learning) dapat digunakan untuk mempelajari pola dari data historis dan memberikan penilaian yang lebih objektif dan cepat terkait risiko pinjaman. Model prediktif ini dapat membantu mengurangi tingkat default pada pinjaman, meningkatkan efisiensi proses persetujuan, dan meningkatkan pengalaman pemohon dengan memberikan keputusan lebih cepat dan akurat.

### Hasil Riset Terkait
Beberapa studi telah menunjukkan bahwa model prediktif berbasis data dapat meningkatkan akurasi dalam keputusan persetujuan pinjaman. Menurut penelitian oleh *Jumaa, M., et al, 2023* yang berjudul **"Improving  Credit  Risk Assessment  through  Deep  Learning-based Consumer Loan Default Prediction Model"**, pendekatan berbasis machine learning berhasil meningkatkan tingkat akurasi dalam prediksi default kredit sebesar 15-20% dibandingkan dengan metode tradisional seperti regresi logistik. Sementara itu, *Zhou, S., et al, 2023* dalam studi **"The Current State and Challenges of Financial Risk Management"** menekankan pentingnya pemilihan fitur yang tepat seperti skor kredit, rasio utang terhadap pendapatan, dan riwayat pembayaran dalam pengembangan model prediksi kredit yang akurat.

### Referensi
- Jumaa, M., et al. (2023). [**Improving  Credit  Risk Assessment  through  Deep  Learning-based Consumer Loan Default Prediction Model**](https://www.ssbfnet.com/ojs/index.php/ijfbs/article/view/2579/1822) 
- Zhou, S., et al. (2023). [**The Current State and Challenges of Financial Risk Management**](https://www.researchgate.net/publication/379363316_The_Current_State_and_Challenges_of_Financial_Risk_Management).

## Business Understanding
Tujuan dari proyek ini adalah untuk menilai risiko keuangan yang terkait dengan pemohon pinjaman serta memprediksi kemungkinan persetujuan pinjaman mereka. Lembaga keuangan menghadapi tantangan kritis dalam menilai aplikasi pinjaman, yaitu menyeimbangkan antara persetujuan peminjam yang sah dan mitigasi risiko gagal bayar. Menyetujui pinjaman berisiko tinggi dapat mengakibatkan kerugian finansial, sementara menolak pemohon yang memenuhi syarat dapat berpotensi menyebabkan kehilangan peluang bisnis. Oleh karena itu, beberapa pernyataan masalah (problem statements) dirumuskan untuk dijawab sebagai berikut.
### Problem Statements

1. **Pernyataan Masalah 1**: Bagaimana mengidentifikasi faktor-faktor utama yang mempengaruhi keputusan persetujuan pinjaman (LoanApproved) berdasarkan atribut personal dan finansial pemohon?
2. **Pernyataan Masalah 2**: Bagaimana algoritma prediktif dapat diimplementasikan untuk meningkatkan akurasi prediksi persetujuan pinjaman dan risiko kredit dengan memanfaatkan data historis dari pemohon?

### Goals

1. **Jawaban Pernyataan Masalah 1**: Mengidentifikasi fitur-fitur utama yang berkontribusi positif dan negatif terhadap persetujuan pinjaman.
   - Tujuan ini dapat dicapai melalui analisis data yang mencakup korelasi antar variabel, visualisasi data, dan penggunaan teknik statistik untuk menentukan faktor-faktor yang paling berpengaruh dalam proses persetujuan.

2. **Jawaban Pernyataan Masalah 2**: Mengembangkan model prediktif yang dapat memprediksi persetujuan pinjaman dengan akurasi tinggi berdasarkan data historis.
   - Dengan melibatkan algoritma machine learning seperti AdaBoostClassifier, RidgeClassifier, dan SVM, model ini diharapkan dapat memberikan prediksi yang lebih baik dalam menentukan apakah pemohon pinjaman layak untuk disetujui atau tidak.

### Solution Statements

1. **Solusi 1**: Menerapkan analisis korelasi untuk mengidentifikasi faktor-faktor yang berpengaruh. Melalui visualisasi seperti grafik korelasi dan regresi, kita bisa memahami hubungan antara variabel personal dan finansial pemohon dengan status persetujuan pinjaman. 
   - Dalam hal ini, faktor-faktor seperti **MonthlyIncome**, **AnnualIncome**, dan **CreditScore** diharapkan menunjukkan hubungan positif dengan hasil persetujuan pinjaman, sementara **RiskScore** dan **TotalDebtToIncomeRatio** diperkirakan memiliki korelasi negatif yang signifikan.
   ![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)

2. **Solusi 2**: Mengimplementasikan beberapa algoritma machine learning dan melakukan evaluasi menyeluruh untuk memilih model yang terbaik. Ini mencakup tahap pengumpulan dan persiapan data, pelatihan model, serta evaluasi menggunakan metrik seperti accuracy, precision, recall, dan F1 score.
   - Dengan melakukan trial and error pada berbagai model dan tuning hyperparameters, diharapkan ditemukan model yang optimal untuk memprediksi hasil persetujuan pinjaman secara akurat.

Dengan langkah-langkah solusi di atas, proyek ini bertujuan untuk memberikan wawasan yang mendalam tentang faktor-faktor yang mempengaruhi persetujuan pinjaman serta membangun model prediktif yang efisien dan efektif.

**Rubrik/Kriteria Tambahan (Opsional)**:
- Menambahkan bagian “Solution Statement” yang menguraikan cara untuk meraih goals. Bagian ini dibuat dengan ketentuan sebagai berikut: 


## Data Understanding
Paragraf awal bagian ini menjelaskan informasi mengenai data yang Anda gunakan dalam proyek. Sertakan juga sumber atau tautan untuk mengunduh dataset. Contoh: [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/Restaurant+%26+consumer+data).

Selanjutnya uraikanlah seluruh variabel atau fitur pada data. Sebagai contoh:  

### Variabel-variabel pada Restaurant UCI dataset adalah sebagai berikut:
- accepts : merupakan jenis pembayaran yang diterima pada restoran tertentu.
- cuisine : merupakan jenis masakan yang disajikan pada restoran.
- dst

**Rubrik/Kriteria Tambahan (Opsional)**:
- Melakukan beberapa tahapan yang diperlukan untuk memahami data, contohnya teknik visualisasi data atau exploratory data analysis.

## Data Preparation
Pada bagian ini Anda menerapkan dan menyebutkan teknik data preparation yang dilakukan. Teknik yang digunakan pada notebook dan laporan harus berurutan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan proses data preparation yang dilakukan
- Menjelaskan alasan mengapa diperlukan tahapan data preparation tersebut.

## Modeling
Tahapan ini membahas mengenai model machine learning yang digunakan untuk menyelesaikan permasalahan. Anda perlu menjelaskan tahapan dan parameter yang digunakan pada proses pemodelan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan kelebihan dan kekurangan dari setiap algoritma yang digunakan.
- Jika menggunakan satu algoritma pada solution statement, lakukan proses improvement terhadap model dengan hyperparameter tuning. **Jelaskan proses improvement yang dilakukan**.
- Jika menggunakan dua atau lebih algoritma pada solution statement, maka pilih model terbaik sebagai solusi. **Jelaskan mengapa memilih model tersebut sebagai model terbaik**.

## Evaluation
Pada bagian ini anda perlu menyebutkan metrik evaluasi yang digunakan. Lalu anda perlu menjelaskan hasil proyek berdasarkan metrik evaluasi yang digunakan.

Sebagai contoh, Anda memiih kasus klasifikasi dan menggunakan metrik **akurasi, precision, recall, dan F1 score**. Jelaskan mengenai beberapa hal berikut:
- Penjelasan mengenai metrik yang digunakan
- Menjelaskan hasil proyek berdasarkan metrik evaluasi

Ingatlah, metrik evaluasi yang digunakan harus sesuai dengan konteks data, problem statement, dan solusi yang diinginkan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan formula metrik dan bagaimana metrik tersebut bekerja.

**---Ini adalah bagian akhir laporan---**

_Catatan:_
- _Anda dapat menambahkan gambar, kode, atau tabel ke dalam laporan jika diperlukan. Temukan caranya pada contoh dokumen markdown di situs editor [Dillinger](https://dillinger.io/), [Github Guides: Mastering markdown](https://guides.github.com/features/mastering-markdown/), atau sumber lain di internet. Semangat!_
- Jika terdapat penjelasan yang harus menyertakan code snippet, tuliskan dengan sewajarnya. Tidak perlu menuliskan keseluruhan kode project, cukup bagian yang ingin dijelaskan saja.
