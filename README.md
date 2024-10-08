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
   ![Correlation between Features and Loan Approval](https://raw.githubusercontent.com/Rendika7/Predictive-Analysis-for-Loan-Approval/refs/heads/main/source/Correlation%20between%20Features%20and%20Loan%20Approval.png)
    ![Regression plot feature correlated with Loan Approved](https://raw.githubusercontent.com/Rendika7/Predictive-Analysis-for-Loan-Approval/refs/heads/main/source/Regression%20plot%20feature%20correlated%20with%20Loand%20Approved.png)
2. **Solusi 2**: Mengimplementasikan beberapa algoritma machine learning dan melakukan evaluasi menyeluruh untuk memilih model yang terbaik. Ini mencakup tahap pengumpulan dan persiapan data, pelatihan model, serta evaluasi menggunakan metrik seperti accuracy, precision, recall, dan F1 score.
   - Dengan melakukan trial and error pada berbagai model, diharapkan ditemukan model yang optimal untuk memprediksi hasil persetujuan pinjaman secara akurat.
    ![Model Object Initiation](https://raw.githubusercontent.com/Rendika7/Predictive-Analysis-for-Loan-Approval/refs/heads/main/source/Model%20Object%20Initiation.png)
    ![Class for Train and Evaluate Model](https://raw.githubusercontent.com/Rendika7/Predictive-Analysis-for-Loan-Approval/refs/heads/main/source/Class%20for%20Train%20and%20Evaluate%20Model.png)
    ![Train and Evaluation Models](https://raw.githubusercontent.com/Rendika7/Predictive-Analysis-for-Loan-Approval/refs/heads/main/source/Train%20and%20Evaluation%20Models.png)

Dengan langkah-langkah solusi di atas, proyek ini bertujuan untuk memberikan wawasan yang mendalam tentang faktor-faktor yang mempengaruhi persetujuan pinjaman serta membangun model prediktif yang efisien dan efektif.

## Data Understanding
Pada bagian ini, dataset yang digunakan dalam proyek ini terdiri dari 20.000 catatan sintetis pemohon pinjaman yang dirancang untuk mensimulasikan data keuangan dan pribadi di dunia nyata. Dataset ini menyajikan informasi demografis dan finansial yang komprehensif, memungkinkan analisis mendalam mengenai faktor-faktor yang mempengaruhi keputusan persetujuan pinjaman dan penilaian risiko. Dataset ini dapat diunduh melalui tautan berikut: [Financial Risk for Loan Approval](https://www.kaggle.com/datasets/lorenzozoppelletto/financial-risk-for-loan-approval/data).

### Variabel-variabel pada dataset "Financial Risk for Loan Approval" adalah sebagai berikut:
- **ApplicationDate**: Tanggal pengajuan pinjaman.
- **Age**: Usia pemohon.
- **AnnualIncome**: Pendapatan tahunan pemohon.
- **CreditScore**: Skor kredit yang menunjukkan tingkat kelayakan pemohon.
- **EmploymentStatus**: Status pekerjaan pemohon saat ini.
- **EducationLevel**: Tingkat pendidikan tertinggi yang telah dicapai pemohon.
- **Experience**: Pengalaman kerja pemohon.
- **LoanAmount**: Jumlah pinjaman yang diminta.
- **LoanDuration**: Durasi pembayaran pinjaman.
- **MaritalStatus**: Status perkawinan pemohon.
- **NumberOfDependents**: Jumlah tanggungan yang dimiliki pemohon.
- **HomeOwnershipStatus**: Jenis kepemilikan rumah (misalnya, sewa, milik sendiri).
- **MonthlyDebtPayments**: Kewajiban pembayaran utang bulanan pemohon.
- **CreditCardUtilizationRate**: Persentase penggunaan kartu kredit pemohon.
- **NumberOfOpenCreditLines**: Jumlah garis kredit aktif yang dimiliki pemohon.
- **NumberOfCreditInquiries**: Jumlah pemeriksaan kredit yang telah dilakukan.
- **DebtToIncomeRatio**: Rasio utang terhadap pendapatan.
- **BankruptcyHistory**: Riwayat kebangkrutan pemohon.
- **LoanPurpose**: Tujuan pengajuan pinjaman.
- **PreviousLoanDefaults**: Riwayat gagal bayar pinjaman sebelumnya.
- **PaymentHistory**: Riwayat pembayaran pemohon.
- **LengthOfCreditHistory**: Durasi sejarah kredit pemohon.
- **SavingsAccountBalance**: Saldo rekening tabungan pemohon.
- **CheckingAccountBalance**: Saldo rekening giro pemohon.
- **TotalAssets**: Total aset yang dimiliki pemohon.
- **TotalLiabilities**: Total utang yang dimiliki pemohon.
- **MonthlyIncome**: Pendapatan per bulan pemohon.
- **UtilityBillsPaymentHistory**: Riwayat pembayaran tagihan utilitas pemohon.
- **JobTenure**: Durasi pekerjaan pemohon saat ini.
- **NetWorth**: Total kekayaan finansial pemohon.
- **BaseInterestRate**: Tingkat bunga awal yang diterapkan.
- **InterestRate**: Tingkat bunga yang diterapkan pada pinjaman.
- **MonthlyLoanPayment**: Pembayaran pinjaman bulanan.
- **TotalDebtToIncomeRatio**: Total utang dibandingkan dengan pendapatan.
- **LoanApproved**: Status persetujuan pinjaman (apakah disetujui atau tidak).
- **RiskScore**: Skor penilaian risiko yang mengukur kemungkinan gagal bayar pemohon.

### Tahapan Pemahaman Data
- **Informasi Umum dalam Dataset**
Tahapan pertama dalam pemahaman data adalah memperoleh informasi umum mengenai dataset. Melalui fungsi yang menampilkan 5 baris pertama, tipe data setiap kolom, jumlah nilai yang tidak null, dan ukuran dataset, kita dapat memahami struktur dan karakteristik data secara keseluruhan. Selain itu, statistik deskriptif memberikan gambaran tentang sebaran data, termasuk nilai rata-rata dan rentang, serta jumlah nilai unik per kolom yang membantu mengidentifikasi variasi dalam data.

    ![Statistika Deskriptif](https://raw.githubusercontent.com/Rendika7/Predictive-Analysis-for-Loan-Approval/refs/heads/main/source/Statistika%20Deskriptif.png)
    ![Distribusi Tipe Data](https://raw.githubusercontent.com/Rendika7/Predictive-Analysis-for-Loan-Approval/refs/heads/main/source/Distribusi%20Tipe%20Data.png)

- **Distribusi Variabel Numerik**
Setelah mendapatkan informasi umum, analisis distribusi variabel numerik dilakukan dengan menggunakan histogram dan boxplot. Histogram menunjukkan frekuensi setiap nilai dalam variabel, sementara boxplot memberikan informasi mengenai outlier, median, dan sebaran data. Dengan analisis ini, kita dapat memahami bagaimana data terdistribusi dan apakah ada pola atau keanehan yang perlu ditangani dalam proses pemodelan.

    ![Histogram for Distribution Numeric Features](https://raw.githubusercontent.com/Rendika7/Predictive-Analysis-for-Loan-Approval/refs/heads/main/source/Histogram.png)
    
- **Distribusi Variabel Target ('LoanApproved')**
Tahapan berikutnya adalah menganalisis distribusi variabel target, yaitu **'LoanApproved'**, menggunakan diagram batang. Visualisasi ini menggambarkan jumlah pemohon yang disetujui dan tidak disetujui dalam pengajuan pinjaman, memberikan wawasan tentang keseimbangan kelas dalam dataset. Memahami proporsi antara kelas-kelas ini penting untuk mengantisipasi potensi bias yang mungkin muncul saat membangun model prediksi.

    ![Loan Approved Distribution](https://raw.githubusercontent.com/Rendika7/Predictive-Analysis-for-Loan-Approval/refs/heads/main/source/Loan%20Approved%20Distribution.png)

Dengan demikian, setiap tahapan ini berkontribusi pada pemahaman yang lebih baik terhadap dataset dan membantu dalam pengembangan model yang lebih efektif dan akurat.


## Data Preparation

Tahapan **Data Processing** atau **Data Preparation** merupakan langkah penting dalam mengolah dataset agar siap untuk analisis dan pemodelan. Proses ini meliputi serangkaian teknik yang bertujuan untuk membersihkan, memformat, dan mempersiapkan data dengan lebih baik untuk model yang akan digunakan.

1. **Data Duplicated**
Selanjutnya, kita memeriksa adanya **data duplikat** menggunakan fungsi `check_duplicates(df)`. Mengidentifikasi dan menghapus data duplikat penting untuk memastikan analisis tidak terdistorsi oleh entri yang berulang, yang dapat menyebabkan bias dalam hasil model.

    ![Duplicated Data](https://raw.githubusercontent.com/Rendika7/Predictive-Analysis-for-Loan-Approval/refs/heads/main/source/Duplicated%20Data.png)

2. **Missing Values**
Tahapan berikutnya adalah memeriksa **nilai yang hilang** dalam dataset dengan menggunakan fungsi `missing_data(df)`. Nilai yang hilang dapat mengganggu analisis, sehingga penting untuk mengidentifikasi kolom yang memiliki nilai hilang dan mengambil langkah yang diperlukan untuk mengatasinya, seperti menghapus atau mengisi nilai tersebut.

    ![Missing Values](https://raw.githubusercontent.com/Rendika7/Predictive-Analysis-for-Loan-Approval/refs/heads/main/source/Missing%20Value.png)

3. **Handling Outliers**
Setelah mengidentifikasi nilai yang hilang, kita melakukan **penanganan outlier** dengan memisahkan kolom menjadi numerik dan kategorikal. Menggunakan metode **Interquartile Range (IQR)**, kita mendeteksi dan menghapus outlier dari kolom numerik. Visualisasi melalui boxplot membantu dalam memahami penyebaran dan dampak outlier. Dengan menghilangkan outlier, kita memastikan bahwa data yang digunakan untuk pemodelan lebih representatif dan akurat.

    ![Outlier Data](https://raw.githubusercontent.com/Rendika7/Predictive-Analysis-for-Loan-Approval/refs/heads/main/source/Outlier.png)

4. **Encoding Fitur Kategori**
Setelah data dibersihkan, langkah selanjutnya adalah melakukan **One-Hot Encoding** untuk fitur kategorikal menggunakan `pd.get_dummies()`, mengubah kategori menjadi variabel biner untuk memudahkan pemodelan.

5. **Feature Scaling**
Kemudian, kita menerapkan **Min-Max Scaling** untuk menormalkan fitur ke rentang [0, 1]. Teknik ini mencegah dominasi fitur dengan skala yang lebih besar dan meningkatkan performa model yang berbasis jarak serta seperti **KNN**, **SVM**, dan **Neural Networks**. 

**Rumus Min-Max Scaling:**

$$
X_{\text{scaled}} = \frac{X - X_{\text{min}}}{X_{\text{max}} - X_{\text{min}}}
$$

- $` X `$ adalah nilai asli.
- $` X_{\text{min}} `$ dan $` X_{\text{max}} `$ adalah nilai minimum dan maksimum fitur.

6. **Splitting Data**
Tahap terakhir dalam persiapan data adalah membagi dataset menjadi fitur (`X`) dan target (`y`), serta membagi dataset menjadi data latih dan data uji (80:20) dengan menjaga distribusi kelas yang seimbang. Penghapusan kolom yang tidak relevan, seperti `ApplicationDate`, dilakukan untuk memastikan hanya fitur yang signifikan yang digunakan dalam analisis.

    ![Splitting Dataset](https://raw.githubusercontent.com/Rendika7/Predictive-Analysis-for-Loan-Approval/refs/heads/main/source/Splitting%20Dataset.png)

Dengan tahapan data processing dan preparation yang sistematis ini, kita dapat meningkatkan kualitas data yang digunakan, meningkatkan akurasi model, dan memastikan bahwa hasil analisis lebih dapat diandalkan.

## Modeling
Tahapan ini membahas mengenai model machine learning yang digunakan untuk menyelesaikan permasalahan klasifikasi. Penelitian ini menggunakan enam model yang berbeda untuk melihat model mana yang memberikan hasil terbaik. Berikut adalah penjelasan mengenai tahapan yang dilakukan dan parameter yang digunakan pada proses pemodelan, serta kelebihan dan kekurangan dari masing-masing algoritma.

### Tahapan Proses Pemodelan
1. **Inisialisasi Model**: Beberapa model digunakan untuk pelatihan, yaitu AdaBoostClassifier, RidgeClassifier, Linear Discriminant Analysis (LDA), Support Vector Machine (SVM) dengan kernel linear, Logistic Regression, dan Quadratic Discriminant Analysis (QDA). Setiap model diinisialisasi tanpa pengaturan parameter yang kompleks pada tahap awal.
  
2. **Pelatihan Model**: Model dilatih menggunakan data pelatihan (`X_train` dan `y_train`). Waktu yang diperlukan untuk pelatihan dicatat untuk setiap model.
  
3. **Evaluasi Model**: Setiap model dievaluasi menggunakan data uji (`X_test` dan `y_test`). Metrik evaluasi yang digunakan meliputi akurasi, presisi, recall, dan F1 Score. Selain itu, confusion matrix digunakan untuk mengevaluasi kesalahan prediksi.

4. **Visualisasi Hasil Evaluasi**: Hasil evaluasi model divisualisasikan menggunakan bar chart untuk perbandingan metrik, serta confusion matrix untuk masing-masing model.

### Model dan Parameternya
Berikut adalah model yang digunakan, parameter yang disetel secara default, serta kelebihan dan kekurangan dari masing-masing algoritma:

1. **AdaBoostClassifier**
   - *Parameter Utama*:
     - `n_estimators`: **50** (Jumlah estimasi dasar yang digunakan)
     - `learning_rate`: **1.0** (Mempertimbangkan kontribusi setiap estimator)
   - *Kelebihan*: Dapat meningkatkan performa model lemah menjadi lebih kuat, robust terhadap overfitting jika parameter disetel dengan baik.
   - *Kekurangan*: Proses pelatihan relatif lambat dibandingkan model yang lebih sederhana, tidak cocok untuk dataset dengan banyak noise.

2. **RidgeClassifier**
   - *Parameter Utama*:
     - `alpha`: **1.0** (Parameter regulasi yang mengontrol kompleksitas model)
   - *Kelebihan*: Sederhana dan cepat dalam hal komputasi, cocok untuk data dengan multikolinearitas.
   - *Kekurangan*: Tidak efektif untuk menangani data yang tidak dapat dipisahkan secara linear.

3. **Linear Discriminant Analysis (LDA)**
   - *Parameter Utama*:
     - `solver`: **'svd'** (Algoritma yang digunakan untuk memecahkan masalah LDA)
     - `priors`: **None** (Menyatakan distribusi a priori dari kelas)
   - *Kelebihan*: Cocok untuk data dengan distribusi normal dan separasi linear, dapat mengurangi dimensi fitur.
   - *Kekurangan*: Sangat sensitif terhadap outlier, kurang efektif untuk data dengan distribusi non-normal.

4. **Support Vector Machine (SVM) dengan Kernel Linear**
   - *Parameter Utama*:
     - `C`: **1.0** (Parameter regulasi yang mengontrol trade-off antara margin yang lebih lebar dan klasifikasi yang lebih akurat)
   - *Kelebihan*: Efektif pada ruang dimensi tinggi, dapat menangani kasus data tidak seimbang.
   - *Kekurangan*: Waktu komputasi cukup lama untuk dataset besar, membutuhkan tuning parameter yang akurat.

5. **Logistic Regression**
   - *Parameter Utama*:
     - `C`: **1.0** (Parameter regulasi yang mengontrol kompleksitas model)
     - `solver`: **'lbfgs'** (Algoritma optimasi yang digunakan)
   - *Kelebihan*: Sederhana, mudah diinterpretasikan, cocok untuk klasifikasi biner.
   - *Kekurangan*: Tidak dapat menangani data yang tidak terpisahkan secara linear, performa menurun jika fitur sangat kompleks.

6. **Quadratic Discriminant Analysis (QDA)**
   - *Parameter Utama*:
     - `reg_param`: **0.0** (Regularization parameter; tidak diterapkan secara default)
   - *Kelebihan*: Baik untuk data dengan distribusi berbeda dan dapat dipisahkan secara kuadratik.
   - *Kekurangan*: Sensitif terhadap outlier, memerlukan jumlah sampel yang cukup banyak untuk mengestimasi parameter distribusi.

### Model Terbaik

Berdasarkan evaluasi metrik yang diukur, **RidgeClassifier** dipilih sebagai model terbaik untuk prediksi persetujuan pinjaman. Berikut alasan pemilihan RidgeClassifier dibandingkan model lainnya:

- **Performansi Metrik Sempurna:** RidgeClassifier memberikan akurasi, precision, recall, dan F1 score sempurna (semua 1.0), menunjukkan tidak ada kesalahan klasifikasi. Hal ini memastikan semua prediksi dibuat dengan tepat, baik untuk persetujuan maupun penolakan pinjaman.

- **Waktu Pelatihan Tercepat:** RidgeClassifier memiliki waktu pelatihan tercepat (0.061 detik) dibandingkan dengan model lain yang juga mencapai akurasi sempurna, seperti AdaBoostClassifier dan Linear Discriminant Analysis (LDA). Waktu pelatihan yang cepat sangat penting untuk efisiensi dan memungkinkan model diperbarui lebih sering tanpa menghabiskan banyak sumber daya.

- **Stabilitas Model:** RidgeClassifier menggunakan regulasi Ridge, yang membantu menghindari overfitting pada data. Hal ini menjadikannya lebih stabil dan andal saat menghadapi dataset yang mungkin mengandung multikolinearitas atau fitur saling terkait.

Dengan performansi metrik sempurna, waktu pelatihan yang paling efisien, dan kemampuan untuk generalisasi yang baik, **RidgeClassifier** adalah pilihan yang paling sesuai untuk digunakan dalam implementasi prediksi persetujuan pinjaman.

## Evaluation

Pada bagian ini, evaluasi model dilakukan menggunakan beberapa metrik untuk memastikan model prediksi persetujuan pinjaman bekerja secara optimal. Metrik evaluasi yang digunakan adalah **accuracy**, **precision**, **recall**, **F1 score**, dan **waktu pelatihan**.

### Penjelasan Metrik yang Digunakan:

1. **Accuracy**: Mengukur proporsi prediksi yang benar dibandingkan dengan total prediksi yang dibuat. Metrik ini menunjukkan seberapa sering model benar dalam memprediksi persetujuan atau penolakan pinjaman.
   - Formula:
     
     $`\text{Accuracy} = \frac{TP + TN}{TP + TN + FP + FN}`$
     
   - **True Positives (TP)** dan **True Negatives (TN)** adalah prediksi yang benar, sedangkan **False Positives (FP)** dan **False Negatives (FN)** adalah prediksi yang salah.

2. **Precision**: Mengukur proporsi prediksi positif yang benar. Precision penting untuk menghindari kesalahan ketika model menyetujui pinjaman, sehingga meminimalkan risiko memberikan pinjaman kepada pemohon dengan risiko gagal bayar.
   - Formula:
     
     $`\text{Precision} = \frac{TP}{TP + FP}`$
     
   - Precision tinggi berarti mayoritas pemohon yang disetujui memang layak untuk diberikan pinjaman.

3. **Recall**: Mengukur kemampuan model dalam mendeteksi semua kasus positif yang sebenarnya. Dalam konteks ini, recall memastikan model tidak melewatkan pemohon yang layak mendapatkan persetujuan.
   - Formula:
     
     $`\text{Recall} = \frac{TP}{TP + FN}`$
     
   - Recall tinggi mengindikasikan model berhasil mengidentifikasi semua pemohon layak dengan benar.

4. **F1 Score**: Merupakan rata-rata harmonis dari precision dan recall. Metrik ini berguna ketika ada trade-off antara precision dan recall, dan memastikan keseimbangan antara mengurangi kesalahan tipe I (false positives) dan tipe II (false negatives).
   - Formula:
     
     $`\text{F1 Score} = 2 \times \frac{\text{Precision} \times \text{Recall}}{\text{Precision} + \text{Recall}}`$
     
   - F1 score digunakan karena penting untuk menjaga keseimbangan antara risiko menyetujui pemohon yang tidak layak dan menolak pemohon yang layak.

5. **Training Time**: Mengukur waktu yang dibutuhkan model untuk menyelesaikan proses pelatihan. Ini penting untuk mempertimbangkan efisiensi komputasi, terutama untuk model yang harus sering diperbarui dengan data baru.

Penggunaan format seperti ini akan lebih mudah dibaca dan ditampilkan dengan baik pada platform yang mendukung format LaTeX untuk rumus matematika.

### Hasil Evaluasi:

![Model Evaluation Metric Comparison](https://raw.githubusercontent.com/Rendika7/Predictive-Analysis-for-Loan-Approval/refs/heads/main/source/Model%20Evaluation%20Metrics%20Comparison.png)

![Confusion Matrix](https://raw.githubusercontent.com/Rendika7/Predictive-Analysis-for-Loan-Approval/refs/heads/main/source/Confusion%20Matrix.png)

![Time Comparison](https://raw.githubusercontent.com/Rendika7/Predictive-Analysis-for-Loan-Approval/refs/heads/main/source/Model%20Training%20Time%20Comparison.png)

Berdasarkan metrik evaluasi yang digunakan, berikut adalah hasil dari masing-masing model:

1. **AdaBoostClassifier**:
   - **Accuracy, Precision, Recall, F1 Score**: 1.0 (semua metrik sempurna).
   - **Confusion Matrix**: Tidak ada kesalahan klasifikasi, yang berarti model memprediksi semua kasus dengan benar.
   - **Training Time**: 1.445 detik. Waktu pelatihan ini cukup lama dibandingkan dengan model lain, yang bisa menjadi kelemahan untuk pembaruan model yang sering.

2. **RidgeClassifier**:
   - **Accuracy, Precision, Recall, F1 Score**: 1.0 (semua metrik sempurna).
   - **Confusion Matrix**: Tidak ada kesalahan klasifikasi.
   - **Training Time**: 0.010 detik, menjadikannya model dengan waktu pelatihan tercepat dan sangat efisien.

3. **Linear Discriminant Analysis (LDA)**:
   - **Accuracy, Precision, Recall, F1 Score**: 1.0 (semua metrik sempurna).
   - **Confusion Matrix**: Tidak ada kesalahan klasifikasi.
   - **Training Time**: 0.049 detik. Waktu pelatihan lebih cepat dibandingkan AdaBoostClassifier tetapi lebih lambat dari RidgeClassifier.

4. **SVM - Linear Kernel**:
   - **Accuracy, Precision, Recall, F1 Score**: 1.0 (semua metrik sempurna).
   - **Confusion Matrix**: Tidak ada kesalahan klasifikasi.
   - **Training Time**: 0.168 detik. Waktu pelatihan lebih lama dibandingkan RidgeClassifier dan LDA.

5. **Logistic Regression**:
   - **Accuracy**: 0.999, **Precision**: 1.0, **Recall**: 0.998, **F1 Score**: 0.999.
   - **Confusion Matrix**: 1 kesalahan klasifikasi pada kelas positif.
   - **Training Time**: 0.056 detik. Meskipun cukup cepat, akurasinya sedikit lebih rendah dibandingkan model lain dengan metrik sempurna.

6. **Quadratic Discriminant Analysis (QDA)**:
   - **Accuracy**: 0.999, **Precision**: 0.995, **Recall**: 1.0, **F1 Score**: 0.998.
   - **Confusion Matrix**: 2 kesalahan klasifikasi pada kelas negatif.
   - **Training Time**: 0.027 detik. Cukup cepat, tetapi akurasi lebih rendah dibandingkan RidgeClassifier dan LDA.

### Kesimpulan Evaluasi Model:

Berdasarkan evaluasi menggunakan accuracy, precision, recall, F1 score, dan waktu pelatihan, **RidgeClassifier** adalah model terbaik untuk prediksi persetujuan pinjaman. Alasan pemilihan ini adalah sebagai berikut:

- **Metrik Evaluasi Sempurna**: RidgeClassifier memberikan nilai sempurna pada semua metrik evaluasi, menunjukkan bahwa tidak ada kesalahan dalam klasifikasi pemohon yang layak atau tidak layak mendapatkan pinjaman.
- **Waktu Pelatihan yang Cepat**: RidgeClassifier memiliki waktu pelatihan tercepat (0.010 detik), menjadikannya sangat efisien untuk implementasi dalam skenario produksi, terutama jika model perlu diperbarui dengan data baru secara berkala.

Dengan performansi sempurna dan efisiensi waktu pelatihan, RidgeClassifier adalah pilihan yang paling tepat untuk digunakan dalam implementasi prediksi persetujuan pinjaman.
