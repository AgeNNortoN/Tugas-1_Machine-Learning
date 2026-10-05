# Tugas-1_Machine-Learning
Tugas 1 UT 
Berikut langkah-langkah dan beberapa poin atau catatan tambahan yang perlu saya sebutkan (untuk pembelajaran sendiri dan pertanyaan untuk tutor pengampu – Ibu Fonda) dalam proses pengerjaan tugas 1 ini:
Tahap 1 yang terdiri dari load dataset (import library dan baca file data + jadikan df) tidak ada masalah atau pertanyaan. 
 

Tahap 2 EDA sepertinya tidak ada masalah. Terdapat nilai hilang dalam data (yang ada null di kolom Umur dan Nilai_Akhir) dan ini harus jadi perhatian karena Nilai_Akhir merupakan data kategorikal ordinal (bertingkat) karena isinya A,B,C dan seterusnya. Juga, tipe data yang digunakan Umur bisa diubah dari FLOAT menjadi Integer mungkin? Nanti dicek kembali. Tipe data untuk Tanggal juga harus diubah karena tidak sesuai tipe datetime. Oh ya, juga cek duplikasi data terlebih dahulu.  

Tahap 3 Saya memutuskan menghilangkan baris yang mengandung Nilai_Akhir NaN, dengan alasan, data yang mendukung memberikan penilaian seperti misal nilai ujian akhir, nilai tugas, nilai absensi dsb tidak ada dalam dataset. Jadi untuk mereplace missing value langsung dengan modus, median atau mean menurut saya akan mengganggu fungsi data itu sendiri. Misal kita menggunakan MODUS untuk menggantikan, maka yang muncul adalah nilai C. Artinya semua nilai 
 
kosong (29 baris) akan diisi dengan nilai C dan itu rasanya akan sangat berdampak pada analisis akhir yang akan dilakukan. Sisa data setelah baris yang mengandung Nilai_Akhir NaN masih layak kuantitasnya dan menurut saya lebih baik dalam menghasilkan analisa (tidak terjadi bias yang membuat kesimpulan  atau hasil melenceng dari analisis data real seharusnya). Untuk Umur cukup mudah, diganti dengan mean (23an) atau Median (23). Karena kita akan menggunakan integer, maka hasil akhirnya tetap 23 dan ini yang akan digunakan untuk mengganti missing value di kolom Umur.
Pada tahap 4 akan dilakukan penggantian format tanggal karena pada kolom Tanggal, terdapat dua format yang bisa mengganggu proses pengenalan bentuk format tanggal. Kolom ini juga memiliki tipe data yang salah, OBJECT, yang seharusnya datetime yakni format penanggalan. CATATAN: Pada ppt inisasi 3 halaman 38-39 terlihat tanggal_lahir_parsed menjadi satu tanggal yang sama (akibatnya tabel tanggal lahirnya hanya 1 bar yang sama). Apa maksudnya? Apakah memang harus begitu? Semua data tanggal dengan format yang salah dijadikan satu tanggal yang sama? Proses ini tidak saya ikuti dan catatan juga punya saya tipe datanya bukan lagi DATETIME melainkan OBJECT jadi akan saya usahakan kembali menjadi datetime.

Tahap 5 Encoding.  
Pada tahap ini dilakukan pengubahan data dari tipe-tipe object menjadi numerik agar bisa diproses oleh algoritma machine learning. Misal: Laki-laki dan perempuan menjadi 0 dan 1. Dari instruksi tugas, dilabelkan beberapa kolom. Yang menjadi catatan dalam hal ini adalah kolom NAMA. Untuk tabel data contoh yang dipakai nama memang hanya terdapat dari beberapa saja. Namun demikian, menurut saya ini tidak natural. Karena pada data asli, tentunya nama yang akan muncul adalah unik sehingga pada data yang sebenarnya, sangat tidak masuk akal untuk melabelkan nama karena misal ada 100ribu siswa dengan 100 ribu nama berbeda, akan muncul 100ribu label yang menganulir fungsi pelabelan itu sendiri. Saya cari di google, istilahnya adalah High Cardinality dan dihindari untuk Machine Learning Algoritma. Namun, karena pada data contoh hanya sedikit label yang ada, hasil tetap saya pertahankan. 

Tahap 6 
	Tahap ini mengambil feature sklearn model selection. Untuk memetakan dan memisahkan 80-20, diperlukan kolom target. Untuk ini saya menggunakan kolom “Status”. Saya asumsikan data test dan data uji yang dihasilkan cukup menggambarkan data. Yang menjadi pertanyaan saya, apakah dengan mentargetkan kolom Status, apakah seharusnya menjadi kolom hasil prediksi dari ML? Maksudnya, misal, dengan memperhitungkan data-data yang ada, maka algoritama ML akhirnya bisa memprediksikan suatu seorang siswa akan memiliki status apa jika diinput data-data yang dibutuhkan. Atau hanya mempersiapkan data train dan test dengan kolom status sebagai target teorinya. Kalau begitu untuk apa dan apa fungsinya untuk kemudian hari?
 
 
Untuk Tahap 7 dibutuhkan import library visualisasi. Langkah ini saya ikuti sebisa mungkin sesuai dengan instruksi dan ajaran di inisiasi UT. 






Demikian proses dan pembelajaran saya selama mengikuti arahan Tugas 1. Mohon masukan dan penilaian dari Tutor pengampu mata kuliah. 

Sebelum dan sesudahnya, saya ucapkan terima kasih yang sebesar-besarnya. 
