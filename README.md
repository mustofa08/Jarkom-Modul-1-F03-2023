# Jarkom-Modul-1-F03-2023
### Anggota Kelompok Jarkom D27:
- Abyan Zhafran Trisnanto - 5025211218
- Akhmad Mustofa Solikin - 5025211230

## Soal 1
### Soal

User melakukan berbagai aktivitas dengan menggunakan protokol FTP. Salah satunya adalah mengunggah suatu file.
Berapakah sequence number (raw) pada packet yang menunjukkan aktivitas tersebut? 
Berapakah acknowledge number (raw) pada packet yang menunjukkan aktivitas tersebut? 
Berapakah sequence number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?
Berapakah acknowledge number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?

### Penyelesaian
Untuk mengetahui protokol FTP yang digunakan untuk mengupload file bisa menggunakan sintaks display filter berikut:
```
ftp contains "STOR"
```
![alt text](https://github.com/KleponPutu21/Jarkom-Modul-1-F03-2023/blob/main/img/1.1.png?raw=true)
setelah mengetahui file yang diupload, kita bisa lakukan display filter berikut untuk mengetahui Request dan Response nya
```
ftp contains "zip"
```
![alt text](https://github.com/KleponPutu21/Jarkom-Modul-1-F03-2023/blob/main/img/1.2.png?raw=true)

Untuk soal a dan b kita bisa lihat pada paket Request bagian berikut:

![alt text](https://github.com/KleponPutu21/Jarkom-Modul-1-F03-2023/blob/main/img/1.3.png?raw=true)

Sedangkan untuk soal b dan c kita bisa lihat pada paket Response bagian berikut:

![alt text](https://github.com/KleponPutu21/Jarkom-Modul-1-F03-2023/blob/main/img/1.4.png?raw=true)

Perolehan Flag:

![alt text](https://github.com/KleponPutu21/Jarkom-Modul-1-F03-2023/blob/main/img/1.5.jpg?raw=true)

Kendala: tidak ada

## Soal 2
### Soal
Sebutkan web server yang digunakan pada portal praktikum Jaringan Komputer!
### Penyelesaian
Kita perlu mencari paket-paket dengan alamat IP portal praktikum yakni 10.21.78.111 menggunakan display filter berikut:
```
ip.addr == 10.21.78.111
```
![alt text](https://github.com/KleponPutu21/Jarkom-Modul-1-F03-2023/blob/main/img/2.1.png?raw=true)

setelah itu kita klik salah satu paket dan follow ke tcp streamnya

![alt text](https://github.com/KleponPutu21/Jarkom-Modul-1-F03-2023/blob/main/img/2.2.png?raw=true)

maka akan muncul server yang dipakai yaitu gunicorn

![alt text](https://github.com/KleponPutu21/Jarkom-Modul-1-F03-2023/blob/main/img/2.3.png?raw=true)

Perolehan Flag:

![alt text](https://github.com/KleponPutu21/Jarkom-Modul-1-F03-2023/blob/main/img/2.4.jpg?raw=true)

Kendala: tidak ada

## Soal 3
### Soal
Dapin sedang belajar analisis jaringan. Bantulah Dapin untuk mengerjakan soal berikut:
Berapa banyak paket yang tercapture dengan IP source maupun destination address adalah 239.255.255.250 dengan port 3702?
Protokol layer transport apa yang digunakan?
### Penyelesaian
Lakukan display filter sesuai alamat IP soal sebagai berikut:
```
ip.addr == 239.255.255.250
```
![alt text](https://github.com/KleponPutu21/Jarkom-Modul-1-F03-2023/blob/main/img/3.1.png?raw=true)

lalu kita bisa lihat protocol layer yang digunakan adalah UDP (jawaban soal b), sehingga bisa kita tambahkan ke display filter menjadi:
```
ip.addr == 239.255.255.250 and udp.port == 3702
```

![alt text](https://github.com/KleponPutu21/Jarkom-Modul-1-F03-2023/blob/main/img/3.2.png?raw=true)

setelah itu dapat kita hitung total paket nya yakni 21 

Perolehan Flag:

![alt text](https://github.com/KleponPutu21/Jarkom-Modul-1-F03-2023/blob/main/img/3.3.jpg?raw=true)

Kendala: tidak ada

## Soal 4
### Soal
Berapa nilai checksum yang didapat dari header pada paket nomor 130?
### Penyelesaian
Kita cukup scroll hingga menemukan paket nomor 130 lalu buka deskripsi TCP nya seperti berikut:

![alt text](https://github.com/KleponPutu21/Jarkom-Modul-1-F03-2023/blob/main/img/4.1.png?raw=true)

nilai checksum yang dimaksud adalah: 0x18e5

Perolehan Flag:

![alt text](https://github.com/KleponPutu21/Jarkom-Modul-1-F03-2023/blob/main/img/4.2.jpg?raw=true)

Kendala: tidak ada

## Soal 5
### Soal
Elshe menemukan suatu file packet capture yang menarik. Bantulah Elshe untuk menganalisis file packet capture tersebut.
Berapa banyak packet yang berhasil di capture dari file pcap tersebut?
Port berapakah pada server yang digunakan untuk service SMTP?
Dari semua alamat IP yang tercapture, IP berapakah yang merupakan public IP?

### Penyelesaian


## Soal 6
### Soal
Seorang anak bernama Udin Berteman dengan SlameT yang merupakan seorang penggemar film detektif. sebagai teman yang baik, Ia selalu mengajak slamet untuk bermain valoranT bersama. suatu malam, terjadi sebuah hal yang tak terdUga. ketika udin mereka membuka game tersebut, laptop udin menunjukkan sebuah field text dan Sebuah kode Invalid bertuliskan "server SOURCE ADDRESS 7812 is invalid". ketika ditelusuri di google, hasil pencarian hanya menampilkan a1 e5 u21. jiwa detektif slamet pun bergejolak. bantulah udin dan slamet untuk menemukan solusi kode error tersebut.
### Penyelesaian


## Soal 7
### Soal
Berapa jumlah packet yang menuju IP 184.87.193.88?
### Penyelesaian
Kita cukup lakukan sintaks display filter berikut:
```
ip.dst == 184.87.193.88 
```
![alt text](https://github.com/KleponPutu21/Jarkom-Modul-1-F03-2023/blob/main/img/7.1.png?raw=true)

Jumlah paket yang menuju IP tersebut adalah 6

Perolehan Flag:

![alt text](https://github.com/KleponPutu21/Jarkom-Modul-1-F03-2023/blob/main/img/7.2.jpg?raw=true)

Kendala: tidak ada

## Soal 8
### Soal
Berikan kueri filter sehingga wireshark hanya mengambil semua protokol paket yang menuju port 80! (Jika terdapat lebih dari 1 port, maka urutkan sesuai dengan abjad)
### Penyelesaian
Memerlukan kueri filter yang menyaring paket dengan tujuan port 80.Karena berkaitan dengan port, kami menggunakan TCP dan UDP, kemudian karena disebutkan port 80 maka kueri filter yang sesuai adalah [tcp.dstport == 80 || udp.dstport == 80]

Perolehan Flag:

![alt text](https://github.com/KleponPutu21/Jarkom-Modul-1-F03-2023/blob/main/img/8.1.jpg?raw=true)

Kendala: tidak ada

## Soal 9
### Soal
Berikan kueri filter sehingga wireshark hanya mengambil paket yang berasal dari alamat 10.51.40.1 tetapi tidak menuju ke alamat 10.39.55.34!
### Penyelesaian
Memerlukan queri filter untuk mengabil paket yang berasal dari alamat 10.51.40.1 dan tidak menuju alamat 10.39.55.34. Karena berkaitan dengan alamata, maka kami menggunakan (ip), kemudian menggunakan and(&&) untuk menyatukan kondisi yang dibutuhkan. Sehingga kueri yang sesuai adalah [ip.src == 10.51.40.1 && ip.dst != 10.39.55.34]

![alt text](https://github.com/KleponPutu21/Jarkom-Modul-1-F03-2023/blob/main/img/9.1.jpg?raw=true)

Kendala: tidak ada

## Soal 10
### Soal
Sebutkan kredensial yang benar ketika user mencoba login menggunakan Telnet
### Penyelesaian
Pertama kita mencari telent user yang mencoba login dengan cara berikut
```
tcp contains "Password"
```
![alt text](https://github.com/KleponPutu21/Jarkom-Modul-1-F03-2023/blob/main/img/10.1.png?raw=true)

setelah itu kita klik paket yang ada dan follow ke tcp streamnya

![alt text](https://github.com/KleponPutu21/Jarkom-Modul-1-F03-2023/blob/main/img/10.2.png?raw=true)

maka akan akan muncul tampilan User dan password

Perolehan Flag:

![alt text](https://github.com/KleponPutu21/Jarkom-Modul-1-F03-2023/blob/main/img/10.3.jpg?raw=true)

Kendala:
- brute force username yang mana di paket tertulis ddhhaaffiinn tetapi jawaban yang benar dhafin


