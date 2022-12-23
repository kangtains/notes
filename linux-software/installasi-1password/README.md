# 1Password

1Password adalah aplikasi yang memungkinkan pengguna untuk menyimpan dan mengelola kata sandi mereka dengan aman. Aplikasi ini memungkinkan pengguna untuk menyimpan kata sandi mereka dalam satu tempat yang aman dan mudah diakses, sehingga mereka tidak perlu mengingat banyak kata sandi yang berbeda untuk akun yang berbeda. Selain itu, aplikasi ini juga memungkinkan pengguna untuk membuat kata sandi yang aman secara otomatis, sehingga mereka tidak perlu khawatir tentang keamanan kata sandi mereka.

Aplikasi 1Password Linux tersedia untuk semua distribusi Linux utama termasuk Ubuntu, Fedora, dan Arch.

Anda dapat menambahkan repo 1Password resmi ke sistem Anda untuk menginstalnya menggunakan manajer paket pilihan Anda, tetapi cara termudah untuk menginstal 1Password di Ubuntu adalah dengan mengunduh paket penginstal di bawah, dan menginstalnya menggunakan aplikasi Perangkat Lunak Ubuntu.

Meskipun tersedia, aplikasi Snap 1Password tidak memiliki integrasi browser web serta metode otentikasi sistem yang mendasarinya. Ini menjadikannya pilihan yang kurang menarik daripada paket instal biasa yang tersedia IMO, tetapi ada jika Anda menginginkannya.

## Kelebihan
Beberapa kelebihan dari aplikasi 1Password adalah:

* Memungkinkan pengguna untuk menyimpan dan mengelola kata sandi mereka dengan aman dalam satu tempat yang mudah diakses.
* Memungkinkan pengguna untuk membuat kata sandi yang aman secara otomatis.
* Dapat bekerja di berbagai perangkat, seperti komputer, smartphone, dan tablet.
* Dapat digunakan untuk menyimpan informasi penting lainnya, seperti nomor kartu kredit atau informasi pribadi lainnya.
* Dapat digunakan secara offline, sehingga pengguna tidak perlu terhubung ke internet untuk mengakses informasi yang tersimpan.
* Memiliki fitur keamanan yang kuat, sehingga informasi yang tersimpan tidak bisa diakses oleh orang lain.
* 1Password for Linux supports
* Automatic Dark Mode selection based on your GTK theme
* Open network locations (FTP, SSH, SMB)
* Integration with GNOME, KDE, and other window managers
* System tray icon
* Open and fill in your default browser
* X11 clipboard integration and clearing
* GNOME Keyring and KDE Wallet support
* Kernel keyring integration
* DBUS API support
* Command line API
* Integration with system lock and idle services

## Installasi di Ubuntu

Pertama instal curl dengan menjalankan perintah di bawah ini:

```
sudo apt update
```

```
sudo apt install curl
```

Next, add 1Password repository key to Ubuntu/Debian

```
curl -sS https://downloads.1password.com/linux/keys/1password.asc | sudo gpg --dearmor --output /usr/share/keyrings/1password-archive-keyring.gpg
```

Then create a repository file.

```
echo 'deb [arch=amd64 signed-by=/usr/share/keyrings/1password-archive-keyring.gpg] https://downloads.1password.com/linux/debian/amd64 stable main' | sudo tee /etc/apt/sources.list.d/1password.list
```

To verify packages signatures and make sure they’re authentic, add lines below:

```
sudo mkdir -p /etc/debsig/policies/AC2D62742012EA22/
```

```
curl -sS https://downloads.1password.com/linux/debian/debsig/1password.pol | sudo tee /etc/debsig/policies/AC2D62742012EA22/1password.pol
```

```
sudo mkdir -p /usr/share/debsig/keyrings/AC2D62742012EA22
```

```
curl -sS https://downloads.1password.com/linux/keys/1password.asc | sudo gpg --dearmor --output /usr/share/debsig/keyrings/AC2D62742012EA22/debsig.gpg
```

Terakhir, jalankan perintah di bawah ini untuk memperbarui dan menginstal 1Password

```
sudo apt update && sudo apt install 1password
```

## Installasi di Fedora

If you’re using a Fedora workstation or a Red Hat-based Linux system, you need to run the following rpm command on your shell to import the GPG keys of 1password on your machine.

```
sudo rpm --import https://downloads.1password.com/linux/keys/1password.asc
```

Now, run the following echo command to get the updated 1password repository for your Red Hat/Fedora system.

```
sudo sh -c 'echo -e "[1password]\nname=1Password Stable Channel\nbaseurl=https://downloads.1password.com/linux/rpm/stable/\$basearch\nenabled=1\ngpgcheck=1\nrepo_gpgcheck=1\ngpgkey=\"https://downloads.1password.com/linux/keys/1password.asc\"" > /etc/yum.repos.d/1password.repo'
```

Finally, run the following DNF/YUM command on the terminal shell to install the 1password tool on your Linux system. If you’re using an upgraded Fedora workstation, you can also run the YUM on the shell.

```
sudo dnf install 1password
```

```
sudo yum install 1password
```

## Installasi di Arch

Installing the 1password tool on an Arch or Arch-based Linux requires the root privilege and the basic knowledge of Git. First, run the following cURL command to get the GPG key of 1password for the Arch system.

```
curl -sS https://downloads.1password.com/linux/keys/1password.asc | gpg --import
```

Now, run the git command to download the 1password package file from your system.

```
git clone https://aur.archlinux.org/1password.git
```

When the download finishes, run the following commands to install the 1password tool on your Arch Linux system.

```
cd 1password
```

```
makepkg -si
```

### Source
* [ubuntupit.com](https://www.ubuntupit.com/how-to-install-and-set-up-1password-on-linux-desktop/)