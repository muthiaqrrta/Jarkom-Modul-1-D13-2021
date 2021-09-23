# Jarkom-Modul-1-D13-2021

### Anggota kelompok:
Anggota | NRP
------------- | -------------
Muthia Qurrota Akyun | 05111940000019
Fayha Syifa Qalbi | 05111940000185
Raihan Alifianto | 05111940000213

### 1. Sebutkan webserver yang digunakan pada "ichimarumaru.tech"! 

### 2. Temukan paket dari web-web yang menggunakan basic authentication method!

### 3. Ikuti perintah di basic.ichimarumaru.tech! Username dan password bisa didapatkan dari file .pcapng!

### 4. Temukan paket mysql yang mengandung perintah query select!

### 5. Login ke portal.ichimarumaru.tech kemudian ikuti perintahnya! Username dan password bisa didapat dari query insert pada table users dari file .pcap!

### 6. Cari username dan password ketika melakukan login ke FTP Server!
Pertama membuka file 6-7.pcap dengan wireshark kemudian, mengisi filter pada file 6-7.pcap dengan : ftp.request.command == PASS || ftp.request.command == USER, sebagai berikut:
<img src="https://github.com/muthiaqrrta/Jarkom-Modul-1-D13-2021/blob/main/Screenshot/no6.png">

### 7. Ada 500 file zip yang disimpan ke FTP Server dengan nama 0.zip, 1.zip, 2.zip, ..., 499.zip. Simpan dan Buka file pdf tersebut. (Hint = nama pdf-nya "Real.pdf")
Mengisi display filter : frame contains “Real.pdf” sebagai berikut,
<img src="https://github.com/muthiaqrrta/Jarkom-Modul-1-D13-2021/blob/main/Screenshot/no7-1.png">

Kemudian mengisi Follow TCP Stream, dan mengubah tampilan ASCII ke RAW dan Save-As Real.zip,
<img src="https://github.com/muthiaqrrta/Jarkom-Modul-1-D13-2021/blob/main/Screenshot/no7-2.png">

Kemudian ekstrak file Real.zip yang sudah tersimpan untuk mendapatkan file pdf
<img src="https://github.com/muthiaqrrta/Jarkom-Modul-1-D13-2021/blob/main/Screenshot/no7-3.png">

Adapun isi file pdf yaitu,
<img src="https://github.com/muthiaqrrta/Jarkom-Modul-1-D13-2021/blob/main/Screenshot/no7-4.png">

### 8. Cari paket yang menunjukan pengambilan file dari FTP tersebut!
Pertama membuka file 8-10.pcap dengan wireshark dan tulis di display filter: ftp.request.command == RETR, adapun hasilnya sebagai berikut:
<img src="https://github.com/muthiaqrrta/Jarkom-Modul-1-D13-2021/blob/main/Screenshot/no8-3.png">

### 9. Dari paket-paket yang menuju FTP terdapat inidkasi penyimpanan beberapa file. Salah satunya adalah sebuah file berisi data rahasia dengan nama "secret.zip". Simpan dan buka file tersebut!
Pertama mengisi display filter : ftp-data contains “secret.zip”, kemudian → Follow TCP Stream ubah ASCII, dan stream menjadi 10 kemudian Save-As secret.zip. Adapun hasil screenshotnya sebagai berikut,
<img src="https://github.com/muthiaqrrta/Jarkom-Modul-1-D13-2021/blob/main/Screenshot/no9-1.png">
<img src="https://github.com/muthiaqrrta/Jarkom-Modul-1-D13-2021/blob/main/Screenshot/no9-2.png">

### 10. Selain itu terdapat "history.txt" yang kemungkinan berisi history bash server tersebut! Gunakan isi dari "history.txt" untuk menemukan password untuk membuka file rahasia yang ada di "secret.zip"!
Pertama buka file 8-10.pcap dengan wireshark dan isi display filter dengan: ftp-data contains “history.txt”
<img src="https://github.com/muthiaqrrta/Jarkom-Modul-1-D13-2021/blob/main/Screenshot/no10-1.png">

lalu follow hasil filter berikut dengan tcp-stream dan ubah ascii menjadi raw, streamnya dinaikan menjadi 11 kemudian save dengan nama history.txt, lalu setelah di save kami mendapatkan file dengan isi seperti dibawah ini
<img src="https://github.com/muthiaqrrta/Jarkom-Modul-1-D13-2021/blob/main/Screenshot/no10-2.png">

yang dapat kita gunakan untuk membuka wanted,pdf yang terdapat di dalam secret.zip, berikut setelah pdfnya terbuka.
<img src="https://github.com/muthiaqrrta/Jarkom-Modul-1-D13-2021/blob/main/Screenshot/no10-3.png">

### 11. Filter sehingga wireshark hanya mengambil paket yang berasal dari port 80! 
Mengisi capture filter dengan `src port 80` seperti berikut.
<img src="https://github.com/muthiaqrrta/Jarkom-Modul-1-D13-2021/blob/main/Screenshot/no11-1.png">

Kemudian hasilnya 
<img src="https://github.com/muthiaqrrta/Jarkom-Modul-1-D13-2021/blob/main/Screenshot/no11-2.png">

### 12. Filter sehingga wireshark hanya mengambil paket yang mengandung port 21!
Mengisi capture filter dengan `port 21` seperti berikut.
<img src="https://github.com/muthiaqrrta/Jarkom-Modul-1-D13-2021/blob/main/Screenshot/no12-1.png">

Kemudian hasilnya 
<img src="https://github.com/muthiaqrrta/Jarkom-Modul-1-D13-2021/blob/main/Screenshot/no12-2.png">
Tidak terdapat port yang ditampilkan dikarenakan port 21 merupakan private server.

### 13. Filter sehingga wireshark hanya menampilkan paket yang menuju port 443!
Mengisi capture filter dengan `dst port 443` seperti berikut.
<img src="https://github.com/muthiaqrrta/Jarkom-Modul-1-D13-2021/blob/main/Screenshot/no13-1.png">

Kemudian hasilnya 
<img src="https://github.com/muthiaqrrta/Jarkom-Modul-1-D13-2021/blob/main/Screenshot/no13-2.png">

### 14. Filter sehingga wireshark hanya mengambil paket yang tujuannya ke kemenag.go.id!
Mengisi capture filter dengan `dst host kemenag.go.id` seperti berikut.
<img src="https://github.com/muthiaqrrta/Jarkom-Modul-1-D13-2021/blob/main/Screenshot/no14-1.png">

Kemudian buka website kemenag.go.id sehingga wireshark menampilkan tampilan berikut.
<img src="https://github.com/muthiaqrrta/Jarkom-Modul-1-D13-2021/blob/main/Screenshot/no14-2.png">

### 15. Filter sehingga wireshark hanya mengambil paket yang berasal dari ip kalian!
Mengisi capture filter dengan `src host 192.168.134.29` yang merupakan alamat ip laptop yang digunakan seperti berikut.

<img src="https://github.com/muthiaqrrta/Jarkom-Modul-1-D13-2021/blob/main/Screenshot/no15-1.png">

Kemudian hasilnya 

<img src="https://github.com/muthiaqrrta/Jarkom-Modul-1-D13-2021/blob/main/Screenshot/no15-2.png">

