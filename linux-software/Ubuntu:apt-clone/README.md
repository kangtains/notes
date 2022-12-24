# Ubuntu:apt-clone

Installasi

```
sudo apt install apt-clone
```

cara backup

```
sudo apt-clone clone /home/tain/Documents/backupapt/
```

atau

```
sudo apt-clone clone --with-dpkg-repack /home/tain/Documents/backupapt/
```

Informasi setelah di clone

```
apt-clone info /home/tain/Documents/backupapt/
```
restore backup


```
sudo apt-clone restore /home/tain/Documents/backupapt/
```

## Source
* [2daygeek.com](https://www.2daygeek.com/apt-clone-backup-installed-packages-and-restore-them-on-fresh-ubuntu-system/)