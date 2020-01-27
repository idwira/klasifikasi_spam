# klasifikasi_spam
Klasifikasi spam dengan pre-processing sederhana

I. Rumusan Masalah

Diberikan data pesan sejumlah 5572 record pesan singkat (sms), dimana sudah dilabeli apakah pesan tersebut termasuk:
-	Spam dan
-	Ham (bukan spam)
Bagaimana membuat model pemrosesan Bahasa yang dapat mengenali pola apakah suatu pesan itu spam atau ham.

II. Garis Besar Pemodelan

Akan digunakan NLTK untuk memproses pesan, pandas untuk mengambil data, pre-processing dengan NLTK stopwords (menghilangkan kata-kata yang tidak menambah makna) dan nopunctuation (menghilangkan tanda baca), eekstraksi fitur dengan CountVectorizer (mengubah teks menjadi vector) dan TfIdfTransformer (bobot kata), matplotlib untuk visualisasi. Training dengan classifier MultinomialNB.

