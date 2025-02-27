## About / Tentang
Pernah mengalami ketika kita instal cPanel di Centosatau di linux lain, 
lalu koneksi terputus dan terpaksa harus mengulang dari awal? atau mungkin secara tidak sengaja Anda menutup jendela / window SSH ?

Nah, ada sebuah Tools di linux yang bernama `screen` yang berguna untuk tetap melanjutkan progress / perintah yang sedang kita kerjakan sekalipun koneksi kita via SSH terputus (bisa karena Internet tidak stabil atau apapun yang dapat memutus sambungan SSH kita).

# Install
Pertama-tama buatlah koneksi SSH ke server / VPS anda. Pastikan server anda telah terinstall tools screen agar dapat menjalankan perintah-perintah dibawah.

cara cek apa kah sudah di install degan menggunakan perintah seperti berikut:
```
screen
```


### Apabila belum terinstall 
Anda dapat menginstal **screen** dengan cara sebagai berikut:  

### **Untuk Ubuntu/Debian**  
```bash
sudo apt update
sudo apt install screen
```

### **Untuk CentOS/RHEL**  
```bash
sudo yum install screen
```

### **Untuk Fedora**  
```bash
sudo dnf install screen
```

### **Untuk Arch Linux**  
```bash
sudo pacman -S screen
```

# Tutorial
Perintah `screen` dapat digunakan dengan opsi dan argumen seperti perintah Linux lainnya. Sintaks untuk perintah `screen` adalah sebagai berikut, beserta opsi dan argumennya: 
```bash 
screen [-opts] [cmd [args]]
```
Perintah **screen** sering digunakan untuk menjalankan proses di terminal tanpa khawatir terputus, terutama saat menggunakan SSH. Berikut adalah beberapa cara penggunaan **screen** yang sering dipakai:  

### **1. Membuat Sesi Baru**  
```bash
screen -S [nama_sesi/kode_id_sesi]
```  
Gunakan perintah ini untuk membuat sesi baru dengan nama tertentu, misalnya:  
```bash
screen -S server_backup
```

### **2. Melihat Daftar Sesi yang Berjalan**  
```bash
screen -ls
```  
Gunakan ini untuk melihat daftar sesi **screen** yang masih aktif. Hasilnya akan menampilkan daftar sesi yang bisa dilanjutkan.

### **3. Melanjutkan Sesi yang Ada**  
```bash
screen -r [nama_sesi/kode_id_sesi]
```  
Jika sesi terputus (detached), Anda bisa melanjutkannya dengan perintah ini, contohnya:  
`screen -r [server_backup/264835]` atau `screen -r [264835.pts-0.server2/264835.server_backup]`

### **4. Keluar dari Screen Tanpa Menghentikan Proses** (Detach)  
Saat berada di dalam sesi **screen**, tekan:  
```
Ctrl + A, lalu tekan D
```  
Ini akan mengembalikan Anda ke terminal utama tanpa menutup sesi **screen**.

### **5. Menutup Screen Secara Permanen**  
Untuk keluar dan menutup sesi sepenuhnya, jalankan perintah berikut di dalam screen:  
`exit` Atau tekan:`Ctrl + D`

### **6. Menjalankan Perintah di Screen Tanpa Masuk ke Dalamnya**  
```bash
screen -dmS nama_sesi perintah
```  
Misalnya, menjalankan script tanpa masuk ke dalam sesi:  
```bash
screen -dmS backup bash backup.sh
```

### **7. Menghapus Sesi yang Tidak Digunakan**  
Jika ada sesi yang tidak aktif tetapi masih terdaftar, Anda bisa menghapusnya dengan:  
```bash
screen -X -S nama_sesi quit
```  
Atau jika ingin menghapus semua sesi yang tidak aktif:  
```bash
screen -wipe
```

Dengan menggunakan **screen**, Anda bisa menjalankan proses di latar belakang dan tetap berjalan meskipun Anda logout dari SSH. 🚀

---

### Untuk yang lebih banyak dari `screen`, anda dapat menjalankan perintah:
| **Keterangan**                          | **Command**                      | **Tombol**            |  
|-----------------------------------------|----------------------------------|-----------------------|  
| **Membuat sesi baru tanpa nama**       | `screen`                         | -                     |  
| **Mencantumkan sesi layar yang sudah ada**       | `screen -ls`                         | -                     |  
| **Masuk ke sesi dengan ID tertentu**   | `screen -r [ID]`                 | -                     |  
| **Masuk ke sesi terdetach terakhir**   | `screen -d -r`                   | -                     |  
| **Detach sesi dari tempat lain & masuk** | `screen -D -r namasession`      | -                     |  
| **Memaksa detach sesi di tempat lain** | `screen -d namasession`          | -                     |  
| **Menutup jendela aktif dalam screen** | -                                | `Ctrl + A, K`         |  
| **Menutup semua jendela & keluar**    | -                                | `Ctrl + A, \`         |  
| **Ganti nama jendela aktif**          | -                                | `Ctrl + A, A`         |  
| **Membuka kembali sesi dalam mode tampilan** | `screen -r -x`             | -                     |  
| **Mengirim perintah ke sesi tertentu** | `screen -S namasession -X <cmd>` | -                     |  
| **Menampilkan log aktivitas screen**  | `screen -X logfile <nama_file>`  | -                     |  
| **Merekam output sesi ke file**       | `screen -L`                      | -                     |  
| **Menyalakan mode logging otomatis**  | `screen -X log on`               | -                     |  
| **Mengubah scrollback buffer (default 100)** | `screen -X scrollback 5000` | -                     |  
|**Menghapus semua sesi mati** |	`screen -wipe`|	-
|**Menghapus sesi tertentu** |	`screen -X -S namasession quit`| -

---

### Berikut adalah beberapa perintah lain di `screen` beserta tombol pintasnya:  
| **Tombol**        | **Keterangan**                                      |  
|-------------------|------------------------------------------------------|  
| `Ctrl + A, C`    | Membuat jendela baru dalam sesi `screen`              |  
| `Ctrl + A, N`    | Beralih ke jendela berikutnya                         |  
| `Ctrl + A, P`    | Beralih ke jendela sebelumnya                         |  
| `Ctrl + A, "`    | Menampilkan daftar jendela yang aktif                 |  
| `Ctrl + A, 0-9`  | Berpindah ke jendela dengan nomor tertentu            |  
| `Ctrl + A, D`    | Detach (keluar dari screen tanpa menghentikan sesi)   |  
| `Ctrl + A, K`    | Menutup jendela aktif dalam `screen`                   |  
| `Ctrl + A, [`    | Masuk ke mode scroll (gunakan panah untuk navigasi)   |  
| `Ctrl + A, ]`    | Keluar dari mode scroll                               |  
| `Ctrl + A, X`    | Mengunci layar `screen`, butuh password untuk masuk   |  
| `Ctrl + A, ?`    | Menampilkan daftar semua perintah `screen`            |  

---

### 📌 **Perintah untuk Multiuser (Sharing Session)**
| **Keterangan**                            | **Command**                      |  
|-------------------------------------------|----------------------------------|  
| **Mengaktifkan mode multiuser**           | `screen -S namasession -X multiuser on`  |  
| **Menambahkan user agar bisa join sesi**  | `screen -S namasession -X addacl username` |  
| **User lain masuk ke sesi yang dibagikan** | `screen -x namasession` |  
| **Menghapus user dari sesi**              | `screen -S namasession -X acldel username` | 

### **Apa Itu "Perintah untuk Multiuser (Sharing Session)" di `screen`?**  

**Multiuser (Sharing Session)** dalam `screen` adalah fitur yang memungkinkan **lebih dari satu pengguna** untuk melihat dan berinteraksi dalam satu sesi terminal yang sama. Ini berguna untuk:  

✅ **Kolaborasi** → Dua atau lebih user bisa melihat dan mengetik perintah dalam sesi yang sama.  
✅ **Mentoring/Pelatihan** → Seorang instruktur bisa memperlihatkan proses di terminal kepada user lain.  
✅ **Debugging Bersama** → Beberapa admin bisa mengecek log atau memperbaiki masalah server secara real-time.  

## **🔹 Penjelasan Perintah**
1. **Mengaktifkan Mode Multiuser**  
   ```bash
   screen -S namasession -X multiuser on
   ```
   - Mengubah sesi `screen` agar bisa diakses oleh banyak user.  

2. **Menambahkan User ke Sesi**  
   ```bash
   screen -S namasession -X addacl username
   ```
   - Memberikan izin kepada **user tertentu** agar bisa bergabung ke sesi `screen`.  

3. **User Lain Masuk ke Sesi yang Dibagikan**  
   ```bash
   screen -x namasession
   ```
   - User yang diizinkan bisa melihat dan berinteraksi di dalam sesi yang sama.  

4. **Menghapus User dari Sesi**  
   ```bash
   screen -S namasession -X acldel username
   ```
   - Mencabut akses user agar tidak bisa lagi masuk ke sesi tersebut.  

---

## **🔹 Contoh Penggunaan Multiuser di `screen`**
Misalnya, **admin A** ingin berbagi sesi `screen` dengan **admin B**, maka:  

**Admin A (Pemilik sesi):**  
1. **Membuat sesi baru**  
   ```bash
   screen -S shared_session
   ```
2. **Mengaktifkan mode multiuser**  
   ```bash
   screen -S shared_session -X multiuser on
   ```
3. **Menambahkan admin B ke sesi**  
   ```bash
   screen -S shared_session -X addacl adminB
   ```

**Admin B (Bergabung ke sesi):**  
```bash
screen -x shared_session
```

Sekarang, **admin A dan admin B bisa melihat dan menggunakan terminal yang sama!**
