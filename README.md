# Modul 2 : Pemrograman Input Output 

## 🎯 Tujuan Praktikum
Berikut ini adalah tujuan praktikum pada Modul Praktikum 2:
- Membuat program dengan teknik loop dalam arduino untuk control input dan output pin arduino
- Merangkai rangkaian input dan output dengan arduino.
- Mengendalikan LED dalam Seven Segment dan penggunaan Push Button

## 📄 Dasar Teori
GPIO (General Purpose Input/Output) adalah salah satu fitur penting dalam pengembangan proyek elektronik dan pemrograman mikrokontroler. Pada Arduino, fungsi GPIO memungkinkan pengguna untuk melakukan interaksi langsung dengan lingkungan sekitar, seperti membaca data dari sensor, mengoperasikan motor maupun menyalakan LED. GPIO adalah pin pada mikrokontroler atau komputer papan tunggal (seperti Raspberry Pi) yang dapat dikonfigurasi sebagai input atau output sesuai kebutuhan pengguna. Pin-pin ini tidak memiliki fungsi khusus bawaan, sehingga disebut "general purpose" (serbaguna).

Pada mikrokontroler Arduino berbasis ATmega, setiap pin secara default berada dalam mode input setelah sistem dinyalakan. Oleh karena itu, tidak selalu diperlukan pemanggilan fungsi pinMode() untuk menetapkannya sebagai input.

Pada tahap ini, kita mulai menyalakan LED menggunakan program dengan memberikan logika HIGH (5V) pada Pin 11. Selanjutnya, program tersebut akan diubah sehingga LED tidak hanya menyala terus, tetapi juga dapat berkedip. Untuk itu, kita perlu memahami konsep keluaran digital pada Arduino.

Arduino Uno memiliki 20 pin GPIO seperti ditunjukkan pada Gambar 2.1 yang dapat digunakan untuk menerima atau mengirim sinyal digital, yaitu HIGH dan LOW. Sinyal ini dikendalikan melalui fungsi digitalRead() untuk membaca dan digitalWrite() untuk menulis nilai digital.

Walaupun pin digital lain juga bisa digunakan, Pin 11 dipilih agar konsisten dengan pelajaran selanjutnya, sehingga proses belajar menjadi lebih sederhana dan tidak membingungkan.

<div align="center">
  <img width="762" height="390" alt="image" src="https://github.com/user-attachments/assets/e73024ad-a8cf-4a62-b723-8dcdbe40e2ea" />
</div>

Anda dapat mengendalikan salah satu dari 20 pin digital I/O tersebut dengan menggunakan tiga fungsi berikut:
- ```pinMode(int pin, int mode)```. Fungsi ini digunakan untuk mengatur sebuah pin agar berfungsi sebagai INPUT atau OUTPUT. Dalam kasus ini, kita memilih OUTPUT karena kita ingin mengirimkan sinyal untuk menyalakan LED.
- ```digitalRead(int pin)```. Fungsi ini digunakan untuk membaca sinyal digital dari pin tertentu, yaitu HIGH atau LOW. Fungsi digitalRead akan dibahas lebih lanjut pada seri pelajaran pengantar input.
- ```digitalWrite(int pin, int value)```. Fungsi ini digunakan untuk mengirimkan sinyal digital ke pin tertentu, yaitu HIGH atau LOW.

Pada pelajaran ini, kita akan menggunakan fungsi ```digitalWrite()```.

### Bagaimana kita menghitung 20 pin I/O digital?

Pada Arduino Uno dan Leonardo, tulisan dan label pada papan sering membuat kita mengira hanya ada 14 pin digital. Padahal, jika dilihat secara keseluruhan, terdapat 20 pin digital I/O yang bisa digunakan. Untuk memastikan hal ini, kita dapat melihat diagram pinout resmi Arduino Uno pada Gambar yang menunjukkan semua pin yang tersedia.

<img width="940" height="509" alt="image" src="https://github.com/user-attachments/assets/3a4ae551-4e7d-429f-9aef-abb37e304a53" />

Untuk lebih jelasnya, berikut pin I/O digtial dan analog seperti yang ditunjukkan pada Gambar berikut

<img width="940" height="512" alt="image" src="https://github.com/user-attachments/assets/7d009840-9bdb-4f97-8ba9-ea5eac5c599c" />

### LED Blink Dengan Arduino Uno

Dalam dunia Embedded System, LED Blink menjadi pemrograman bagi yang pertama kali memasuki dunia Embedded System atau LED Blink merupakan "Hello World" nya Embedded System.

```cpp
const int ledPin = 8;
void setup()
{
  pinMode(ledPin, OUTPUT);
}

void loop()
{
  digitalWrite(ledPin, HIGH);
  delay(1000); // Wait for 1000 millisecond(s)
  digitalWrite(ledPin, LOW);
  delay(1000); // Wait for 1000 millisecond(s)
}
```

https://github.com/user-attachments/assets/d603646f-599c-4296-86f5-40df84c39872

## 🚀 Tugas Pendahuluan

- Membuat semua program (source code) yang diperlukan untuk masing-masing percobaan (sertakan keterangan-keterangan penting pada source code menggunakan komentar); Jelaskan masing-masing baris atau bagian kode tersebut.
- Menyiapkan rangkaian hardware untuk percobaan (sudah dirangkai, sehingga saat percobaan langsung menjalankan program yang telah dibuat). Sertakan pada tugas pendahuluan dalam bentuk foto yang juga menampilkan wajah Anda. (Dilakukan untuk masing-masing percobaan; Sebelum praktikum, cukup siapkan untuk percobaan pertama saja jika space pada breadboard terbatas)

## ⚙️ Alat dan Bahan

Dalam percobaan sederhana ini, berikut alat dan bahan yang digunakan:

<div align="center">
<table border="1" cellpadding="10" cellspacing="0" width="100%">
  <tr>
    <th>Arduino</th>
    <th>Seven Segment Dispaly</th>
    <th>Breadboard</th>
    <th>Kabel Jumper</th>
    <th>Push Button</th>
  </tr>

  <tr align="center">
    <td>
      <img width="192" height="136,1" alt="arduino_uno" src="https://github.com/user-attachments/assets/3e61e208-bb23-42aa-bbef-0ac539279ce0" /><br>
    </td>
    <td>
      <img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/42b8435b-06d7-4f68-a1f0-be5326f7901a" />
    </td>
    <td>
      <img width="500" height="326" alt="breadboard" src="https://github.com/user-attachments/assets/c4bc7843-4387-4289-863c-2634ceafd131" />
    </td>
    <td>
      <img width="250" height="250" alt="image" src="https://github.com/user-attachments/assets/e0dce381-e5f0-4754-84cc-31c2d8d692fd" />
    </td>
    <td>
      <img width="297" height="297" alt="image" src="https://github.com/user-attachments/assets/0f9dd1a0-ae6e-42f4-b42d-74e9f4c0871a" />
    </td>
  </tr>

  <tr align="center">
    <td>Arduino Uno</td>
    <td>Seven Segment Display</td>
    <td>Breadboard Mini</td>
    <td>Jumper Male to Male</td>
    <td>Push Button Tactical</td>
  </tr>
</table>
</div>

## 💻 Percobaan
<h3><a href="Percobaan 1">Percobaan 2A: Seven Segment Display</a></h3>

Seven Segment Display memiliki 7 Segmen dimana setiap segmen dikendalikan secara ON dan OFF untuk menampilkan angka yang diinginkan. Angka-angka dari 0 (nol) sampai 9 (Sembilan) dapat ditampilkan dengan menggunakan beberapa kombinasi Segmen. Selain 0 – 9, Seven Segment Display juga dapat menampilkan Huruf Hexadecimal dari A sampai F. Segmen atau elemen-elemen pada Seven Segment Display diatur menjadi bentuk angka “8” yang agak miring ke kanan dengan tujuan untuk mempermudah pembacaannya. Pada beberapa jenis Seven Segment Display, terdapat juga penambahan “titik” yang menunjukan angka koma decimal. Terdapat beberapa jenis Seven Segment Display, diantaranya adalah Incandescent bulbs, Fluorescent lamps (FL), Liquid Crystal Display (LCD) dan Light Emitting Diode (LED).

Terdapat 2 Jenis LED 7 Segment, diantaranya adalah “LED 7 Segment common Cathode” dan “LED 7 Segment common Anode” seperti pada Gambar

<img width="940" height="503" alt="image" src="https://github.com/user-attachments/assets/adaa65da-a3b9-4fa3-be68-cd1e894e7655" />

Menghubungkan kaki-kaki Seven Segment ke Ground dan VCC dari Arduino

https://github.com/user-attachments/assets/bcbaa2a8-cac5-4ad5-bf02-c060824722c4

<h3><a href="Percobaan 2">Percobaan 2B: Kontrol Counter Dengan Push Button</a></h3>
Push button adalah sebuah komponen yang menghubungkan dua titik dalam rangkaian ketika ditekan. Sebuah pushbutton memiliki setidaknya dua kontak, yang akan menutup atau membuka rangkaian ketika tombol ditekan. Biasanya sebuah pegas akan mengembalikan tombol ke posisi semula ketika tekanan dilepaskan. 

<div align="center">
  <img width="814" height="240" alt="image" src="https://github.com/user-attachments/assets/27cdf371-89ca-46f2-891b-697e61147b9b" />
</div>

Ketika pushbutton dalam keadaan terbuka (tidak ditekan), tidak ada hubungan antara dua kaki pushbutton, sehingga pin terhubung ke 5 volt (melalui resistor pull-up) dan kita membaca kondisi HIGH. Ketika tombol ditekan (tertutup), pushbutton membuat hubungan antara kedua kakinya, sehingga pin terhubung ke ground, dan kita membaca kondisi LOW (Pin tersebut sebenarnya masih terhubung ke 5 volt, tetapi karena ada resistor di antaranya, maka pin menjadi “lebih dekat” ke ground.)

Kendali LED dengan menggunakan Push Button. Pada dasarnya Push Button adalah komponen momentary yang berarti hanya bekerja saat ditekan, dan akan kembali ke posisi semula saat dilepaskan. Namun dengan program Arduino dapat dimanipulasi fungsi dari push button menjadi Toggle yang mengunci posisi (on/off) setiap kali ditekan.

```cpp
/*
  Praktikum GPIO Input dengan Push Button

  Program ini membaca input dari push button dan
  mengontrol LED berdasarkan kondisi tombol.
*/

#define BTN_PIN 3     // Mendefinisikan pin tombol pada pin digital 3
#define ledPin 12     // Mendefinisikan pin LED pada pin digital 12

void setup()
{
  pinMode(ledPin, OUTPUT);   // Mengatur pin LED sebagai output
  pinMode(BTN_PIN, INPUT);   // Mengatur pin tombol sebagai input (butuh resistor eksternal)
}

void loop()
{
  // Membaca kondisi tombol
  // Jika tombol ditekan (HIGH), maka kondisi di dalam if akan dijalankan
  if(digitalRead(BTN_PIN))
  {
    // Membaca kondisi LED saat ini, lalu dibalik (toggle)
    // Jika sebelumnya HIGH (nyala) → jadi LOW (mati)
    // Jika sebelumnya LOW (mati) → jadi HIGH (nyala)
    digitalWrite(ledPin, !digitalRead(ledPin));

    // Delay 500 ms untuk mencegah pembacaan berulang terlalu cepat
    // (berfungsi sebagai debounce sederhana)
    delay(500);
  }
}
```

https://github.com/user-attachments/assets/8eb97c45-85ce-40b7-8cfd-cd6f978b9f37

## 📚 Pertanyaan Praktikum

## 🧰 Mengakhiri Percobaan

Berikut hal yang perlu dilakukan setelah selesai praktikum:
- Sebelum keluar dari ruang praktikum, pastikan meja dalam keadaan rapi.
- Jangan lupa untuk mendokumentasikan dalam bentuk foto dan video serta diunggah lewat google drive dan sertakan tautan dokumentasi tersebut di Buku Catatan Praktikum.
- Pastikan asisten telah menandatangani catatan percobaan kali ini pada Buku Catatan Praktikum Anda. Catatan percobaan yang tidak ditandatangani oleh asisten tidak akan dinilai.
- Kumpulkan kode program tugas tambahan pada setiap percobaan dalam repository github dengan format name repository “Kelas(value)_Modul(value)_Nama_NIM”


<h2></h2>

<br>

![banner](https://github.com/user-attachments/assets/f1f03032-41c0-4121-94e3-df1d513b42e5)
