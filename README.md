# Welcome to Git Tutorial

----------

## Cara Install Git di Linux
- **sudo apt install git** atau
- **sudo apt-get install** git
- pada **fedora yum install git**
- **git --version** (untuk check versi git yang di install)

## Cara Install Git di Windows
- Download Git [https://git-scm.com/](https://git-scm.com/ "https://git-scm.com/")
- Cari di [www.google.com](www.google.com) cara install git

----------

## Konfigurasi Awal Git
- git config --global user.name "root"
- git config --global user.email root@git.com
- git config --list (untuk periksa konfigurasinya)

----------

## Membuat Repositori
- git init projectname
- git init . (membuat repositori pada direktori saat ini / *working directory*)
- buat file baru dengan nama **.gitignore** (merupakan sebuah file yang berisi daftar nama-nama file dan direktori yang akan diabaikan oleh Git)

----------

## Simpan Perubahan Revisi dengan Git Commit
- git status

### Tiga Kelompok Kondisi File dalam Git
- **Modified** (Modified adalah kondisi dimana revisi atau perubahan sudah dilakukan, tetapi belum ditandai dan belum disimpan di version control. Contohnya pada gambar di atas, ada tiga file HTML yang dalam kondisi modified)
- **Staged** (Staged adalah kondisi dimana revisi sudah ditandai, tetapi belum disimpan di version control. Untuk mengubah kondisi file dari modified ke staged gunakan perintah git add nama_file) 
- **Commited** (Commited adalah kondisi dimana revisi sudah disimpan di version control. perintah untuk mengubah kondisi file dari staged ke commited adalah git commit)

### Membuat Revisi Git
- git add. (untuk menambahkan semua file ke dalam git)
- git add nama_file.html (untuk menambah sesuai dengan nama file)
- git add *.html (untuk menambah sesuai dengan type file)
- git status
- git commit -m "Commit pertama"
- git status

----------

## Melihat Catatan Log Revisi
- git log (untuk melihat semua log revisi)
- git log --oneline (untuk melihat log lebih sedikit)
- git log cf08ca0837cf26f1c595be36bb3a6b815e311be1 (Untuk melihat log pada revisi tertentu, kita bisa memasukan nomer revisi/commit)
- git log nama_file (Untuk melihat revisi pada file tertentu)
- git log --author='username' (Untuk melihat revisi yang di lakukan oleh author)

----------

## Melihat Perbandingan Revisi dengan Git Diff
- git diff cf08ca0837cf26f1c595be36bb3a6b815e311be1 (fungsinya untuk melihat perbedaan perubahan di revisi)
- git diff nama_file.html (Melihat Perbandingan pada File)
- git diff nomer_commit nomer_commit (Melihat Perbandingan antar Revisi/Commit)
- git diff nama_cabang nama_cabang (Perbandingan Antar Cabang/Branch)

----------

## Perintah untuk Membatalkan Revisi/Commit
- git checkout nama_file (Membatalkan Perubahan Jika revisi kita belum staged ataupun committed)
- git status (Hati-hati! Terkadang perintah ini sangat berbahaya, karena akan menghapus perubahan yang baru saja dilakukan)

### Membatalkan Perubahan File yang Sudah dalam Kondisi staged

- git reset nama_file (Membatalkan Perubahan File yang Sudah dalam Kondisi staged)
- git status (Jika file nama_file sudah dalam kondisi modified, kita bisa membatalkan perubahannya dengan perintah git checkout)
- git status

### Membatalkan Perubahan File yang Sudah dalam Kondisi Commited
- git log
- git checkout nomor_commit nama_file 
- git reset nama_file
- git checkout nomor_commit (Perintah ini akan mengembalikan semua file dalam kondisi pada nomer commit yang diberikan, namun bersifat temporer)

### Kembali ke 3 Commit sebelumnya

- git checkout HEAD~3 nama_file (Untuk kembali ke 3 commit sebelumnya, kita bisa menggunakan perintah berikut)

### Membatalkan Semua Perubahan yang ada

- git revert -n nomer_commit (Jika kita ingin mengembalikan semua file ke suatu commit)


----------

## Membuat Percabangan untuk Mencegah Konflik

- git branch nama_branch (Untuk membuat branch baru)
- git branch (untuk melihat branch aktif dengan tand *)
- git checkout nama_branch (untuk berpindah branch)
- git merge nama_branch (untuk menggabungkan branch ke branch yang aktif saat ini)
- git branch -d nama_branch (untuk menghapus branch)

### Mengatasi Bentrok
- Buka file yang bentrok dengan text editor, kedua kode cabang dipisahkan dengan tanda ====== kemudian eliminasi kode yang akan digunakan

----------
## Perbedaan Git checkout, Git Reset, dan Git Revert
- **Git Checkout** Perintah git checkout seperti mesin waktu, kita bisa kembalikan kondisi file proyek seperti waktu yang dituju
- git checkout nomor_commit Maka semua file akan dikembalikan seperti keadaan pada nomer commit tersebut
- git checkout -b nama_cabang nomer_commit (Membuat cabang baru berdasarkan kondisi kode di masa lalu). Cara ini bisa kita ibaratkan seperti menulis cerita baru dengan plot yang berbeda.
- **Git Reset** sering disebut sebagai perintah berbahaya yang dapat menghancurkan catatan sejarah perubahan
- git reset --soft nomor_commit (akan mengebalikan dengan kondisi file dalam keadaan staged)
- git reset --mixed nomor_commit (akan mengebalikan dengan kondisi file dalam keadaan modified)
- git reset --hard nomor_commit (akan mengebalikan dengan kondisi file dalam keadaan commited)
- **Git Revert** Revert artinya mengembalikan. Perintah ini lebih aman daripada git reset, karena tidak akan menghapus catatan sejarah revisi. Revert akan akan mengambil kondisi file yang ada di masa lalu, kemudian menggabungkannya dengan commit terakhir.
- git revert nomor_commit

----------

## Remote Repositori
- Buat Repository Git (Github, Bitbucket, Gitlab dll)
- git remote add github url_respository (Menambahkan Git Remote Respository)
- git remote -v
- git remote rename nama_lama nama_baru (Ubah nama remote)
- git remote remove url_respository (Menghapus Git Remote Respository)
- git remote set-url origin url_respository (Mengganti Git Remote Respository)
- git push url_respository master

### Mengambil Revisi dari Remote Repository
- git fetch nama_remote nama_cabang (Hanya akan mengambil revisi (commit) saja dan tidak langsung melakukan penggabungan (merge) terhadap repository lokal)
- git full nama_remote nama_cabang akan mengambil revisi (commit) dan langsung melakukan penggabungan (merge) terhadap repository lokal
- Bila kita sudah membuat perubahan di repository lokal, maka sebaiknya menggunakan git fetch agar perubahan yang kita lakukan tidak hilang. Namun, bila kita tidak pernah melakukan perubahan apapun dan ingin mengambil versi terakhir dari repository remote, maka gunakanlah git pull.
- done, thank you.
