# SIG_Handling-Invalid-Geometries

*Tutorial Handling Invalid Geometries

1. Download terlebih dahulu file India-States.zip 

2. Cari file India-States lalu cari file India-States.shp lalu seret ke kanvas (*Gambar 1*)

3. Kita akan melihat layer India-States pada Layers panel. Klik Processing lalu pilih Toolbox (*Gambar 2*)

4. Kita akan mencoba menjalankan algoritme pemrosesan pada lapisan input untuk mendemonstrasikan bagaimana geometri yang tidak valid dapat menyebabkan masalah selama operasi geoproses. Cari dan temukan Cartography lalu Topological coloeing klik dua kali untuk menampilkannya (*Gambar 3*)

5. Pada Topological coloring, pilih India-States sebagai input layer. Simpan semua parameter lain ke default dan klik Run (*Gambar 4*)

6. Saat algoritme berjalan, kita akan melihat peringatan ditampilkan di tab Log. 1 fitur di lapisan input memiliki geometri yang tidak valid dan dilewati selama pemrosesan. Pengaturan default untuk menangani geometri yang tidak valid di Processing Toolbox lalu  settings, processing, general,pemfilteran fitur yang tidak valid dan diatur ke lewati fitur dengan geomteri yang tidak valid. Ini adalah pengaturan default yang bagus, tetapi jika masukan kita besar, kita mungkin melewatkan peringatan ini dan mungkin tidak mengetahui bahwa fitur masukan telah dilewati. Kita mungkin ingin mengubah nilainya menjadi Hentikan eksekusi algoritme saat geometri tidak valid (*Gambar 5*)

7. Kembali pada halaman utama, kita akan melihat layer baru berwarna ditambahkan ke layers panel. Perhatikan bahwa layer baru tidak memiliki status yang geometrinya tidak valid. Kita sekrang tahu bahwa poligon keadaan tertentu ini memiliki geomteri yang tidak valid tetapi kita tidak tahu apa penyebabnya. Kita dapat dengan mudah mengetahuinya. Cari dan temukan Vector geometry lalu chck validity klik dua kali untuk menampilkannya (*Gambar 6*)

8. Pada Check validity ini, pilih India-States sebagai input layer. Pilih GEOS sebagai method lalu klik Run (*Gambar 7*)

9. Saat algoritme selesai diproses, kita kan melihat 3 layer baru di layer panel. Valid output, invalid output dan error output dan deskripsi kesalahan geometri. KLik kanan dan pilih Open Attribute Table (*Gambar 8*)

10. Kita akan melihat bahwa pesan kesalahannya adalah Ring self-intersection. Pilih baris dan klik tombol Zoom map to selected features. Saat memperbesar kita akan melihat akar penyebab galat geometri (*Gambar 9*)

11. QGIS ada dengan algoritme bawaan untuk memperbaiki kesalahan geomteri secara otomatis. Cari dan temukan Vector geometry lalu Fix geometries dan klik dua kali untuk menampilkannya (*Gambar 10*)

12. Pada Fix Geometries pilih India-States sebagai input layer dan klik Run (*Gambar 11*)

13. Sebuah layer baru Fixed Geometries muncul. Pada titik ini kesalahan geometri telah diperbaiki dan kita dapat menjalankan algoritme pemrosesan apa pun pada lapisan ini tanpa masalah. Tetapi bahwa masih ada celah di antara poligon yang berdekatan yang tidak terduga dan dapat menyebabkan kesalahan topologi di kemudian hari, Kita juga dapat memperbaikinya dengan mengedit poligon. Klik tombol Toggle Editing di Digitizing Toolbar. Pilih vertex tool dan dari drop-down pilih vertex tool(Current Layer). Jika celahnya tidak ada proses ini bisa di skip saja (*Gambar 12*)

14. Saat alat vertex aktif, klik pada vertex untuk memilihnya. Kita dapat menekan tombol Delete untuk menghapus vertex atau menyeretnya untuk memindahkannya. Kita dapat memindahkan vertex sehingga tepi poligon sekarang menyentuh poligon berdekatan. Jika tidak ada celah seperti di gambar proses ini bisa di skip (*Gambar 13*)

15. Setelah selesai, klik tombol Toggle Editing lagi dan klik Save (*Gambar 14*)

16. Mari kita jalankan lagi algoritme Cartography lalu pilih Topological coloring klik dua kali untuk menampilkannya (*Gambar 15*)

17. Pada Topological coloring, pastika kita memilih Fixed Geometries sebagai input layer lalu klik Run (*Gambar 16*)

18. Kita akan melihat algoritme berjalan tanpa kesalahan dan lapisan baru berwarna akan ditambahkan ke layer panel. Perhatikan bahwa algoritme tidak mewarnai layer dengan sendirinya, tetapi bekerja dengan menambahkan kolom baru bernama color_id ke setiap poligon yang dapat digunakan untuk menetapkan warna unik yang berbeda dari poligon yang berdekatan. Pilih layer Colored dan klik tombol Open the Layer Styling Panel (*Gambar 17*)

19. Pilih Categorized renderer dan column color_id sebagai value. Klik Classify. Kita sekarang akan melihat peta berwarna sehingga poligon yang berdekatan memiliki warna yang berbeda (*Gambar 18* *Gambar 19*)
