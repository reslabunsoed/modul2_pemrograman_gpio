# Percobaan 2: Input dengan Push Button

## 🎯 Tujuan
Fokus percobaan adalah menghubungkan dan mengendalikan rangkaian input (push button) dan output (seven segment) dalam satu sistem terintegrasi.

## 💡 Spesifikasi yang Diharapkan
1.	Tampilan angka pada Seven Segment Display berjalan dengan benar
2.	Push button berfungsi sebagai input control
3.	Fungsi counter berjalan sesuai logika
4.	Tidak terjadi kesalahan tampilan (glitch)

## ♻️ Langkah Percobaan
1. Persiapkan Alat dan Bahan

- Lakukan seperti halnya tugas pendahuluan poin 1
- Pastikan Arduino Uno terhubung dengan komputer

2. Program Percobaan

```cpp
#include <Arduino.h>

// ================= PIN =================
const int segmentPins[8] = {7, 6, 5, 11, 10, 8, 9, 4}; 
// a  b  c  d  e  f  g  dp

const int btnUp = 2;

// ================= DATA =================
// CC: 1 = ON, 0 = OFF
byte digitPattern[16][8] = {
  {1,1,1,1,1,1,0,0}, //0
  {0,1,1,0,0,0,0,0}, //1
  {1,1,0,1,1,0,1,0}, //2
  {1,1,1,1,0,0,1,0}, //3
  {0,1,1,0,0,1,1,0}, //4
  {1,0,1,1,0,1,1,0}, //5
  {1,0,1,1,1,1,1,0}, //6
  {1,1,1,0,0,0,0,0}, //7
  {1,1,1,1,1,1,1,0}, //8
  {1,1,1,1,0,1,1,0}, //9
  {1,1,1,0,1,1,1,0}, //A
  {0,0,1,1,1,1,1,0}, //b
  {1,0,0,1,1,1,0,0}, //C
  {0,1,1,1,1,0,1,0}, //d
  {1,0,0,1,1,1,1,0}, //E
  {1,0,0,0,1,1,1,0}  //F
};

int currentDigit = 0;

// state sebelumnya (untuk edge detection)
bool lastUpState = HIGH;

// ================= FUNCTION =================
void displayDigit(int num)
{
  for(int i=0;i<8;i++)
  {
    digitalWrite(segmentPins[i], digitPattern[num][i]);
  }
}

// ================= SETUP =================
void setup()
{
  for(int i=0;i<8;i++)
  {
    pinMode(segmentPins[i], OUTPUT);
  }

  pinMode(btnUp, INPUT_PULLUP);

  displayDigit(currentDigit);
}

// ================= LOOP =================
void loop()
{
  bool upState = digitalRead(btnUp);

  // ===== UP (maju) =====
  if(lastUpState == HIGH && upState == LOW)
  {
    currentDigit++;
    if(currentDigit > 15) currentDigit = 0;
    displayDigit(currentDigit);
  }

  lastUpState = upState;
}
```

3. Simpan sketch dengan nama file modul1_perulangan
4. Konfigurasi Rangkaian

<img width="940" height="387" alt="image" src="https://github.com/user-attachments/assets/c0221663-a82f-4a28-9632-64709611f175" />

Membuat rangkaian yang menghubungkan pin pada seven segment dengan Pin digital menggunakan breadboard sesuai pada Gambar dengan konfigurasi pin sesuai pada Tabel.

| Segmen | Label | Pin Arduino |
|:------:|:-----:|:-----------:|
| a      | a     | 7           |
| b      | b     | 6           |
| c      | c     | 5           |
| d      | d     | 11          |
| e      | e     | 10          |
| f      | f     | 8           |
| g      | g     | 9           |
| dp     | titik | 4           |

Push button ----- Pin 2

6. Berikutnya compile dan upload program ke dalam Arduino board. Perhatikan dan berikan analisi pada hasil yang terjadi, apakah sesuai dengan spesifikasi atau tidak. Tuliskan di Buku Catatan Praktikum

https://github.com/user-attachments/assets/a77dff1c-3347-441b-a191-2ddefb3af922

## 💡 Pertanyaan Praktikum
1.	Gambarkan rangkaian schematic yang digunakan pada percobaan!
2.	Mengapa pada push button digunakan mode INPUT_PULLUP pada Arduino Uno? Apa keuntungannya dibandingkan rangkaian biasa?
3.	Jika salah satu LED segmen tidak menyala, apa saja kemungkinan penyebabnya dari sisi hardware maupun software?
4.	Modifikasi rangkaian dan program dengan dua push button yang berfungsi sebagai penambahan (increment) dan pengurangan (decrement) pada sistem counter dan berikan penjelasan disetiap baris kode nya dalam bentuk README.md!

<h2></h2>

<br>

[![banner](https://github.com/user-attachments/assets/f1f03032-41c0-4121-94e3-df1d513b42e5)](https://github.com/reslabunsoed/modul2_pemrograman_gpio)
