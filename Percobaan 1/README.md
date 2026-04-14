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

//7-Segment Display (Efficient Version)
//Display 0 - 9 and A - F

// Pin mapping segment
const int segmentPins[8] = {7, 6, 5, 11, 10, 8, 9, 4}; 
// a  b  c  d  e  f  g  dp

// Segment pattern for 0-F
// urutan segmen: a b c d e f g dp
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

// Fungsi menampilkan digit
void displayDigit(int num)
{
  for(int i=0;i<8;i++)
  {
    digitalWrite(segmentPins[i], digitPattern[num][i]);
  }
}

void setup()
{
  for(int i=0;i<8;i++)
  {
    pinMode(segmentPins[i], OUTPUT);
  }
}

void loop()
{
  for(int i=0;i<16;i++)   //0 sampai F
  {
    displayDigit(i);
    delay(1000);
  }
}
```
4. Simpan sketch dengan nama file modul2_output
5. Konfigurasi rangkaian
6. Berikutnya compile dan upload program ke dalam Arduino board. Perhatikan dan berikan analisi pada hasil yang terjadi, apakah sesuai dengan spesifikasi atau tidak.

<h2></h2>

<br>

![banner](https://github.com/user-attachments/assets/f1f03032-41c0-4121-94e3-df1d513b42e5)
