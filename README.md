# Jarkom-Modul-1-F10-2023
Laporan resmi praktikum modul 1 wireshark &amp; crimping mata kuliah jaringan komputer

## 1. User melakukan berbagai aktivitas dengan menggunakan protokol FTP. Salah satunya adalah mengunggah suatu file.
Aktivitas mengunggah pada ftp menggunakan perintah STOR. Paket dapat dicari dengan memberi display filter “ftp contains "STOR"”, response dapat dilihat dengan follow tcp stream paket tersebut. Paket response berada setelah paket mengunggah.<br />
SS paket mengunggah:<br />
![SS paket mengunggah](tangkaplayar/1a.jpg)<br />
SS paket respon:<br />
![SS paket respon](tangkaplayar/1b.jpg)<br /><br />
a. Berapakah sequence number (raw) pada _packet_ yang menunjukkan aktivitas tersebut? **258040667**<br />
b. Berapakah acknowledge number (raw) pada _packet_ yang menunjukkan aktivitas tersebut? **1044861039**<br />
c. Berapakah sequence number (raw) pada _packet_ yang menunjukkan response dari aktivitas tersebut? **1044861039**<br />
d. Berapakah acknowledge number (raw) pada _packet_ yang menunjukkan response dari aktivitas tersebut? **258040696**

## 2. Sebutkan web server yang digunakan pada portal praktikum Jaringan Komputer!
Melakukan display filter dengan kueri http. Kemudian mem-follow http stream. Informasi web server yang digunakan tertera pada kolom Server.<br />
![gunicorn](tangkaplayar/2.jpg)

## 3. Dapin sedang belajar analisis jaringan. Bantulah Dapin untuk mengerjakan soal berikut:
- Display Filter dengan kueri “(ip.src == 239.255.255.250 || ip.dst == 239.255.255.250) && (tcp.port == 3702 || udp.por t== 3702)”<br />
- Export specified packets<br />
- Hasil:<br />
![analisis jaringan](tangkaplayar/3.jpg)<br /><br />
a. Berapa banyak paket yang tercapture dengan IP source maupun destination address adalah 239.255.255.250 dengan port 3702? **21**<br />
b. Protokol layer transport apa yang digunakan? **UDP**

## 4. Berapa nilai checksum yang didapat dari header pada paket nomor 130?
Mengecek paket yang dimaksud. Informasi nilai checksum ada di bawah dropdown layer transport, UDP.<br />
![0x18e5](tangkaplayar/4.jpg)

## 5. Elshe menemukan suatu file packet capture yang menarik. Bantulah Elshe untuk menganalisis file packet capture tersebut.
Mengecek satu-satu dari _packet_ yang tertangkap akan data yang dapat dibaca. Ditemukan email yang isinya dapat dibaca di _packet_ nomor 22. Email berisi password terenkripsi beserta instruksi memecahkannya, yaitu menggunakan Base64.<br />
![smtp](tangkaplayar/5a.jpg)<br />
Menggunakan decoder Base64 daring. Didapatkan password untuk membuka file zip yang terkunci.<br />
![base64 decoder](tangkaplayar/5b.jpg)<br />
Isi dari file zip yang terkunci adalah alamat pertanyaan-pertanyaan untuk dijawab.<br />
![netcat](tangkaplayar/5c.jpg)<br /><br />
a. Berapa banyak _packet_ yang berhasil di capture dari file pcap tersebut? **60**<br />
b. Port berapakah pada server yang digunakan untuk service SMTP? **25**<br />
c. Dari semua alamat IP yang tercapture, IP berapakah yang merupakan public IP? **74.53.140.153** (alamat IP selain dari IP local kita)

## Soal no. 6
Pada paragraf, huruf yang ditulis menggunakan huruf kapital membentuk kata “SUBSTITUSI”, lalu terdapat pula a1 e5 u21, yang menunjukkan bahwa tiap huruf dapat disubstitusi dengan angka sesuai urutan abjad. Terakhir, pada pesan error terdapat “SOURCE 7812”, pada pcap paket ke 7812 ip sourcenya adalah “104 18 14 101”, jika disubstitusi dapat menjadi JDRNJA (10 4 18 14 10 1).<br />
![7812](tangkaplayar/6.jpg)

## 7. Berapa jumlah packet yang menuju IP 184.87.193.88?
Dengan display filter `ip.dst==184.87.193.88`, didapatkan: **6**<br />
![jumlah packet](tangkaplayar/7.jpg)

## 8. Berikan kueri filter sehingga wireshark hanya mengambil semua protokol paket yang menuju port 80! (Jika terdapat lebih dari 1 port, maka urutkan sesuai dengan abjad)
`tcp.dstport == 80 || udp.dstport == 80`<br />
![kueri filter](tangkaplayar/8.jpg)

## 9. Berikan kueri filter sehingga wireshark hanya mengambil paket yang berasal dari alamat 10.51.40.1 tetapi tidak menuju ke alamat 10.39.55.34!
`ip.src == 10.51.40.1 && ip.dst != 10.39.53.34`<br />
![kueri filter](tangkaplayar/9.jpg)

## 10. Sebutkan kredensial yang benar ketika user mencoba login menggunakan Telnet
Mencoba-coba kombinasi yang tersedia dengan format username:password yang merupakan format kredensial telnet.<br />
![kredensial](tangkaplayar/10.jpg)