Teori :

Segmentasi citra adalah proses membagi citra menjadi beberapa bagian yang lebih berarti untuk analisis lebih lanjut. Dalam proyek ini, kita menggunakan segmentasi warna untuk mengisolasi objek tertentu dari latar belakang, seperti mangga dan daun pada gambar. Metode segmentasi warna menggunakan ruang warna HSV (Hue, Saturation, Value) sangat efektif karena memisahkan informasi warna dari intensitas, yang memudahkan untuk membuat masker warna.

Tahapan Cara Menyelesaikan Proyek :

1. Membaca dan Menampilkan Gambar Asli:
Gambar dibaca menggunakan cv2.imread dan dikonversi ke format RGB menggunakan cv2.cvtColor. Hal ini dilakukan karena OpenCV membaca gambar dalam format BGR, sedangkan Matplotlib menampilkan gambar dalam format RGB.

2. Mengonversi Gambar ke Format HSV:
Gambar dikonversi ke format HSV (Hue, Saturation, Value) menggunakan cv2.cvtColor. Ruang warna HSV memisahkan informasi warna (Hue) dari intensitas (Value), membuat segmentasi warna lebih mudah dan lebih efektif.

3. Membuat Masker untuk Mangga:
Masker dibuat berdasarkan range warna kuning yang sesuai dengan warna mangga. Range ini ditentukan dengan dua array numpy: lower_yellow dan upper_yellow.
Fungsi cv2.inRange digunakan untuk membuat masker, yang menghasilkan gambar biner di mana piksel dalam range warna kuning ditandai dengan nilai 255 (putih) dan piksel lainnya dengan nilai 0 (hitam).

4. Membuat Masker untuk Daun:
Proses yang sama seperti untuk mangga diterapkan untuk daun, dengan menentukan range warna hijau menggunakan lower_green dan upper_green.

5. Segmentasi Mangga:
Segmentasi dilakukan dengan menggunakan fungsi cv2.bitwise_and, yang menggabungkan gambar asli dengan masker. Hanya bagian gambar yang sesuai dengan masker (mangga) yang akan ditampilkan dalam gambar hasil segmentasi.

6. Segmentasi Daun:
Proses segmentasi yang sama diterapkan untuk daun menggunakan masker hijau.

Jurnal Terkait :

1. "Image Segmentation Techniques: A Survey" - Artikel ini memberikan tinjauan komprehensif tentang berbagai teknik segmentasi citra, termasuk segmentasi berdasarkan warna yang kita gunakan.
-Link: IEEE Xplore

2. "Color Image Segmentation: A State-of-the-Art Survey" - Artikel ini mengulas berbagai metode segmentasi warna dan aplikasinya.
-Link: SpringerLink