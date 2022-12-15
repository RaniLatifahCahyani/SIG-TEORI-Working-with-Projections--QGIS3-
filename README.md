Langkah Kerja :
Buka QGIS. Pergi ke Layer ‣ Add Layer ‣ Add Vector Layer….
Klik … di sebelah Sumber, Jelajahi file ne_10m_admin_0_countries.shp yang diunduh dan klik Add.
Di bagian bawah jendela QGIS, Anda akan melihat label Coordinate. Saat Anda menggerakkan kursor di atas peta, itu akan menunjukkan kepada Anda koordinat X dan Y di lokasi itu. Di pojok kanan bawah Anda akan melihat EPSG:4326. Ini adalah kode untuk CRS (Projection) saat ini untuk proyek - juga dikenal sebagai Project CRS.
Untuk menentukan proyeksi layer, kita dapat melihat metadata. Klik kanan pada layer ne_10m_admin_0_countries dan pilih Properties.
Beralih ke tab Informasi di dialog Layer Properties. Luaskan bagian Informasi dari penyedia. Di bagian bawah, Anda akan melihat nama proyeksi di bawah CRS.
Sekarang mari kita lihat bagaimana kita dapat mengubah proyeksi layer. Operasi ini disebut Re-Projection. Daripada memproyeksikan ulang seluruh lapisan, kita juga dapat memilih subset fitur dan memproyeksikannya kembali ke lapisan baru. Gunakan alat Select features by area or single click dan klik fitur United Kingdom untuk memilihnya.
Cari dan temukan algoritma Vector General ‣ Proyeksi ulang layer di kotak alat Processing
Pilih ne_10m_admin_0_countries sebagai Input layer, centang Selected features only lalu klik ikon bola dunia di sebelah Target CRS, cari dan pilih EPSG:27700 - OSGB 1936 / British National Grid. Di Diproyeksikan ulang, pilih ... dan klik Simpan ke file. Sekarang pilih direktori dan masukkan nama sebagai united_kingdom.gkpg dan klik Run..
Sebuah layer baru united_kingdom akan muncul di Panel Layer. Seperti yang Anda lihat, kedua lapisan masih sejajar satu sama lain - meskipun mereka berada di CRS yang berbeda. Ini karena QGIS mendukung transformasi CRS On-The-Fly (OTF). Artinya, setiap kali CRS layer tidak cocok dengan Project CRS, maka secara otomatis akan ditransformasikan ke Project CRS sehingga dapat ditampilkan dengan benar. Sekarang mari kita atur Project CRS agar sesuai dengan CRS United_kingdom Layer yang baru dibuat. Hapus layer ne_10m_admin_0_countries dan, klik kanan pada layer united_kingdom Layer CRS ‣ Set Project CRS dari Layer.
Anda akan melihat Project CRS diperbarui ke EPSG:27700.
Sekarang mari kita tambahkan Raster layer. Go to Layer ‣ Add Layer ‣ Add Raster Layer….
Klik pada ... di sebelah Sumber, pilih layer MiniScale_(standard)_R23.tif. Klik Add.
Sekarang layer baru MiniScale_(standard)_R23 ditambahkan ke kanvas.
Untuk membuat kedua layer terlihat, alihkan urutan layer dengan menyeret MiniScale_(standard)_R23 ke bawah di panel Layers.
Klik kanan pada layer MiniScale_(standard)_R23 dan klik Properties.
Di Layer Properties, alihkan ke Information, CRS adalah EPSG:27700 - OSBG 1935 / British National Grid - Projected. Ini menegaskan bahwa CRS lapisan raster sama dengan Project CRS.
