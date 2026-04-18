# Implementasi Teknik Perbaikan Kualitas Citra (Image Enhancement)

Operasi Pemrosesan Citra Digital — Mata Kuliah Pengolahan Citra

---

## Deskripsi Proyek

Image enhancement merupakan proses perbaikan tampilan visual suatu citra agar lebih mudah diinterpretasikan, baik untuk manusia maupun sistem komputer. Tujuannya adalah untuk menonjolkan informasi yang sudah ada namun kurang terlihat, misalnya detail yang tersembunyi akibat pencahayaan buruk, noise, atau kontras yang rendah.

Notebook ini mengimplementasikan tujuh teknik image enhancement menggunakan Python di Google Colab dengan satu gambar bebas sebagai input.

---

## Teknik yang Diimplementasikan

| No | Teknik | Metode |
|----|--------|--------|
| 1 | Pengubahan Kecerahan (Image Brightness) | Penambahan nilai piksel (beta), Transformasi Gamma |
| 2 | Peregangan Kontras (Contrast Stretching) | Rumus linear: s = (r - rmin) / (rmax - rmin) x 255 |
| 3 | Pengubahan Histogram | Histogram Equalization, CLAHE |
| 4 | Pelembutan Citra (Image Smoothing) | Gaussian Filter, Median Filter, Mean Filter |
| 5 | Penajaman Tepi (Sharpening Edge) | Unsharp Masking, Filter Laplacian |
| 6 | Pewarnaan Semu (Pseudocolouring) | Colormap JET, HOT, RAINBOW, OCEAN |
| 7 | Pengubahan Geometrik | Rotasi, Scaling, Flipping, Affine Transform, Koreksi Perspektif |

---

## Struktur Notebook

```
image_enhancement.ipynb
|
|-- Cell 1  : Import Library
|-- Cell 2  : Upload dan tampilkan gambar asli
|-- Cell 3  : Teknik 1 - Pengubahan Kecerahan (Brightness & Gamma)
|-- Cell 4  : Teknik 2 - Peregangan Kontras (Contrast Stretching)
|-- Cell 5  : Teknik 3 - Pengubahan Histogram (HE & CLAHE)
|-- Cell 6  : Teknik 4 - Pelembutan Citra (Smoothing)
|-- Cell 7  : Teknik 5 - Penajaman Tepi (Sharpening Edge)
|-- Cell 8  : Teknik 6 - Pewarnaan Semu (Pseudocolouring)
|-- Cell 9  : Teknik 7 - Pengubahan Geometrik
|-- Cell 10 : Ringkasan semua teknik
```

---

## Library yang Digunakan

```python
opencv-python    # Pengolahan citra utama
numpy            # Operasi array dan matriks
matplotlib       # Visualisasi gambar dan grafik
```

---

## Cara Menjalankan

1. Buka Google Colab di https://colab.research.google.com
2. Upload file notebook image_enhancement.ipynb
3. Jalankan Cell 1 terlebih dahulu untuk mengimpor semua library
4. Jalankan Cell 2, lalu upload satu gambar bebas (format JPG atau PNG) saat diminta
5. Jalankan Cell 3 sampai Cell 10 secara berurutan
6. Setiap cell akan menampilkan hasil visualisasi perbandingan sebelum dan sesudah teknik diterapkan

Catatan: Tidak diperlukan GPU untuk notebook ini. Cukup gunakan runtime CPU standar di Google Colab.

---

## Penjelasan Singkat Tiap Teknik

**1. Pengubahan Kecerahan**
Kecerahan citra ditentukan oleh nilai rata-rata intensitas pikselnya. Pengubahan kecerahan dilakukan dengan dua cara yaitu menambah atau mengurangi nilai intensitas piksel secara seragam, serta menggunakan transformasi gamma dengan rumus s = c x r^gamma untuk hasil yang lebih natural.

**2. Peregangan Kontras**
Teknik untuk memperbaiki citra yang terlihat datar akibat nilai pikselnya tersebar pada rentang sempit. Peregangan kontras memperlebar rentang tersebut ke 0-255 menggunakan rumus linear sehingga perbedaan antara area gelap dan terang menjadi lebih jelas.

**3. Pengubahan Histogram**
Histogram citra menunjukkan distribusi frekuensi nilai intensitas piksel. Histogram Equalization meratakan distribusi secara otomatis, sedangkan CLAHE (Contrast Limited Adaptive Histogram Equalization) bekerja per-blok kecil sehingga hasilnya lebih natural dan cocok untuk citra dengan pencahayaan tidak merata.

**4. Pelembutan Citra**
Teknik untuk menghilangkan noise pada citra. Gaussian Filter menghaluskan citra berdasarkan distribusi Gaussian, Median Filter mengganti nilai piksel dengan median tetangganya dan efektif melawan noise salt-and-pepper, serta Mean Filter merata-ratakan nilai piksel di sekitarnya.

**5. Penajaman Tepi**
Sharpening bertujuan mempertegas batas antar objek dalam citra. Unsharp Masking bekerja dengan mengurangi versi blur dari citra asli lalu menambahkan selisihnya kembali. Filter Laplacian mendeteksi area perubahan intensitas tajam menggunakan turunan kedua dan menambahkannya ke citra asli.

**6. Pewarnaan Semu**
Pseudocolouring adalah pemberian warna buatan pada citra grayscale berdasarkan nilai intensitas pikselnya. Warna yang dihasilkan bukan warna asli objek, melainkan warna yang sengaja diberikan untuk memudahkan interpretasi visual karena mata manusia lebih sensitif membedakan warna dibanding gradasi abu-abu.

**7. Pengubahan Geometrik**
Perubahan geometrik mengubah posisi, orientasi, atau ukuran objek dalam citra tanpa mengubah nilai intensitas pikselnya. Teknik yang diimplementasikan meliputi rotasi, scaling, flipping horizontal dan vertikal, affine transform, serta koreksi perspektif.

---

## Kesimpulan

Perbaikan kualitas citra (image enhancement) bertujuan untuk menonjolkan ciri-ciri tertentu dalam citra agar lebih mudah diinterpretasikan. Terdapat tujuh teknik utama yang diimplementasikan dalam notebook ini. Setiap teknik memiliki fungsi spesifik dan pemilihannya disesuaikan dengan kondisi serta kebutuhan analisis citra.

---

## Referensi

- Gonzalez, R.C. & Woods, R.E. — Digital Image Processing
- OpenCV Documentation: https://docs.opencv.org
- NumPy Documentation: https://numpy.org/doc
- Matplotlib Documentation: https://matplotlib.org/stable/contents.html
