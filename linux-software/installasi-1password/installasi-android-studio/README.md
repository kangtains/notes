# Android Studio

Android Studio adalah Integrated Development Environment (IDE) resmi untuk pengembangan aplikasi Android, yang didasarkan pada IntelliJ IDEA . Selain sebagai editor kode dan fitur developer IntelliJ yang andal, Android Studio menawarkan banyak fitur yang meningkatkan produktivitas Anda dalam membuat aplikasi Android, seperti:

* Sistem build berbasis Gradle yang fleksibel
* Emulator yang cepat dan kaya fitur
* Lingkungan terpadu tempat Anda bisa mengembangkan aplikasi untuk semua perangkat Android
* Terapkan Perubahan untuk melakukan push pada perubahan kode dan resource ke aplikasi yang sedang berjalan tanpa memulai ulang aplikasi
* Template kode dan integrasi GitHub untuk membantu Anda membuat fitur aplikasi umum dan mengimpor kode sampel
* Framework dan alat pengujian yang lengkap
* Alat lint untuk merekam performa, kegunaan, kompatibilitas versi, dan masalah lainnya
* Dukungan C++ dan NDK
* Dukungan bawaan untuk Google Cloud Platform, yang memudahkan integrasi Google Cloud Messaging dan App Engine

## Sejarah
Software ini diperkenalkan pertama kali pada tahun 2013 di acara Google I/O Conference. Android Studio merupakan software resmi yang didukung penuh oleh Google sebagai perusahaan induk Sistem Operasi Android. IDE ini dikembangkan oleh JetBrains dan dirilis pertama kali ke publik pada tahun 2014.

Sebelum Google meresmikan dan mendukung penuh Android Studio, Google sudah lebih dulu mendukung Eclipse. Dimana dulunya Eclipse adalah software atau IDE yang digunakan oleh para developer android untuk mengembangkan aplikasi android. Namun kini Google sudah menghentikan dukungan penuh terhadap Eclipse.

Meskipun begitu Eclipse masih tetap bisa digunakan untuk mendevelop aplikasi android. Saat ini di tahun 2020 membuat aplikasi menggunakan Eclipse sudah tidak disarankan lagi.

## Installasi di Ubuntu

### Install Android Studio Using Repository

* Add the audio repository
* After JDK is downloaded and installed, you must install the studio repository by executing the command given below.

```
sudo add-apt-repository ppa:maarten-fonville/android-studio
```

* The pop-up will appear in the terminal during installation; hit Enter to carry on with adding the repository, or press C + Ctrl to stop adding the repository to the system.

* Update the system cache
* You should use the below command to update the system’s apt-cache after setting the Android repository successfully:

```
sudo apt update
```

### Install the Android Studio on Ubuntu
It’s now time to use the package manager to download the Android Studio for Ubuntu. The subsequent command will help you install ADB Ubuntu and all of its requirements.

```
sudo apt install android-studio
```

### Install Android Studio Using the Snap

```
Install the snap
```

Ubuntu system already has Snap installed by default. Still, if your system doesn’t have it, install it using the command listed below.

```
sudo apt install snapd
```

### Download and install the JDK
As mentioned in the previous technique, you must first install the JDK on the PC prior to setting up Android Studio. Use the below command to do so.

```
sudo apt install openjdk-11-jdk
```

### Install the Android Studio on Ubuntu

On your Ubuntu system, run the below command to install the Android Studio utilizing snap:

```
sudo snap install android-studio –classic
```
## Installasi di Fedora

### Install Android Studio Using Snap

Android studio is available as a snap package for Fedora operating system. So, first, install the Snap package management on your system.

```
sudo dnf install -y snapd
```

```
sudo ln -s /var/lib/snapd/snap /snap
```

```
sudo snap install core && sudo snap refresh core
```

Then, install Android Studio using the snap command.

```
sudo snap install android-studio --classic
```

The installation will take some time to complete. After installing Android Studio, verify the Android Studio installation using the below command.

```
sudo snap list android-studio
```

Output:

```
Name            Version      Rev  Tracking       Publisher     Notes
android-studio  2021.2.1.14  121  latest/stable  snapcrafters  classic
```

You may need to link the executable to /usr/local/bin directory so that you can start Android Studio using the android-studio command.

```
sudo ln -sf /snap/bin/android-studio /usr/local/bin/android-studio
```

### Install Android Studio From Official Archive

First, install 32-bit libraries for Android Studio installation.

```
sudo dnf install -y zlib.i686 ncurses-libs.i686 bzip2-libs.i686
```

Then, open a web browser and visit the below link to download the latest version of Android Studio from the official website.

OR

Use the below command to download the Android Studio package using the terminal.

```
cd /tmp
```

```
wget https://dl.google.com/dl/android/studio/ide-zips/2021.2.1.14/android-studio-2021.2.1.14-linux.tar.gz
```

Next, extract the downloaded archive using the tar command.

```
sudo tar -zxvf android-studio-*-linux.tar.gz
```

```
sudo mv android-studio /opt/
```

Then link the executable to /bin directory so that you can start Android Studio using the android-studio command.

```
sudo ln -sf /opt/android-studio/bin/studio.sh /usr/local/bin/android-studio
```

You may like to create a desktop entry so that you can start Android Studio from the Activities menu.

```
sudo vi /usr/share/applications/android-studio.desktop
```

Use the following information in the above file.

```
[Desktop Entry]
Version=1.0
Type=Application
Name=Android Studio
Comment=Android Studio
Exec=bash -i "/opt/android-studio/bin/studio.sh" %f
Icon=/opt/android-studio/bin/studio.png
Categories=Development;IDE;
Terminal=false
StartupNotify=true
StartupWMClass=jetbrains-android-studio
Name[en_GB]=android-studio.desktop
```

### Source

* [explorateglobal.com](https://www.explorateglobal.com/blog/install-android-studio-on-ubuntu-and-linux/)
* [itzgeek.com](https://www.itzgeek.com/how-tos/linux/fedora-how-tos/install-android-studio-on-fedora.html)