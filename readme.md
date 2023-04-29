# Dokumentasi PA ASD KEl 16

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

- "datetime" digunakan untuk mengambil waktu saat ini dan melakukan operasi terkait tanggal dan waktu.
- "Queue" digunakan untuk membuat antrian yang akan digunakan dalam program.
- "prettytable" digunakan untuk membuat tabel yang rapi dan mudah dibaca.
- "math" digunakan untuk melakukan operasi matematika yang lebih kompleks.
- "os" digunakan untuk berinteraksi dengan sistem operasi, seperti membaca atau menulis file.
- "time" digunakan untuk melakukan operasi terkait waktu, seperti menghitung waktu eksekusi program.
- "re" yang akan digunakan untuk melakukan validasi ekspresi reguler.
####
- Fungsi menambahkan jadwal pada admin

Blok kode dimulai dengan menerima input jadwal dari pengguna, yang harus dalam format "kota asal - kota tujuan". Kemudian, blok kode memvalidasi format input menggunakan fungsi split() dan len().

Jika input jadwal tidak sesuai format, program mencetak pesan kesalahan "Format jadwal tidak sesuai". Jika input jadwal sesuai, blok kode meminta input jam keberangkatan dan memvalidasi formatnya menggunakan ekspresi reguler.

Jika input jam keberangkatan tidak sesuai format, program mencetak pesan kesalahan "Format jam keberangkatan tidak sesuai". Jika input jam keberangkatan sesuai, blok kode meminta input stok kursi dan memvalidasi bahwa itu adalah bilangan bulat positif.

Jika input stok kursi tidak sesuai format atau tidak positif, program mencetak pesan kesalahan "Stok kursi harus berupa bilangan bulat positif". Jika semua input valid, blok kode memanggil metode "tambah_jadwal" pada objek "admin" dan menambahkan jadwal ke antrian "queue_jadwal". Akhirnya, program mencetak pesan berhasil ditambahkan dengan rincian jadwal, jam keberangkatan, dan stok kursi.

- Fungsi menghapus jadwal pada admin

Meminta input dari pengguna berupa jadwal yang ingin dihapus. Kemudian dilakukan pengecekan apakah format jadwal sesuai atau tidak, jika sesuai maka fungsi hapus_jadwal dipanggil dan jadwal dihapus.

Fungsi hapus_jadwal menerima parameter jadwal yang akan dihapus. Fungsi akan memeriksa apakah antrian jadwal kosong atau tidak. Jika kosong, maka akan ditampilkan pesan bahwa tidak ada jadwal yang tersedia dan fungsi akan selesai.

Jika tidak kosong, maka fungsi akan melakukan pencarian jadwal yang ingin dihapus dengan cara memeriksa setiap elemen dalam antrian jadwal. Jika ditemukan, maka elemen tersebut tidak dimasukkan ke dalam antrian sementara dan dianggap telah dihapus. Jika tidak ditemukan, maka elemen tersebut dimasukkan ke dalam antrian sementara.

Setelah selesai melakukan pencarian, antrian jadwal asli di-update dengan antrian sementara, yang artinya jadwal yang ingin dihapus telah dihapus dari antrian jadwal asli. Kemudian akan ditampilkan pesan bahwa jadwal berhasil dihapus.

- Fungsi menampilkan jadwal pada admin

Menampilkan seluruh jadwal keberangkatan yang tersedia dalam bentuk tabel menggunakan package prettytable.

- Fungsi beli tiket pada pelanggan 

Pengguna diminta untuk memasukkan jadwal keberangkatan dan jumlah kursi yang ingin dipesan. Pertama-tama akan dicek apakah terdapat jadwal yang tersedia di queue_jadwal. Jika tidak ada jadwal yang tersedia, maka akan diberikan pesan bahwa tidak ada jadwal yang tersedia dan fungsi akan langsung selesai. Jika ada, maka jadwal-jadwal tersebut akan dicek satu per satu untuk menemukan jadwal yang sesuai dengan input pengguna.

Jika jadwal yang dicari ditemukan, maka akan dicek apakah jumlah kursi yang diminta kurang dari atau sama dengan jumlah kursi yang tersedia pada jadwal tersebut. Jika iya, maka jumlah kursi pada jadwal tersebut akan dikurangi sesuai jumlah kursi yang diminta oleh pengguna, dan data pembelian akan ditambahkan pada list pembelian. Jika tidak, maka akan diberikan pesan bahwa stok kursi tidak cukup.

Jika jadwal yang dicari tidak ditemukan, maka akan diberikan pesan bahwa jadwal tersebut tidak tersedia.

- Fungsi lihat jadwal pada pelanggan

Menampilkan jadwal yang sesuai dengan kata kunci yang dimasukkan oleh user. User diminta untuk memasukkan kata kunci, kemudian program akan mencari jadwal yang sesuai dengan kata kunci tersebut dalam queue_jadwal.

Fungsi mencari blok yang sesuai dengan kata kunci menggunakan teknik jump search pada queue_jadwal. Ukuran blok ditentukan menggunakan fungsi sqrt dari library math, dan kemudian dilakukan iterasi pada setiap item dalam blok. Jika kata kunci ditemukan dalam jadwal, item ditambahkan ke tabel menggunakan library prettytable.

Jika tabel memiliki setidaknya satu baris, maka tabel ditampilkan. Jika tidak ada jadwal yang sesuai dengan kata kunci, maka pesan akan dicetak ke layar.

- Fungsi lihat history pada pelanggan 

Menampilkan riwayat pembelian tiket pelanggan yang sedang aktif dengan format tabel. Jika pelanggan belum pernah melakukan pembelian tiket, maka akan muncul pesan "Anda belum melakukan pembelian tiket.". Jika pelanggan telah melakukan pembelian tiket, maka fungsi akan menampilkan jadwal keberangkatan, jam keberangkatan, jumlah kursi yang dipesan, dan tanggal pemesanan dari setiap transaksi yang telah dilakukan oleh pelanggan. Data-data tersebut akan ditampilkan dalam bentuk tabel menggunakan library PrettyTable.

### Fitur dan Fungsionalitas

Fitur dan Fungsionalitas untuk Admin:
- Login: Admin harus dapat login ke dalam sistem menggunakan email dan password yang sudah terdaftar.
- Kelola Jadwal: Admin dapat menambah, menghapus, dan menampilkan jadwal keberangkatan bus.
- Menambah jadwal: Admin dapat menambah jadwal bus dengan memasukkan jadwal keberangkatan, jam keberangkatan, dan stok kursi.
- Menghapus jadwal: Admin dapat menghapus jadwal dengan memasukkan kata kunci jadwal yang ingin di hapus.
- Melihat Jadwal: Admin dapat melihat daftar jadwal bus yang sudah diatur dan detailnya seperti jadwal keberangkatan, jam keberangkatan, dan stok kursi.

Fitur dan Fungsionalitas untuk Pelanggan:
- Login: Pelanggan harus dapat login ke dalam sistem menggunakan email dan password yang sudah terdaftar.
- Pembelian Tiket: Pelanggan dapat membeli tiket dengan memilih jadwal yang tersedia dan mengisi jumlah kursi yang akan dipesan
- Melihat Jadwal: Pelanggan dapat melihat jadwal bus yang tersedia dengan memasukkan kata kunci jadwal keberangkatan kemudian akan muncul detailnya seperti jadwal - - - keberangkatan, jam keberangkatan, dan stok kursi yang tersedia
- Melihat History Pembelian: Pelanggan dapat melihat riwayat pembelian tiket yang sudah dilakukan.

### Cara Penggunaan 

- Program akan menampilkan menu utama berupa opsi login sebagai pelanggan atau admin.
![Screenshot (551)](https://user-images.githubusercontent.com/121865360/235320540-782f3720-9ccb-468e-ac30-d8d032dc4d18.png)

- Jika user login sebagai admin maka program akan meminta email dan password admin. Jika email dan password yang dimasukkan benar, program akan menampilkan menu untuk menambah jadwal keberangkatan, menghapus jadwal keberangkatan, menampilkan daftar jadwal keberangkatan, dan log out.
![Screenshot (552)](https://user-images.githubusercontent.com/121865360/235320579-d1a537ed-052f-4cad-b6c4-fe8392474312.png)
![Screenshot (553)](https://user-images.githubusercontent.com/121865360/235320590-ad3ee27b-54e8-4a91-a038-7db8bddf1c11.png)
![Screenshot (554)](https://user-images.githubusercontent.com/121865360/235320609-c63ba643-919f-4942-b0df-960d25e3b98f.png)

- Jika admin memilih untuk menambah jadwal keberangkatan, program akan meminta input jadwal, jam keberangkatan, dan stok kursi. Program akan mengecek format input dan memastikan bahwa jumlah stok kursi adalah bilangan bulat positif sebelum menambahkan jadwal keberangkatan ke dalam daftar.
![Screenshot (555)](https://user-images.githubusercontent.com/121865360/235320648-66e3b9ef-4170-4422-8f41-2fca0f03206e.png)
![Screenshot (556)](https://user-images.githubusercontent.com/121865360/235320633-9737c577-10db-4736-b74e-8a3638feacec.png)

- Jika admin memilih untuk menghapus jadwal keberangkatan, program akan meminta input jadwal yang ingin dihapus. Program akan mengecek format input dan menghapus jadwal keberangkatan dari daftar jika jadwal yang dimasukkan ada dalam daftar.
![Screenshot (596)](https://user-images.githubusercontent.com/121865360/235320792-d634f61c-bdb1-4307-9c47-169d5dc211b5.png)
![Screenshot (597)](https://user-images.githubusercontent.com/121865360/235320809-f5eb51f5-c4ac-4d1b-94bd-761e970ce276.png)

- Jika admin memilih untuk menampilkan daftar jadwal keberangkatan, program akan menampilkan daftar jadwal keberangkatan yang tersedia.
![Screenshot (557)](https://user-images.githubusercontent.com/121865360/235320717-22a3f40a-082d-47e6-95da-894023f50287.png)
![Screenshot (558)](https://user-images.githubusercontent.com/121865360/235320722-efac1f95-7179-44ea-9b33-d19654610abb.png)

- Jika admin memilih untuk logout, program akan kembali ke menu utama.
![Screenshot (598)](https://user-images.githubusercontent.com/121865360/235320845-dfd146c9-4751-4741-bbd8-d5c393419405.png)
![Screenshot (599)](https://user-images.githubusercontent.com/121865360/235321098-3511373f-d20d-4635-8543-7b9f478ceb28.png)

- Jika user login sebagai pelanggan maka program akan meminta email dan password pelanggan. Jika email dan password yang dimasukkan benar, program akan menampilkan menu untuk beli tiket, lihat jadwal, lihat history pembelian dan log out.
![Screenshot (600)](https://user-images.githubusercontent.com/121865360/235321118-a49c5ca3-47eb-47d3-a7e8-66b92bb47c74.png)
![Screenshot (601)](https://user-images.githubusercontent.com/121865360/235321130-5951f586-3154-454a-920b-306caadbb968.png)
![Screenshot (602)](https://user-images.githubusercontent.com/121865360/235321137-4bf0d356-0d79-4d83-992e-24c0951d6fd7.png)

- Jika pelanggan memilih untuk beli tiket, program akan meminta pelanggan untuk memasukkan jadwal keberangkatan dan jumlah kursi yang ingin dipesan. Jika jadwal dan jumlah kursi valid, program akan memanggil metode pesan_kursi() pada objek pelanggan.
![Screenshot (604)](https://user-images.githubusercontent.com/121865360/235321174-0bb09ec6-bd7f-4c6c-9c1c-b7bd41051c32.png)
![Screenshot (606)](https://user-images.githubusercontent.com/121865360/235321184-17b0c51b-9772-4e2a-bdde-68b72246987f.png)

- Jika pelanggan memilih untuk lihat jadwal, program akan meminta pelanggan memasukkan kata kunci jadwal keberangkatan dan menampilkan jadwal yang tersedia. 
![Screenshot (627)](https://user-images.githubusercontent.com/121865360/235321223-733b88f5-7643-4ab9-9558-1328b9d04deb.png)
![Screenshot (654)](https://user-images.githubusercontent.com/121865360/235321233-db957d41-9a6a-47e5-a7bf-673e998b3715.png)

- Jika pelanggan memilih untuk lihat history pembelian, program akan menampilkan detain jadwa keberangkatan, jam keberangkatan, kursi yang dipesan dan waktu memesan.
![Screenshot (655)](https://user-images.githubusercontent.com/121865360/235321266-3226cce8-87c9-4648-9fd2-afdf5fe9dcb8.png)
![Screenshot (656)](https://user-images.githubusercontent.com/121865360/235321274-2f647a34-65c4-47c0-8caf-8039176dd339.png)

- Jika pelanggan memilih untuk log out, program akan keluar dari loop dan kembali ke menu utama. Jika pelanggan memasukkan pilihan yang tidak valid, program akan menampilkan pesan kesalahan dan menampilkan menu kembali.
![Screenshot (657)](https://user-images.githubusercontent.com/121865360/235321318-3347b7ce-1c94-45fa-a615-1e7366dcbf42.png)
![Screenshot (599)](https://user-images.githubusercontent.com/121865360/235321331-08585222-6337-46cf-9a1a-5d7ef36b07c0.png)

### Coding

```
import datetime
from queue import Queue
from prettytable import PrettyTable
import math
import os
import time
import re

# Inisialisasi antrian untuk menyimpan jadwal keberangkatan
queue_jadwal = Queue()

# Membuat class pelanggan
class Pelanggan:
    def __init__(self, email, password, nama):
        self.email = email
        self.password = password
        self.nama = nama
        self.pembelian = []
    
    # Membuat tabel jadwal keberangkatan yang tersedia dengan kata kunci pencarian yang diinputkan oleh pengguna
    # Menggunakan algoritma jump search untuk mencari jadwal keberangkatan yang cocok dengan kata kunci pencaria
    def lihat_jadwal(self):
        try:
            search_query = str(input("Masukkan kata kunci (contoh: Jakarta - Bandung): "))
            x = PrettyTable()
            x.field_names = ["Jadwal Keberangkatan", "Jam Keberangkatan", "Stok Kursi"]
        except ValueError:
            print("\nMohon periksa inputan kembali!")
            time.sleep(2)
            os.system("cls")

    # Menentukan ukuran blok
        block_size = int(math.sqrt(len(queue_jadwal.queue)))
        start = 0
        end = block_size
        while end < len(queue_jadwal.queue) and queue_jadwal.queue[end][0].lower() < search_query.lower():
            start = end
            end += block_size

    # Melakukan jump search pada blok yang sesuai
        idx = start
        while idx < end:
           item = queue_jadwal.queue[idx]
           jadwal, jam_keberangkatan, stok_kursi = item
           if search_query.lower() in jadwal.lower():
              x.add_row([jadwal, jam_keberangkatan, stok_kursi])
              idx += 1
           elif search_query.lower() < jadwal.lower():
               break
           else:
              idx += 1
        if len(x._rows) > 0:
             print(x)
        else:
             print("\nTidak ada jadwal yang sesuai dengan kata kunci yang dimasukkan.")
    
    # Menambahkan pembelian tiket ke daftar pembelian pelanggan dan mengurangi jumlah kursi yang tersedia,
    # jika jumlah kursi yang diminta tersedia. Jika stok kursi tidak mencukupi, akan muncul pesan kesalahan
    def pesan_kursi(self, jadwal, jumlah_kursi):
        if queue_jadwal.empty():
            print("\nTidak ada jadwal yang tersedia.")
            return
        found = False
        for idx, item in enumerate(queue_jadwal.queue):
            if item[0] == jadwal:
                found = True
                if int(item[2]) >= jumlah_kursi:
                    queue_jadwal.queue[idx] = (item[0], item[1], int(item[2]) - jumlah_kursi)
                    self.pembelian.append((item[0], item[1], jumlah_kursi, datetime.datetime.now()))
                    print(f"Terima kasih {self.nama}! Pembelian tiket untuk jadwal {jadwal} dengan jumlah kursi {jumlah_kursi} telah berhasil.")
                else:
                    print(f"Maaf, stok kursi untuk jadwal {jadwal} tidak cukup.")
                break
        if not found:
            print(f"Maaf, jadwal {jadwal} tidak tersedia.")
    
    # Menampilkan riwayat pembelian tiket oleh pelanggan dengan menggunakan PrettyTable
    def lihat_history(self):
        if not self.pembelian:
            print("\nAnda belum melakukan pembelian tiket.")
        else:
            x = PrettyTable()
            x.field_names = ["Jadwal Keberangkatan", "Jam Keberangkatan", "Jumlah Kursi", "Tanggal Pemesanan"]
            for pembelian in self.pembelian:
                jadwal, jam_keberangkatan, jumlah_kursi, tanggal_pemesanan = pembelian
                try:
                    tanggal_str = tanggal_pemesanan.strftime('%Y-%m-%d %H:%M:%S')
                except ValueError:
                    tanggal_str = 'unknown'
                x.add_row([jadwal, jam_keberangkatan, jumlah_kursi, tanggal_str])
            print(x)

# Membuat class admin
class Admin:
    def __init__(self, email, password):
        self.email = email
        self.password = password
    
    # Menambahkan jadwal keberangkatan ke dalam antrian
    def tambah_jadwal(self, jadwal, jam_keberangkatan, stok_kursi):
        queue_jadwal.put((jadwal, jam_keberangkatan, stok_kursi))
        print(f"\nJadwal {jadwal} dengan jam keberangkatan {jam_keberangkatan} dan stok kursi {stok_kursi} berhasil ditambahkan.")
    
    # Menghapus jadwal keberangkatan dari antrian
    def hapus_jadwal(self, jadwal):
        if queue_jadwal.empty():
            print("\nTidak ada jadwal yang tersedia.")
            return

        temp_queue = Queue()
        found = False
        while not queue_jadwal.empty():
            item = queue_jadwal.get()
            if item[0] == jadwal:
                found = True
            else:
                temp_queue.put(item)
                
        if not found:
            print(f"Jadwal {jadwal} tidak ditemukan.")
        else:
            queue_jadwal.queue = temp_queue.queue
            print(f"Jadwal {jadwal} berhasil dihapus.")
    
    # Menampilkan jadwal keberangkatan yang tersedia dengan menggunakan PrettyTable
    def tampilkan_jadwal(self):
        x = PrettyTable()
        x.field_names = ["Jadwal Keberangkatan", "Jam Keberangkatan", "Stok Kursi"]
        for item in sorted(list(queue_jadwal.queue), key=lambda x: x[1]):
            jadwal, jam_keberangkatan, stok_kursi = item
            x.add_row([jadwal, jam_keberangkatan, stok_kursi])
        print(x)

# Inisialisasi list admin_list dan pelanggan_list
admin_list = [Admin("admin@gmail.com", "pass")]
pelanggan_list = [Pelanggan("pelanggan@gmail.com", "word", "Lila")]

os.system("cls")

# Mengulang program utama, yang menampilkan menu pilihan untuk pelanggan dan admin, dan menampilkan fungsi
# yang sesuai dengan pilihan pengguna. Program akan berhenti jika pengguna memilih untuk keluar dari program
def mulai():
    print("="*46)
    print("Selamat datang di aplikasi pemesanan tiket bus")
    print("="*46)

    while True:
        # Pilihan login
        print("\nSilakan pilih opsi login:")
        print("1. Admin")
        print("2. Pelanggan")
        try:
            try:
                login_choice = str(input("\nMasukkan pilihan: "))
                time.sleep(2)
                os.system("cls")

                if login_choice == "1":
                    try:
                        # Login sebagai admin
                        email = str(input("Masukkan email admin: "))
                        password = str(input("Masukkan password admin: "))

                        # Cek apakah username dan password admin sudah benar
                        for admin in admin_list:
                            if admin.email == email and admin.password == password:
                                time.sleep(2)
                                os.system ("cls")
                                print("Anda telah masuk sebagai admin.")
                                print("="*31)

                                # Lanjutkan dengan program untuk admin
                                while True:
                                    print("\nSilakan pilih opsi:")
                                    print("1. Tambah jadwal")
                                    print("2. Hapus jadwal")
                                    print("3. Tampilkan jadwal")
                                    print("4. Logout")
                                    try:
                                        admin_choice = str(input("\nMasukkan pilihan: "))
                                        time.sleep(2)
                                        os.system("cls")

                                        if admin_choice == "1":
                                            try:
                                                jadwal = input("Masukkan jadwal (contoh: Jakarta - Bandung): ")
                                                if len(jadwal.split(" - ")) != 2:
                                                    print("Format jadwal tidak sesuai")
                                                else:
                                                    jam_keberangkatan = input("Masukkan jam keberangkatan (contoh: 08.00): ")
                                                    if not re.match(r"\d{2}.\d{2}", jam_keberangkatan):
                                                        print("Format jam keberangkatan tidak sesuai")
                                                    else:
                                                        stok_kursi = input("Masukkan stok kursi: ")
                                                        if not stok_kursi.isdigit() or int(stok_kursi) <= 0:
                                                            print("Stok kursi harus berupa bilangan bulat positif")
                                                        else:
                                                            admin.tambah_jadwal(jadwal, jam_keberangkatan, stok_kursi)
                                            except ValueError:
                                                print("\nMohon periksa inputan kembali!")
                                                time.sleep(2)
                                                os.system("cls")

                                        elif admin_choice == "2":
                                            try:
                                                jadwal = input("Masukkan jadwal yang ingin dihapus (contoh: Jakarta - Bandung): ")
                                                if len(jadwal.split(" - ")) != 2:
                                                    print("Format jadwal tidak sesuai")
                                                else:
                                                    admin.hapus_jadwal(jadwal)
                                            except ValueError:
                                                print("\nMohon periksa inputan kembali!")
                                                time.sleep(2)
                                                os.system("cls")

                                        elif admin_choice == "3":
                                            admin.tampilkan_jadwal()

                                        elif admin_choice == "4":
                                            break

                                        else:
                                            print("\nPilihan tidak valid")
                                            time.sleep(2)
                                            os.system("cls")

                                    except ValueError:
                                        print("\nMohon periksa inputan kembali!")
                                        time.sleep(2)
                                        os.system("cls")

                            else:
                                print("\nEmail atau password salah. Silakan coba lagi.")
                                time.sleep(2)
                                os.system("cls")

                    except ValueError:
                        print("\nMasukan email atau password dengan benar!")
                        time.sleep(2)
                        os.system("cls")

                elif login_choice == "2":
                    try:
                        # Login sebagai pelanggan
                        email = str(input("Masukkan email pelanggan: "))
                        password = str(input("Masukkan password pelanggan: "))

                        # Cek apakah username dan password pelanggan sudah benar 
                        for pelanggan in pelanggan_list:
                            if pelanggan.email == email and pelanggan.password == password:
                                time.sleep(2)
                                os.system ("cls")
                                print(f"Anda telah masuk sebagai pelanggan {pelanggan.nama}.")
                                print("="*40)

                                # Lanjutkan dengan program untuk pelanggan
                                while True:
                                    print("\nSilakan pilih opsi:")
                                    print("1. Beli tiket")
                                    print("2. Lihat jadwal")
                                    print("3. Lihat History pembelian")
                                    print("4. Logout")
                                    try:
                                        pelanggan_choice = str(input("\nMasukkan pilihan: "))
                                        time.sleep(2)
                                        os.system("cls")

                                        if pelanggan_choice == "1":
                                            try:
                                                jadwal = input("Masukkan jadwal keberangkatan (contoh: Jakarta - Bandung): ")
                                                if len(jadwal.split(" - ")) != 2:
                                                    print("Format jadwal tidak sesuai")
                                                else:
                                                    jumlah_kursi = input("Masukkan jumlah kursi yang ingin dipesan: ")
                                                    if not jumlah_kursi.isdigit() or int(jumlah_kursi) <= 0:
                                                        print("Stok kursi harus berupa bilangan bulat positif")
                                                    else:
                                                        pelanggan.pesan_kursi(jadwal, int(jumlah_kursi))
                                            except ValueError:
                                                print("\nMohon periksa inputan kembali!")
                                                time.sleep(2)
                                                os.system("cls")

                                        elif pelanggan_choice == "2":
                                            pelanggan.lihat_jadwal()

                                        elif pelanggan_choice == "3":
                                            pelanggan.lihat_history()

                                        elif pelanggan_choice == "4":
                                            break

                                        else:
                                            print("\nPilihan tidak valid")
                                            time.sleep(2)
                                            os.system("cls")

                                    except ValueError:
                                        print("\nMohon periksa inputan kembali!")
                                        time.sleep(2)
                                        os.system("cls")

                            else:
                                print("\nEmail atau password salah. Silakan coba lagi.")
                                time.sleep(2)
                                os.system("cls")

                    except ValueError:
                        print("\nMasukan email atau password dengan benar!")
                        time.sleep(2)
                        os.system("cls")

                else:
                    print("\nPilihan tidak valid")
                    time.sleep(2)
                    os.system("cls")

            except UnboundLocalError:
                print("\nMohon periksa inputan kembali!")
                time.sleep(2)
                os.system("cls")  

        except KeyboardInterrupt: # ctrl + c
            print("\nProgram Tidak Mengerti")
            time.sleep(2)
            os.system("cls")
            mulai()

mulai()
```
