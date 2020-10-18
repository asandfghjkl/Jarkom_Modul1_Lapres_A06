# Jarkom_Modul1_Lapres_A06
Kelompok A06<br>
Muhammad Fikri Rabbani 	(05111840000165)<br>
Sandra Agnes Oktaviana 	(05111840000124)

### DISPLAY FILTER
#### 1. Sebutkan webserver yang digunakan pada "testing.mekanis.me"!
penyelesaian:<br>
http.host == testing.mekanis.me

![1a](https://github.com/asandfghjkl/Jarkom_Modul1_Lapres_A06/blob/main/pics/10a.png)


tcp.stream eq 158

![1b](https://github.com/asandfghjkl/Jarkom_Modul1_Lapres_A06/blob/main/pics/1b.png)

#### 2. Simpan gambar "Tim_Kunjungan_Kerja_BAKN_DPR_RI_ke_Sukabumi141436.jpg"!
penyelesaian:<br>
![2a](https://github.com/asandfghjkl/Jarkom_Modul1_Lapres_A06/blob/main/pics/2a.png)

![2b](https://github.com/asandfghjkl/Jarkom_Modul1_Lapres_A06/blob/main/pics/2b.png)

![2c](https://github.com/asandfghjkl/Jarkom_Modul1_Lapres_A06/blob/main/pics/2c.jpg)

#### 3. Cari username dan password ketika login di "ppid.dpr.go.id"!
penyelesaian:<br>
http.request.uri contains login && http.host == ppid.dpr.go.id

![3a](https://github.com/asandfghjkl/Jarkom_Modul1_Lapres_A06/blob/main/pics/3a.png)

![3b](https://github.com/asandfghjkl/Jarkom_Modul1_Lapres_A06/blob/main/pics/3b.png)

#### 4. Temukan paket dari web-web yang menggunakan basic authentication method!
penyelesaian:<br>
http.authbasic

![4a](https://github.com/asandfghjkl/Jarkom_Modul1_Lapres_A06/blob/main/pics/4a.png)

![4b](https://github.com/asandfghjkl/Jarkom_Modul1_Lapres_A06/blob/main/pics/4b.png)

#### 5. Ikuti perintah di aku.pengen.pw! Username dan password bisa didapatkan dari file .pcapng!
penyelesaian:<br>
http.host == aku.pengen.pw

![5a](https://github.com/asandfghjkl/Jarkom_Modul1_Lapres_A06/blob/main/pics/5a.png)

![5b](https://github.com/asandfghjkl/Jarkom_Modul1_Lapres_A06/blob/main/pics/5b.png)

![5c](https://github.com/asandfghjkl/Jarkom_Modul1_Lapres_A06/blob/main/pics/5c.png)

#### 6. Seseorang menyimpan file zip melalui FTP dengan nama "Answer.zip". Simpan dan Buka file "Open This.pdf" di Answer.zip. Untuk mendapatkan password zipnya, temukan dalam file zipkey.txt (passwordnya adalah isi dari file txt tersebut).
penyelesaian:<br>
ftp matches Answer.zip

![6a](https://github.com/asandfghjkl/Jarkom_Modul1_Lapres_A06/blob/main/pics/6a.png)

klik kanan > follow > TCP stream

![6b](https://github.com/asandfghjkl/Jarkom_Modul1_Lapres_A06/blob/main/pics/6b.png)

set stream to 12 and save as raw "Answer.zip"

![6c](https://github.com/asandfghjkl/Jarkom_Modul1_Lapres_A06/blob/main/pics/6c.png)

hasil unduhan file Answer.zip berisikan file pdf, namun diperlukan password yang terdapat pada zipkey.txt

![6d](https://github.com/asandfghjkl/Jarkom_Modul1_Lapres_A06/blob/main/pics/6d.png)

untuk mendapatkan password maka lakukan ftp matches zipkey.txt

![6e](https://github.com/asandfghjkl/Jarkom_Modul1_Lapres_A06/blob/main/pics/6e.png)

klik kanan > follow > TCP stream, lalu set stream to 23 and save as raw "zipkey.txt"

![6f](https://github.com/asandfghjkl/Jarkom_Modul1_Lapres_A06/blob/main/pics/6f.png)

pada file file zipkey.txt ditemukan password: hey997400323051

![6g](https://github.com/asandfghjkl/Jarkom_Modul1_Lapres_A06/blob/main/pics/6g.png)

masukkan password tersebut untuk membuka file pdf

![6h](https://github.com/asandfghjkl/Jarkom_Modul1_Lapres_A06/blob/main/pics/6h.png)



#### 7. Ada 500 file zip yang disimpan ke FTP Server dengan nama 1.zip, 2.zip, ..., 500.zip. Salah satunya berisi pdf yang berisi puisi. Simpan dan Buka file pdf tersebut.
penyelesaian:<br>
frame contains Yes.pdf

![7a](https://github.com/asandfghjkl/Jarkom_Modul1_Lapres_A06/blob/main/pics/7a.png)

klik kanan > follow > FTP stream, save as raw "Yes.zip"

![7b](https://github.com/asandfghjkl/Jarkom_Modul1_Lapres_A06/blob/main/pics/7b.png)

isi Yes.zip tersebut terdapat Yes.pdf

![7c](https://github.com/asandfghjkl/Jarkom_Modul1_Lapres_A06/blob/main/pics/7c.png)

![7d](https://github.com/asandfghjkl/Jarkom_Modul1_Lapres_A06/blob/main/pics/7d.png)

#### 8. Cari objek apa saja yang didownload (RETR) dari koneksi FTP dengan Microsoft FTP Service!
penyelesaian:<br>
cari ip Microsoft FTP service dengan ftp contains Microsoft

![8a](https://github.com/asandfghjkl/Jarkom_Modul1_Lapres_A06/blob/main/pics/8a.png)

setelah diketahui ip hostnya (198.246.117.106), 
lakukan ftp.request.command == RETR && ip.host == 198.246.117.106

![8b](https://github.com/asandfghjkl/Jarkom_Modul1_Lapres_A06/blob/main/pics/8b.png)

objek yang didownload (RETR) adalah Readme

#### 9. Cari username dan password ketika login FTP pada localhost!
penyelesaian:<br>
ftp.request.command == USER || ftp.request.command == PASS

![9a](https://github.com/asandfghjkl/Jarkom_Modul1_Lapres_A06/blob/main/pics/9a.png)

Dapat diambil kesimpulan<br>
USER = dhana<br>
PASS = dhana123<br>


#### 10. Cari file .pdf di wireshark lalu download dan buka file tersebut!
penyelesaian:<br>
http.request.uri contains pdf

![10a](https://github.com/asandfghjkl/Jarkom_Modul1_Lapres_A06/blob/main/pics/10a.png)




### CAPTURE FILTER
#### 11. Filter sehingga wireshark hanya mengambil paket yang mengandung port 21!
penyelesaian:<br>
port 21

![11](https://github.com/asandfghjkl/Jarkom_Modul1_Lapres_A06/blob/main/pics/11.png)

#### 12. Filter sehingga wireshark hanya mengambil paket yang berasal dari port 80!
penyelesaian:<br>
src port 80

![12](https://github.com/asandfghjkl/Jarkom_Modul1_Lapres_A06/blob/main/pics/12.png)

#### 13. Filter sehingga wireshark hanya menampilkan paket yang menuju port 443!
penyelesaian:<br>
dst port 443

![13](https://github.com/asandfghjkl/Jarkom_Modul1_Lapres_A06/blob/main/pics/13.png)

#### 14. Filter sehingga wireshark hanya mengambil paket yang berasal dari ip kalian!
penyelesaian:<br>
untuk mencari ip dengan cmd IPCONFIG

![14a](https://github.com/asandfghjkl/Jarkom_Modul1_Lapres_A06/blob/main/pics/14a.png)

diketahui ip address: 192.168.1.9<br>lalu capture src host 192.168.1.9

![14b](https://github.com/asandfghjkl/Jarkom_Modul1_Lapres_A06/blob/main/pics/14b.png)

#### 15. Filter sehingga wireshark hanya mengambil paket yang tujuannya ke monta.if.its.ac.id!
penyelesaian:<br>
cari ip address monta.if.its.ac.id dengan cmd NSLOOKUP monta.if.its.ac.id

![15a](https://github.com/asandfghjkl/Jarkom_Modul1_Lapres_A06/blob/main/pics/15a.png)

gunakan ip address tersebut, dst host 103.94.190.11

![15b](https://github.com/asandfghjkl/Jarkom_Modul1_Lapres_A06/blob/main/pics/15b.png)

