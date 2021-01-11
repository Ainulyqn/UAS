**Nama        : Ainul Yaqin** <br>
**NIM         : 312010423** <br>
**Kelas       : TI.20.A.1** <br>
**Mata Kuliah : Bahasa Pemrograman** <br>

# Soal <br>
![gambar](gambar/gambar1.png)

# Struktur Pekage dan Module <br>
![gambar](gambar/gambar2.png) <br>
* Terdapat 2 package dengan nama Model dan View <br>
* Package Model berisi module tambah data, ubah data, hapus data dan cari data <br>
* Package View berisi module tampilkan <br>
* Package Controller berisi module core, yang artinya seluruh proses inti melibatkan module core tersebut <br>
* dan yang terakhir ada module main.py, yang nanti akan di eksekusi <br>

# Penjelasan

**Controller** <br>
* `data = {}` untuk menampung list data yang nanti akan terinput <br>
* Menambahkan fungsi yang nanti nya akan di deklarasikan di setiap module nya, `def input_nama(): def input_nim():` dan yg lainnya, yang nanti akan di masukkan kedalam `data={}` <br>
* Nilai akhir didapat dari `nilai_akhir = (nilai_tugas)*30/100 + (nilai_uts)*35/100 + (nilai_uas)*35/100`

**Model** <br>
Tambah data
 * Deklarasikan fungsi `def tambah_data():` <br>
 * `nama = input("Masukan nama: ")` lalu tambahkan input nama, nim, nilai tugas, uts, uas <br>
 * `nilai_akhir = (nilai_tugas)*30/100 + (nilai_uts)*35/100 + (nilai_uas)*35/100` untuk nilai akhir diambil dari perhitungan 3 komponen nilai (nilai_tugas: 30%, nilai_uts: 35%, nilai_uas: 35%) <br>
 * `data[nama] = [nama, nim, nilai_tugas, nilai_uts, nilai_uas, nilai_akhir]` kita akan masukkan data yang tadi kita input ke dalam `data[nama]` <br>
 * lalu cetak `print()`

Ubah Data
* deklarasikan fungsi `def ubah_data():` <br>
* `nama = input("Masukan nama untuk mengubah data: ")` kita akan menginput data yang nanti akan di ubah <br>
* `if nama in data.keys(): print("Mau mengubah apa?")` jika 'nama' dari di dalam 'data' maka akan mengembalikan daftar menggunakan fungsi `keys()` lalu di cetak lah `print()` <br>
* `sub_data = input("(Semua), (Nama), (NIM), (Tugas), (UTS), (UAS) : ")` membuat menu ubah di dalam `sub_data` <br>
* `if sub_data.lower() == "semua":` ambil kata kunci 'semua' di dalam sub_data jika 'semua' maka input `data[nama][1] = input("Ubah NIM:") data[nama][2] = int(input("Ubah Nilai Tugas: ")) data[nama][3] = int(input("Ubah Nilai UTS: ")) data[nama][4] = int(input("Ubah Nilai UAS: "))` <br>
* `data[nama][5] = data[nama][2] *30/100 + data[nama][3]*35/100 + data[nama][4] *35/100` kita dapatkan nilai akhir dengan diambil dari perhitungan 3 komponen nilai (tugas: 30%, uts: 35%, uas: 35%), <br>
* lalu cetak `print("\nBerhasil ubah data!")` <br>
* Jika kita ingin mengubah data tertentu maka `elif sub_data.lower() == "nim": data[nama][1] = input("NIM:")` dan berlaku juga untuk nilai tugas, UTS dan UAS <br>
* lalu cetak `print("\nBerhasil ubah data!")` <br>
* `else: print("'{}' tidak ditemukan.".format(nama))` jika kita salah dalam memasukkan nama untuk mengubah data maka akan muncul 'nama tidak di temukan' <br>

Cari Data <br>
* deklarasikan fungsi `def cari_data():` <br>
* `if nama in data.keys():` kita mengambil list 'nama' di dalam 'data' menggunakan pengkondisian <br>
* maka cetak `print("Nama: {0}\nNIM : {1}\nNilai Tugas: {2}\nUTS: {3}\nUAS: {4}\nNilai akhir: {5}"` untuk menampilkan data yang tersedia <br>
* `else: print("'{}' tidak ditemukan.".format(nama))` jika data yang kita input salah/tidak ditemukan maka akan tercetak 'nama tidak di temukan' <br>

Hapus Data <br>
* deklarasikan fungsi `def hapus_data():` <br>
* `nama = input("Masukan nama untuk menghapus data : ")` kita akan menginput data yang nanti akan di hapus <br>
* `if nama in data.keys():` kita mengambil list 'nama' di dalam 'data' menggunakan pengkondisian <br>
* `del data[nama]` hapus semua 'nama' yang ada di dalam 'data' <br>
* jika sudah maka cetak `print("sub_data '{}' berhasil dihapus.".format(nama))` <br>
* `else: print("'{}' tidak ditemukan.".format(nama)`) jika data yang kita input salah/tidak ditemukan maka akan tercetak 'nama tidak di temukan' <br>

**View** <br>
Lihat Data
* deklarasikan fungsi `def lihat_data():` Kita menggunakan kondisi percabangan if, ambil data dari `data` <br>
* lalu cetak `print()` <br>

Yang terakhir eksekusi file main.py

`from controller.core import data` <br>
`from model.tambah import *` <br>
`from model.ubah import *` <br>
`from model.hapus import *` <br>
`from model.cari import *`<br>
`from view.tampilkan import *`

`    #print("Sebelum akses program izin dulu sama yang punya :p")` <br>
`    #break` <br>

`#Mulai` <br>
`print("===============================================================")` <br>
`print("|                     Program Input Nilai                     |")` <br>
`print("===============================================================")` <br>

`while True:` <br>
`    print("\n")` <br>
`    menu = input("(L) Lihat, (T) Tambah, (H) Hapus, (U) Ubah, (C) Cari, (K) Keluar: ")` <br>
`    print("\n")` <br>

`    # menu` <br>
`    if menu.lower() == 't':` <br>
`        tambah_data()` <br>

`    elif menu.lower() == 'c':` <br>
`        cari_data()` <br>

`    elif menu.lower() == 'l':` <br>
`        lihat_data()` <br>

`    elif menu.lower() == 'u':` <br>
`        ubah_data()` <br>

`    elif menu.lower() == 'h':` <br>
`        hapus_data()` <br>

`    # Keluar` <br>
`    elif menu.lower() == 'k':` <br>
`        break` <br>

`    else:` <br>
`        print("Upss ada yang salah, silahkan cek kembali.")`

# Output

Tambah Data <br>
![gambar](gambar/gambar3.png)

Ubah Data <br>
![gambar](gambar/gambar4.png)

Lihat data <br>
![gambar](gambar/gambar5.png)

Cari Data <br>
![gambar](gambar/gambar6.png)

hapus data <br>
![gambar](gambar/gambar7.png)

# Flowchart <br>
![gambar](gambar/flowchart.png)