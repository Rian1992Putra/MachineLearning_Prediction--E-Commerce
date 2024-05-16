# MachineLearning_Prediction--E-Commerce

# Business Problem Understanding
**Latar Belakang**


Sebuah perusahaan yang bergerak dibidang e-commerce menghadapi berbagai tantangan untuk tetap mempertahankan atau bahkan meningkatkan revenue. Tantangan tersebut diantaranya adalah **meningkatkan retensi pelanggan** karena ditemukannya sejumlah pelanggan yang berhenti bertransaksi. Maka dari itu perusahaan ingin mengetahui pelanggan mana sajakah yang terindikasi akan berhenti bertransaksi serta memahami karakteristik pelanggan dalam bertransaksi. Sehingga perusahaan dapat membuat kebijakan yang tepat dan efisien untuk mengatasi tantangan yang ada.


**Rumusan Masalah :**

Permasalahan yang perlu diatasi adalah **bagaimana upaya perusahaan dalam meningkatkan retensi pelanggan secara efektif dan efisien**. **Adapun untuk meningkatkan retensi pelanggan dapat dilakukan dengan mencegah pelanggan untuk churn**. Hal tersebut menjadi penting mengingat perbandingan biaya yang diperlukan untuk mendapatkan **pelanggan baru adalah 5 kali lebih besar dibanding biaya yang dibutuhkan untuk mempertahankan pelanggan yang ada**. Namun bila seluruh sumber daya digunakan untuk semua pelanggan tanpa membedakan pelanggan yang akan churn atau tidak, maka penggunaan sumber daya tidak akan efektif dan efisien. 

Target :

0 : Pelanggan yang masih bertransaksi/tidak churn

1 : Pelanggan yang berhenti bertransaksi/churn

**Goal :**

Untuk dapat menjawab permasalahan yang ada maka tujuan dari proyek ini yaitu : 

- Untuk **memahami karakteristik pelanggan yang berpotensi akan churn** sehingga kebijakan yang dibuat dapat lebih terarah. Adapun business questions atau pertanyaan bisnis yang perlu dijawab untuk dapat memahami karakteristik pelanggan tersebut diantaranya :

    1. Bagaimana karakteristik pelanggan berdasarkan **informasi personalnya** (jenis kota, status pernikahan, kelamin, jenis perangkat, jenis pembayaran, jenis produk favorit dan durasi penggunaan aplikasi/web aplikasi) ?

    2. Bagaimana karakteristik pelanggan berdasarkan **tingkat kepuasannya** (rating, keluhan) ?

    3. Bagaimana karakteristik pelanggan berdasarkan **riwayat transaksi & promosi** yang didapatkan (lamanya terdaftar, peningkatan jumlah pembelian, jumlah pembelian, penggunaan kupon, penerimaan cashback, jumlah hari setelah hari terakhir pembelian) ?

- Selain itu perusahaan juga ingin **memiliki kemampuan untuk memprediksi pelanggan yang akan churn** sehingga perusahaan khususnya tim marketing dapat membuat strategi untuk meningkatkan retensi pelanggan secara efektif dan efisien.


**Pendekatan Analisis :**

Melakukan analisis data untuk menemukan **karakteristik pelanggan yang berpotensi akan churn**. Selanjutnya adalah **membuat model klasifikasi yang akan membantu perusahaan untuk dapat memprediksi** kemungkinan pelanggan akan churn atau tidak.


**Metrik Evaluasi :**

Sebelum menentukan metrik evaluasi yang akan digunakan, sebaiknya perlu memperhatikan jenis _erorr_ yang dapat timbul dari pemodelan prediksi yaitu :

**False Positive**  : Pelanggan yang diprediksi akan berhenti melakukan transaksi tetapi kenyataannya tetap bertransaksi. Konsekuensinya adalah alokasi sumber daya yang tidak efektif dan efisien (contoh = pemberian diskon tidak tepat sasaran mengakibatkan sumber daya terbuang sia-sia).

**False Negative**  : Pelanggan yang diprediksi akan tetap melakukan transaksi tetapi kenyataannya berhenti bertransaksi. Konsekuensinya adalah kehilangan jumlah pelanggan yang akan berdampak pada penurunan revenue.

Karena fokus perusahaan adalah mempertahankan pelanggan secara efektif dan efisien dimana **meminimalisir false positive dan false negative sekecil mungkin tetapi lebih difokuskan pada recall** maka metrik yang digunakan adalah **f2-score**.

untuk gambaran kuantitatifnya secara umum adalah :
- Costumer Acquisition Cost (CAC) berdasarkan referensi https://firstpagesage.com sebesar 65 USD per orang<sup>[1]</sup>,
- Costumer Retention Cost (CRC) berdasarkan https://www.forbes.com bisa berkisar 20% dari CAC<sup>[2]</sup>, maka simulasi untuk CRC adalah :   20% dari 65 USD (CAC) = 13 USD per pelanggan.

Adapun pengertian dari tiap-tiap metrik evaluasi model klasifikasi yaitu :
- **F1-Score** : ukuran yang menggabungkan Precision dan Recall menjadi satu angka tunggal. Ini memberikan gambaran keseluruhan tentang kinerja model dalam mengklasifikasikan kelas positif, dengan mempertimbangkan baik false positives maupun false negatives.
- **F2-Score** : ukuran yang menggabungkan Precision dan Recall menjadi satu angka tunggal tetapi lebih ditekankan pada Recall.
- **Recall** : merupakan rasio prediksi benar positif dibandingkan dengan keseluruhan data yang benar positif. Ini berguna ketika Anda ingin meminimalkan false negatives.
- **Precision** : merupakan rasio prediksi benar positif dibandingkan dengan keseluruhan data yang diprediksi positf. Ini berguna ketika Anda ingin meminimalkan false positives.

