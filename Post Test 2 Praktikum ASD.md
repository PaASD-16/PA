# Dokumantasi PA ASD KEl 16

##### Anggota : 
##### 1. Ayu Cahyarani (2209116008)
##### 2. Helen Amalia Dengen (2209116009)
##### 3. Harry Chandra (2209116014)
####
##### Prodi : Sistem Informasi A 22
###
### Deskripsi Program

Program ini adalah program untuk pemesanan tiket bus, dimana terdapat 2 tipe pengguna yaitu Admin dan Pelanggan. Admin dapat menambahkan atau menghapus jadwal keberangkatan dan melihat daftar jadwal keberangkatan yang tersedia, sedangkan Pelanggan dapat membeli tiket, melihat daftar jadwal keberangkatan yang tersedia, dan melihat history pembelian tiket.
 
### Struktur Project

Berikut adalah struktur project program pemesanan tiket bus:

Modul yang digunakan

"datetime" digunakan untuk mengambil waktu saat ini dan melakukan operasi terkait     tanggal dan waktu.
"Queue" digunakan untuk membuat antrian yang akan digunakan dalam program.
"prettytable" digunakan untuk membuat tabel yang rapi dan mudah dibaca.
"math" digunakan untuk melakukan operasi matematika yang lebih kompleks.
"os" digunakan untuk berinteraksi dengan sistem operasi, seperti membaca atau         menulis file.
"time" digunakan untuk melakukan operasi terkait waktu, seperti menghitung waktu     eksekusi program.
"re" yang akan digunakan untuk melakukan validasi ekspresi reguler.

Fungsi menambahkan jadwal pada admin

Blok kode dimulai dengan menerima input jadwal dari pengguna, yang harus dalam format "kota asal - kota tujuan". Kemudian, blok kode memvalidasi format input menggunakan fungsi split() dan len().

Jika input jadwal tidak sesuai format, program mencetak pesan kesalahan "Format jadwal tidak sesuai". Jika input jadwal sesuai, blok kode meminta input jam keberangkatan dan memvalidasi formatnya menggunakan ekspresi reguler.

Jika input jam keberangkatan tidak sesuai format, program mencetak pesan kesalahan "Format jam keberangkatan tidak sesuai". Jika input jam keberangkatan sesuai, blok kode meminta input stok kursi dan memvalidasi bahwa itu adalah bilangan bulat positif.

Jika input stok kursi tidak sesuai format atau tidak positif, program mencetak pesan kesalahan "Stok kursi harus berupa bilangan bulat positif". Jika semua input valid, blok kode memanggil metode "tambah_jadwal" pada objek "admin" dan menambahkan jadwal ke antrian "queue_jadwal". Akhirnya, program mencetak pesan berhasil ditambahkan dengan rincian jadwal, jam keberangkatan, dan stok kursi.

Fungsi menghapus jadwal pada admin

Meminta input dari pengguna berupa jadwal yang ingin dihapus. Kemudian dilakukan pengecekan apakah format jadwal sesuai atau tidak, jika sesuai maka fungsi hapus_jadwal dipanggil dan jadwal dihapus.

Fungsi hapus_jadwal menerima parameter jadwal yang akan dihapus. Fungsi akan memeriksa apakah antrian jadwal kosong atau tidak. Jika kosong, maka akan ditampilkan pesan bahwa tidak ada jadwal yang tersedia dan fungsi akan selesai.

Jika tidak kosong, maka fungsi akan melakukan pencarian jadwal yang ingin dihapus dengan cara memeriksa setiap elemen dalam antrian jadwal. Jika ditemukan, maka elemen tersebut tidak dimasukkan ke dalam antrian sementara dan dianggap telah dihapus. Jika tidak ditemukan, maka elemen tersebut dimasukkan ke dalam antrian sementara.

Setelah selesai melakukan pencarian, antrian jadwal asli di-update dengan antrian sementara, yang artinya jadwal yang ingin dihapus telah dihapus dari antrian jadwal asli. Kemudian akan ditampilkan pesan bahwa jadwal berhasil dihapus.

Fungsi menampilkan jadwal pada admin

Menampilkan seluruh jadwal keberangkatan yang tersedia dalam bentuk tabel menggunakan package prettytable.

Fungsi beli tiket pada pelanggan 

Pengguna diminta untuk memasukkan jadwal keberangkatan dan jumlah kursi yang ingin dipesan. Pertama-tama akan dicek apakah terdapat jadwal yang tersedia di queue_jadwal. Jika tidak ada jadwal yang tersedia, maka akan diberikan pesan bahwa tidak ada jadwal yang tersedia dan fungsi akan langsung selesai. Jika ada, maka jadwal-jadwal tersebut akan dicek satu per satu untuk menemukan jadwal yang sesuai dengan input pengguna.

Jika jadwal yang dicari ditemukan, maka akan dicek apakah jumlah kursi yang diminta kurang dari atau sama dengan jumlah kursi yang tersedia pada jadwal tersebut. Jika iya, maka jumlah kursi pada jadwal tersebut akan dikurangi sesuai jumlah kursi yang diminta oleh pengguna, dan data pembelian akan ditambahkan pada list pembelian. Jika tidak, maka akan diberikan pesan bahwa stok kursi tidak cukup.

Jika jadwal yang dicari tidak ditemukan, maka akan diberikan pesan bahwa jadwal tersebut tidak tersedia.

Fungsi lihat jadwal pada pelanggan

Menampilkan jadwal yang sesuai dengan kata kunci yang dimasukkan oleh user. User diminta untuk memasukkan kata kunci, kemudian program akan mencari jadwal yang sesuai dengan kata kunci tersebut dalam queue_jadwal.

Fungsi mencari blok yang sesuai dengan kata kunci menggunakan teknik jump search pada queue_jadwal. Ukuran blok ditentukan menggunakan fungsi sqrt dari library math, dan kemudian dilakukan iterasi pada setiap item dalam blok. Jika kata kunci ditemukan dalam jadwal, item ditambahkan ke tabel menggunakan library prettytable.

Jika tabel memiliki setidaknya satu baris, maka tabel ditampilkan. Jika tidak ada jadwal yang sesuai dengan kata kunci, maka pesan akan dicetak ke layar.

Fungsi lihat history pada pelanggan 

Menampilkan riwayat pembelian tiket pelanggan yang sedang aktif dengan format tabel. Jika pelanggan belum pernah melakukan pembelian tiket, maka akan muncul pesan "Anda belum melakukan pembelian tiket.". Jika pelanggan telah melakukan pembelian tiket, maka fungsi akan menampilkan jadwal keberangkatan, jam keberangkatan, jumlah kursi yang dipesan, dan tanggal pemesanan dari setiap transaksi yang telah dilakukan oleh pelanggan. Data-data tersebut akan ditampilkan dalam bentuk tabel menggunakan library PrettyTable.

### Fitur dan Fungsionalitas

Fitur dan Fungsionalitas untuk Admin:
Login: Admin harus dapat login ke dalam sistem menggunakan email dan password yang sudah terdaftar.
Kelola Jadwal: Admin dapat menambah, menghapus, dan menampilkan jadwal keberangkatan bus.
Menambah jadwal: Admin dapat menambah jadwal bus dengan memasukkan jadwal keberangkatan, jam keberangkatan, dan stok kursi.
Menghapus jadwal: Admin dapat menghapus jadwal dengan memasukkan kata kunci jadwal yang ingin di hapus.
Melihat Jadwal: Admin dapat melihat daftar jadwal bus yang sudah diatur dan detailnya seperti jadwal keberangkatan, jam keberangkatan, dan stok kursi.

Fitur dan Fungsionalitas untuk Pelanggan:
Login: Pelanggan harus dapat login ke dalam sistem menggunakan email dan password yang sudah terdaftar.
Pembelian Tiket: Pelanggan dapat membeli tiket dengan memilih jadwal yang tersedia dan mengisi jumlah kursi yang akan dipesan
Melihat Jadwal: Pelanggan dapat melihat jadwal bus yang tersedia dengan memasukkan kata kunci jadwal keberangkatan kemudian akan muncul detailnya seperti jadwal keberangkatan, jam keberangkatan, dan stok kursi yang tersedia
Melihat History Pembelian: Pelanggan dapat melihat riwayat pembelian tiket yang sudah dilakukan.

### Cara Penggunaan 

Program akan menampilkan menu utama berupa opsi login sebagai pelanggan atau admin.

Jika user login sebagai admin maka program akan meminta email dan password admin. Jika email dan password yang dimasukkan benar, program akan menampilkan menu untuk menambah jadwal keberangkatan, menghapus jadwal keberangkatan, menampilkan daftar jadwal keberangkatan, dan log out.

Jika admin memilih untuk menambah jadwal keberangkatan, program akan meminta input jadwal, jam keberangkatan, dan stok kursi. Program akan mengecek format input dan memastikan bahwa jumlah stok kursi adalah bilangan bulat positif sebelum menambahkan jadwal keberangkatan ke dalam daftar.

Jika admin memilih untuk menghapus jadwal keberangkatan, program akan meminta input jadwal yang ingin dihapus. Program akan mengecek format input dan menghapus jadwal keberangkatan dari daftar jika jadwal yang dimasukkan ada dalam daftar.

Jika admin memilih untuk menampilkan daftar jadwal keberangkatan, program akan menampilkan daftar jadwal keberangkatan yang tersedia.

Jika admin memilih untuk logout, program akan kembali ke menu utama.

Jika user login sebagai pelanggan maka program akan meminta email dan password pelanggan. Jika email dan password yang dimasukkan benar, program akan menampilkan menu untuk beli tiket, lihat jadwal, lihat history pembelian dan log out.

Jika pelanggan memilih untuk beli tiket, program akan meminta pelanggan untuk memasukkan jadwal keberangkatan dan jumlah kursi yang ingin dipesan. Jika jadwal dan jumlah kursi valid, program akan memanggil metode pesan_kursi() pada objek pelanggan.

Jika pelanggan memilih untuk lihat jadwal, program akan meminta pelanggan memasukkan kata kunci jadwal keberangkatan dan menampilkan jadwal yang tersedia. 

Jika pelanggan memilih untuk lihat history pembelian, program akan menampilkan detain jadwa keberangkatan, jam keberangkatan, kursi yang dipesan dan waktu memesan.

Jika pelanggan memilih untuk log out, program akan keluar dari loop dan kembali ke menu utama. Jika pelanggan memasukkan pilihan yang tidak valid, program akan menampilkan pesan kesalahan dan menampilkan menu kembali.

