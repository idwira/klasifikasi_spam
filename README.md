# klasifikasi_spam
Klasifikasi spam dengan pre-processing sederhana

I. Rumusan Masalah

Diberikan data pesan sejumlah 5572 record pesan singkat (sms), dimana sudah dilabeli apakah pesan tersebut termasuk:
-	Spam dan
-	Ham (bukan spam)

Bagaimana membuat model pemrosesan Bahasa yang dapat mengenali pola apakah suatu pesan itu spam atau ham.

II. Garis Besar Pemodelan

Akan digunakan NLTK untuk memproses pesan, pandas untuk mengambil data, pre-processing dengan NLTK stopwords (menghilangkan kata-kata yang tidak menambah makna) dan nopunctuation (menghilangkan tanda baca), eekstraksi fitur dengan CountVectorizer (mengubah teks menjadi vector) dan TfIdfTransformer (bobot kata), matplotlib untuk visualisasi. Training dengan classifier MultinomialNB.

III.	Temuan Awal as-is (kondisi data apa adanya)

Setelah penghilangan kolom-kolom unnamed dan rename dari judul kolom, deskripsi dari data, ditemukan ada 34 pesan yang redundant (0.6%), yang ideal nya dihapus. Tapi karena relative kecil, dalam pengerjaan model ini, data asli tidak diubah sama sekali.

Sebelum di proses lebih jauh, menarik untuk dilihat apakah ada korelasi antara Panjang pesan dan klasifikasi nya sebagai spam atau bukan. Hasil temuan, bahwa pesan spam memiiki kecenderungan lebih panjang pesannya.

IV.	Pre-Process

Menghilangkan tanda baca (punctuation), menghilangkan stopwords (kata yang tidak menambah makna), lalu melihat hasil nya. Hasil stopwords dan no-punctuation ditampilkan (lima records awal), data sudah relative bersih, tanpa tanda baca dan stopwords.

V.	Split Data Training-Test dan Ekstraksi Fitur

Ditentukan 30% data untuk test, sisa 70% adalah data training nya. Ekstraksi fitur dengan countvectorizer (mengubah fitur teks menjadi representasi vector), dan TfIdfTransformer (menentukan bobot kata dari bag of words). Training dengan MultinomialNB yang umum dipakai untuk klasifikasi kelas biner (spam atau ham).

VI.	Hasil Training dan Tingkat Akurasi

Model sudah mencapai akurasi di atas 95%. Confusion Matrix dari test-data, hanya 71 pesan (dari 1672 data training) yang salah di deteksi sebagai spam padahal bukan spam. Didapat tingkat akurasi 95.754%

VII.	Percobaan Output Deteksi Data Secara Random (Spam atau Ham)

Dari empat pesan, semua nya tepat dideteksi, baik sebagai spam dan bukan spam.

VIII. Kesimpulan

Pemodelan spam filtering secara sederhana dengan MultinomialNB sudah menghasilkan tingkat akurasi yang cukup tinggi, paling tidak untuk dataset yang dipakai ini. Butuh untuk dibuktikan untuk diuji di dataset yang lebih besar, juga hasil temuan bahwa banyak pesan (sms) yang merupakan template seperti “I’ll call you later” yang lazim di pesan singkat bisa dihilangkan (dihapus) dahulu untuk mendapat tingkat akurasi yang lebih reliable.
