# Enkripsi File di Ubuntu

Terkadang Anda mungkin perlu mengenkripsi folder di Linux. Linux menyediakan banyak alat sederhana untuk tujuan ini. gpg adalah alat paling populer yang digunakan untuk enkripsi file di Linux. Itu sudah diinstal di sebagian besar distribusi Linux dan tidak memerlukan pengaturan tambahan. Pada artikel ini, kita akan belajar cara mengenkripsi folder di Linux. Anda dapat menggunakan langkah-langkah ini di hampir semua sistem Linux.

## 1. Konversi Direktori ke File
Utilitas gpg hanya dapat mengenkripsi file. Jadi pertama-tama kita cukup mengarsipkan folder ke dalam file ```.tar```. Katakanlah Anda memiliki folder bernama ```/home/data``` di sistem Anda. Berikut adalah perintah untuk mengubah direktori menjadi arsip ```.tar```.

```
tar czf data.tar.gz /home/data
```

## 2. Siapkan Kunci

Jalankan perintah berikut untuk menghasilkan kunci untuk enkripsi.

```
gpg --gen-key
```

Anda akan melihat daftar opsi, meminta Anda untuk memilih jenis kunci yang akan dibuat dan jenis metode enkripsi untuk kunci tersebut. Selanjutnya, Anda akan ditanya panjang kunci. Untuk memilih opsi default dalam setiap kasus, tekan saja tombol enter.

Terakhir, Anda akan ditanya apakah Anda ingin menetapkan kedaluwarsa untuk kunci ini. Jika Anda ingin menggunakannya selamanya, masukkan 0.

Selanjutnya, Anda akan diminta untuk memasukkan kata sandi untuk kunci tersebut. Frasa sandi ini untuk kunci Anda dan file yang akan Anda enkripsi menggunakan kunci ini. Ini untuk melindungi file kunci jika dicuri.

## 3. Import Key

```
gpg --import public.key
```

## 4. Enkripsi File
Selanjutnya, gunakan perintah gpg untuk mengenkripsi file ```.tar.gz```.

```
gpg -e -r USERNAME ~USERNAME/filename
```

Berikut adalah contoh perintah untuk mengenkripsi file ```.tar.gz```.

```
gpg -e -r ubuntu ~ubuntu/data.tar.gz
```

Ini akan membuat file terenkripsi data.tar.gz.gpg yang dapat Anda gunakan, di folder yang sama dengan file input.

# Encrypt Files using Nautilus GUI

If you are not into using the terminal, you might want to have a beautiful GUI in order to encrypt your files.

To encrypt using a graphical interface, you are going to use the “Nautilus” file manager along with the ```seahorse-nautilus``` extension. This extension brings GPG features right into your graphical file explorer.

```
sudo apt-get install nautilus
```

```
sudo apt-get install seahorse-nautilus
```

When you are done, restart Nautilus by using the ```nautilus``` command with the ```-q``` option for ```quit```.

```
nautilus -q
```