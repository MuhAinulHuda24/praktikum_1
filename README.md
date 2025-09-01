# Praktikum Flutter
## Praktikum 1
1. praktikum text widget :
   Menampilkan teks sederhana yang diposisikan tepat di tengah layar aplikasi.
2. praktikum image widget:
   Menampilkan sebuah gambar dengan posisi terletak di bagian tengah layar.
3. praktikum kombnasi text dan image widget :
   Menggabungkan teks dengan logo Poliwangi dalam satu tampilan, kemudian mengkreasikannya menjadi sebuah template sesuai ide masing-masing.

## tahapan kombinasi text dan widget 
1. Membuat Widget baru terlebih dahulu untuk menggabungkan antara teks dan logo.
2.Simpan logo Poliwangi ke dalam folder images/ di proyek.
3.Daftarkan aset gambar tersebut di file pubspec.yaml agar dapat digunakan.
4.Buat tampilan dengan widget Column yang memuat tulisan dan gambar.
5.Atur gaya teks, seperti ukuran atau ketebalan huruf, supaya lebih mudah dibaca.
6.Ubah warna latar belakang Scaffold menjadi biru agar tampilan lebih menarik.

Dokumentasi
<img width="360" height="727" alt="Cuplikan layar 2025-09-01 160702" src="https://github.com/user-attachments/assets/a9f8a9ac-de0b-4069-934b-c954fe120c3b" />

*menambhkan Widget yang Di isi dengan Logo Poliwangi

<img width="344" height="731" alt="Cuplikan layar 2025-09-01 163902" src="https://github.com/user-attachments/assets/22fd59aa-082d-4282-899b-4bec9aff2b5c" />

*Kemudian Mengganti Backgorund Menjadi Warna biru, kemudian Menambahkan Teks "Selamat Datang Di Politeknik Negeri Banyuwagi"

*Source Code :
## main.dart
import 'package:flutter/material.dart';
//import 'images_widget.dart';
import 'praktikum.dart';

void main() {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      debugShowCheckedModeBanner: false,
      home: Scaffold(
        backgroundColor: Colors.blue,
        body: SafeArea(
          child: Center(
            child: Column(
              mainAxisAlignment: MainAxisAlignment.center, 
              crossAxisAlignment: CrossAxisAlignment.center, 
              children: [
                Text(
                  'Selamat Datang Di Politeknik Negeri Banyuwangi',
                  style: TextStyle(
                    fontSize: 30,
                    color: Colors.white,
                    fontWeight: FontWeight.bold,
                  ),
                  textAlign: TextAlign.center,
                ),
                SizedBox(height: 40), 
                LogoPoliwangi(),
              ],
            ),
          ),
        ),
      ),
    );
  }
}

## praktikum.dart
import 'package:flutter/material.dart';

class LogoPoliwangi extends StatelessWidget {
  const LogoPoliwangi({super.key});

  @override
  Widget build(BuildContext context) {
    return Image.asset('images/poliwangi.png', width: 200, height: 200);
  }
}

class PraktikumWidget extends StatelessWidget {
  const PraktikumWidget({super.key});
  @override
  Widget build(BuildContext context) {
    return Column(
      children: [
        // Tulisan
        const Padding(
          padding: EdgeInsets.only(top: 40.0),
          child: Text(
            'Selamat Datang di Politeknik Negeri Banyuwangi',
            style: TextStyle(
              fontSize: 22,
              color: Color.fromARGB(255, 253, 253, 253),
              fontWeight: FontWeight.bold,
            ),
            textAlign: TextAlign.center,
          ),
        ),
        const SizedBox(height: 24),
        Image.asset(
          'images/poliwangi.jpg',
          width: 120,
          height: 120,
        ),
      ],
    );
  }
}


