## About / Tentang
Pernah mengalami ketika kita instal cPanel di Centosatau di linux lain, 
lalu koneksi terputus dan terpaksa harus mengulang dari awal? atau mungkin secara tidak sengaja Anda menutup jendela / window SSH ?

Nah, ada sebuah Tools di linux yang bernama `“screen”` yang berguna untuk tetap melanjutkan progress / perintah yang sedang kita kerjakan sekalipun koneksi kita via SSH terputus (bisa karena Internet tidak stabil atau apapun yang dapat memutus sambungan SSH kita).

# Install
Pertama-tama buatlah koneksi SSH ke server / VPS anda. Pastikan server anda telah terinstall tools screen agar dapat menjalankan perintah-perintah dibawah.

cara cek apa kah sudah di install degan menggunakan perintah seperti berikut:
```
screen
```


### Apabila belum terinstall 
anda dapat menginstall screen dengan cara sebagai berikut :

Untuk Ubuntu:
```
apt-get install screen
```

Untuk CentOS:
```
yum install screen
```

# Tutorial
### Untuk memulai screen, anda dapat menjalankan perintah (Untuk CentOS dan Ubuntu):
| Keterangan | Command | Tombol |
| ------ | ------ | ------ |
|Cara untuk membuka screen yang sudah jika sudah di bikin.|screen -r namascreen/code|Untuk keluar dari screen , tekan tombol “CTRL+a” kemudian tombol “d”.|
|Apabila anda ingin memberikan nama dari screen yang anda buat, gunakan perintah|screen -R namascreen|Untuk keluar dari screen , tekan tombol “CTRL+a” kemudian tombol “d”.|
|Untuk melihat screen yang aktif|**_screen -list_** Atau _**screen -ls**_|Untuk kembali ke screen yang telah dibuat (ingat -r berbeda dengan -R):

### Beberapa perintah lain di screen:
| Tombol | Keterangan |
| ------ | ------ |
|CTRL + a + d|Untuk keluar dari screen.
|CTRL + a + c|Untuk membuat jendela screen baru.
|CTRL + a + n|Untuk melihat jendela screen selanjutnya.
|CTRL + a + p|Untuk melihat jendela screen sebelumnya.
|CTRL + a + w|Ini menampilkan daftar semua jendela yang sedang dibuka.
|CTRL + a + A|Ini mengubah nama jendela saat ini. Nama tersebut akan muncul ketika Anda akan mencantumkan daftar jendela yang dibuka dengan Ctrl-a + w.

