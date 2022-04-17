## About / Tentang
Pernah mengalami ketika kita instal cPanel di Centos, 
lalu koneksi terputus dan terpaksa harus mengulang dari awal? atau mungkin secara tidak sengaja Anda menutup jendela / window SSH ?

Nah, ada sebuah tools di linux yang bernama “screen” yang berguna untuk tetap melanjutkan progress / perintah yang sedang kita kerjakan sekalipun koneksi kita via SSH terputus (bisa karena Internet tidak stabil atau apapun yang dapat memutus sambungan SSH kita).

# Install
Pertama-tama buatlah koneksi SSH ke server / VPS anda. Pastikan server anda telah terinstall tools screen agar dapat menjalankan perintah-perintah dibawah.

Apabila belum terinstall, anda dapat menginstall screen dengan cara sebagai berikut :


Untuk Ubuntu:
```
apt-get install screen
```


Untuk CentOS:
```
yum install screen
```


Untuk memulai screen, anda dapat menjalankan perintah (Untuk CentOS dan Ubuntu):
| Keterangan | Command | Tombol |
| ------ | ------ | ------ |
|Apabila anda ingin memberikan nama dari screen yang anda buat, gunakan perintah|screen -R namascreen|Untuk keluar dari screen , tekan tombol “CTRL+a” kemudian tombol “d”.|
|Untuk melihat screen yang aktif|**_screen -list_** Atau _**screen -ls**_|Untuk kembali ke screen yang telah dibuat (ingat -r berbeda dengan -R):
### Tutorial
