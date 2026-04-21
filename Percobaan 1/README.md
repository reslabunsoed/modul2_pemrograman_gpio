# Percobaan 1: Seven Segment Display

## 🎯 Tujuan
Fokus percobaan adalah merancang rangkaian seven segment 1 byte sebagai counter untuk menampilkan 0 -9 dan A – F. Rangkaian wiring untuk seven segment ke pin Arduino Uno seperti yang ditunjukkan pada gambar.

<img width="940" height="387" alt="image" src="https://github.com/user-attachments/assets/879be078-beca-4a55-adc3-d57266af05d0" />

## 💡 Spesifikasi yang Diharapkan
1.	Kongfigurasi pin sesuai dengan petunjuk praktikum pada bagian langkah percobaan
2.	Display hex 0 – 9 dan A – F ditampilkan secara berurutan
3.	Pola berjalan terus menerus tanpa error 
4.	Tidak ada LED yang mati atau tidak sesuai urutan

## ♻️ Langkah Percobaan
1. Persiapkan alat dan bahan
- Lakukan seperti halnya tugas pendahuluan poin
- Pastikan Arduino Uno terhubung dengan komputer

2. Program percobaan

```cpp
#include <Arduino.h>

// ==========================================
// PRAKTIKUM: 7-Segment Display (0 - F)
// ==========================================
// Tujuan:
// - Mahasiswa memahami cara mengontrol 7-segment
// - Mahasiswa dapat menampilkan angka 0–9 dan huruf A–F

// -------------------------------
// TODO 1:
// Tentukan pin untuk masing-masing segmen
// Urutan segmen: a, b, c, d, e, f, g, dp
// Contoh: {7, 6, 5, ...}
// -------------------------------
const int segmentPins[8] = {
  // isi di sini
};


// -------------------------------
// TODO 2:
// Lengkapi pola untuk menampilkan
// angka 0 - 9 dan huruf A - F
//
// Format:
// 1 = LED segmen ON
// 0 = LED segmen OFF
//
// Urutan: a b c d e f g dp
//
// Contoh angka 0:
// {1,1,1,1,1,1,0,0}
// -------------------------------
byte digitPattern[16][8] = {

  // 0
  { /* isi */ },

  // 1
  { /* isi */ },

  // 2
  { /* isi */ },

  // 3
  { /* isi */ },

  // 4
  { /* isi */ },

  // 5
  { /* isi */ },

  // 6
  { /* isi */ },

  // 7
  { /* isi */ },

  // 8
  { /* isi */ },

  // 9
  { /* isi */ },

  // A
  { /* isi */ },

  // b
  { /* isi */ },

  // C
  { /* isi */ },

  // d
  { /* isi */ },

  // E
  { /* isi */ },

  // F
  { /* isi */ }

};


// -------------------------------
// TODO 3:
// Lengkapi fungsi untuk menampilkan digit
// Gunakan perulangan untuk mengakses setiap segmen
// -------------------------------
void displayDigit(int num)
{
  for(int i = 0; i < 8; i++)
  {
    // tulis logika untuk menyalakan/mematikan segmen
    // menggunakan digitalWrite()
  }
}


// -------------------------------
// SETUP
// -------------------------------
void setup()
{
  // TODO 4:
  // Set semua pin segment sebagai OUTPUT
}


// -------------------------------
// LOOP
// -------------------------------
void loop()
{
  // TODO 5:
  // Tampilkan angka dari 0 sampai F
  // Gunakan perulangan (for)

  // TODO 6:
  // Tambahkan delay agar perubahan terlihat
}
```
3. Simpan sketch dengan nama file modul2_output
4. Konfigurasi rangkaian

Membuat rangkaian yang menghubungkan pin pada seven segment dengan Pin digital menggunakan breadboard

📊 Mapping Pin 7-Segment ke Arduino

| Segmen | Label | Pin Arduino |
|--------|-------|------------|
| a      | a     | 7          |
| b      | b     | 6          |
| c      | c     | 5          |
| d      | d     | 11         |
| e      | e     | 10         |
| f      | f     | 8          |
| g      | g     | 9          |
| dp     | titik | 4          |

5. Berikutnya compile dan upload program ke dalam Arduino board. Perhatikan dan berikan analisi pada hasil yang terjadi, apakah sesuai dengan spesifikasi atau tidak.

## 🚀 Pertanyaan Praktikum
1.	Gambarkan rangkaian schematic yang digunakan pada percobaan!
2.	Apa yang terjadi jika nilai num lebih dari 15?
3.	Apakah program ini menggunakan common cathode atau common anode? Jelaskan alasanya!
4.	Modifikasi program agar tampilan berjalan dari F ke 0 dan berikan penjelasan disetiap baris kode nya dalam bentuk README.md!

<h2></h2>

<br>

[![banner](https://github.com/user-attachments/assets/f1f03032-41c0-4121-94e3-df1d513b42e5)](https://github.com/reslabunsoed/modul2_pemrograman_gpio)
