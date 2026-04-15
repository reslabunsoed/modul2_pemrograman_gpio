# Percobaan 2: Perulangan

## 🎯 Tujuan
Fokus percobaan adalah memahami penggunaan perulangan (for) untuk mengontrol LED berdasarkan kondisi tertentu.

## 💡 Spesifikasi yang Diharapkan
1)	Kongfigurasi pin sesuai dengan petunjuk praktikum pada bagian langkah percobaan
2)	LED menyala secara berurutan dari kiri ke kanan 
3)	Setelah LED terakhir, arah berubah ke kanan ke kiri 
4)	Pola berjalan terus menerus tanpa error 
5)	Tidak ada LED yang mati atau tidak sesuai urutan

## ♻️ Langkah Percobaan
1. Persiapkan Alat dan Bahan

a.	Lakukan seperti halnya tugas pendahuluan poin 1
b.	Pastikan Arduino Uno terhubung dengan komputer

2. Program Percobaan

```cpp
// ===============================
// PRAKTIKUM: Running LED dengan For Loop
// ===============================

// TODO: Tentukan nilai delay (semakin besar, semakin lambat)
// int timer = ...;

void setup() {
  // TODO: Gunakan perulangan for untuk inisialisasi pin LED
  // Rentang pin: dari pin ... sampai pin ...
  
  // for (int ledPin = ...; ledPin < ...; ledPin++) {
  //   pinMode(ledPin, ...);   // set sebagai OUTPUT
  // }
}

void loop() {
  // =========================
  // BAGIAN 1: LED dari kiri ke kanan
  // =========================
  
  // TODO: Buat perulangan dari pin kecil ke besar
  // for (int ledPin = ...; ledPin < ...; ledPin++) {
    
    // TODO: Nyalakan LED
    // digitalWrite(ledPin, ...);
    
    // TODO: Beri delay
    // delay(...);
    
    // TODO: Matikan LED
    // digitalWrite(ledPin, ...);
  // }

  // =========================
  // BAGIAN 2: LED dari kanan ke kiri
  // =========================
  
  // TODO: Buat perulangan dari pin besar ke kecil
  // for (int ledPin = ...; ledPin >= ...; ledPin--) {
    
    // TODO: Nyalakan LED
    // digitalWrite(ledPin, ...);
    
    // TODO: Beri delay
    // delay(...);
    
    // TODO: Matikan LED
    // digitalWrite(ledPin, ...);
  // }
}
```

3. Simpan sketch dengan nama file modul1_perulangan
4. Konfigurasi Rangkaian

Membuat rangkaian yang menghubungkan 5 buah LED dengan Pin digital menggunakan breadboard sesuai pada Gambar 1.1 dengan konfigurasi pin sesuai pada Tabel berikut:

| No | Komponen | Pin    |
|----|----------|--------|
| 1  | LED 1    | Pin 2  |
| 2  | LED 2    | Pin 3  |
| 3  | LED 3    | Pin 4  |
| 4  | LED 4    | Pin 5  |
| 5  | LED 5    | Pin 6  |
| 6  | LED 6    | Pin 7  |
| 7  | GND      | GND    |

6. Berikutnya compile dan upload program ke dalam Arduino board. Perhatikan dan berikan analisi pada hasil yang terjadi, apakah sesuai dengan spesifikasi atau tidak. Tuliskan di Buku Catatan Praktikum

## 💡 Pertanyaan Praktikum
1)	Gambarkan rangkaian schematic 5 LED running yang digunakan pada percobaan!
2)	Jelaskan bagaimana program membuat efek LED berjalan dari kiri ke kanan!
3)	Jelaskan bagaimana program membuat LED kembali dari kanan ke kiri!
4)	Buatkan program agar LED menyala tiga LED kanan dan tiga LED kiri secara bergantian dan berikan penjelasan disetiap baris kode nya dalam bentuk README.md!

<h2></h2>

<br>

[![banner](https://github.com/user-attachments/assets/f1f03032-41c0-4121-94e3-df1d513b42e5)](https://github.com/reslabunsoed/modul2_pemrograman_gpio)
