1. Buat direktori dengan nama UAP-Adsis, isi dengan file txt dengan format penamaan catatannya-<nama kamu>.txt, kemudian isi file txt tersebut dengan nama dan NIM kamu. Kemudian atur permission view-only pada file tersebut untuk user biasa. Tunjukkan bukti berupa screenshot yang menunjukkan bahwa file tersebut berhasil diatur permissionnya menjadi view-only untuk user biasa.
    Jawaban : 
    ![Alt text](SS/images/1.png)
        -Membuat direktori UAP-Adsis dengan perintah mkdir UAP-Adsis.
    ![Alt text](SS/images/3.png)
        -Membuat file catatannya-aulia.txt menggunakan perintah touch catatannya-aulia.txt. Kemudian masuk ke file tersebut dengan menjalankan perintah nano catatannya-aulia.txt
    ![Alt text](SS/images/4.png)
        -Memasukan text berupa nama dan NIM saya dalam file catatanya-fingka.txt
    ![Alt text](SS/images/5.png)
        -Mengatur permission view-only pada file tersebut untuk user biasa dengan menggunakan perintah sudo chmod 644 catatannya-aulia.txt.
    ![Alt text](SS/images/6.png)
        -Mengecek apakah file tersebut sudah berhasil diatur permission nya untuk menjadi view-only untuk user biasa dengan menggunakan perintah ls -l

2. Lakukan konfigurasi alamat IP address sementara pada sistem dan default gateway. (petunjuk 192.168.56 x | x adalah nomor absen)
    Jawaban : 
    ![Alt text](SS/images/7.png)
        -Melakukan konfigurasi IP Address sementara dengan menjalankan perintah sudo ifconfig enp0s8 192.168.56.13 netmask 255.255.255.0. Disini saya memasukkan IP Address 192.168.56.13 sesuai dengan nomor absen saya yaitu 13.
    ![Alt text](SS/images/9.png)
        -Melakukan verifikasi untuk memastikan alamat IP yang telah dikonfigurasi telah terdaftar dengan menjalankan perintah sudo ifconfig enp0s8.
    ![Alt text](SS/images/10.png)    
        -Melakukan konfigurasi IP Addres Default Gateway dengan menjalankan perintah sudo route add default gw 192.168.56.13 enp0s8. Disini saya menggunakan IP Addres yang sama dengan perintah sebelumnya. Kemudian saya menjalankan perintah sudo route -n untuk memastikan bahwa alamat IP Default Gateway sudah terdaftar.

3. Lakukan Instalasi Webmin lalu buatlah user nama anda, lalu buat group Adsis_(kelas masing-masing) dan masukkan nama anda di group
    Jawaban : 
    ![Alt text](SS/images/11.png)
        -Masuk ke dalam direktori file /etc/apt/source.list kemudian tambahkan deb http://download.webmin.com/download/repository sarge contrib pada baris akhir.
    ![Alt text](SS/images/12.png)
        -Menambahkan kunci PGP Webmin agar sistem dapat mempercayai repository baru: wget http://www.webmin.com/jcameron-key.asc 
        -sudo apt-key add jcameron-key.asc
    ![Alt text](SS/images/13.png)
        -Menjalankan perintah sudo apt get install webmin untuk menginstall webmin.
    ![Alt text](SS/images/14.png)
        -Mengakses webmin dengan menjalankan https://webmin:192.168.56.103:10000. Yang dimana 192.168.56.103 merupakan IP saya yang telah saya cek melalui perintah ifconfig. Dan 10000 adalah port untuk mengakses webmin tersebut.
    ![Alt text](SS/images/15.png)
        -Mengakses Users and Group pada webmin untuk membuat user baru.
    ![Alt text](SS/images/16.png)
        -Mengakses group dan membuat group baru dengan nama Adsis_c sesuai dengan ketentuan yang ada pada soal. Serta menambahkan user auliasepty yang baru dibuat pada perintah sebelumnya ke dalam group Adsis_e.

4.  Lakukan ping ke alamat ip anda dan coba lakukan reject dan drop di webmin, lalu analisis apa yang terjadi?
    Jawaban : 
    ![Alt text](SS/images/17.png)
        -Melakukan ping ke alamat IP saya dengan menjalankan perintah ping 192.68.56.103 -t.
    ![Alt text](SS/images/19.png)
        -Mengakses ke network->firewall kemudian ke bagian Incoming packets (INPUT) untuk melakukan reject ping.

5.  Buatlah perintah otomatis yang berfungsi untuk ping www.filkom.ub.ac.id
    Jawaban : 
    ![Alt text](SS/images/20.png)
        -Melakukan proses edit pada konfigurasi file cron dengan perintah sudo crontab -e.
    ![Alt text](SS/images/21.png)
        -Mengisi konfigurasi crontab dengan perintah */1 * * * * ping filkom.ub.ac.id untuk melakukan ping otomatis setiap menit.
    ![Alt text](SS/images/22.png)
        -Memastikan ping berhasil dilakukan dengan menjalankan perintah ps aux | grepping.