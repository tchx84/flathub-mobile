## Building OS

```
$ mkdir tinchOS
$ cd tinchOS

$ git --single-branch --branch tinchOS clone https://gitlab.com/tchx84/pmbootstrap
$ git --single-branch --branch tinchOS clone https://gitlab.com/tchx84/pmaports

$ ln -s pmbootstrap/pmbootstrap.py ~/.local/bin/pmbootstrap

$ mkdir -p workspace/cache_git/
$ ln -s pmaports workspace/cache_git/pmaports

$ pmbootstrap init --work $PWD/workspace
$ pmbootstrap install
$ pmbootstrap flasher flash_rootfs
$ pmbootstrap flasher flash_kernel
```

## Setting Flatpak

```
$ ssh tchx84@192.168.100.62

$ sudo mkdir /flatpak
$ sudo fdisk -l
$ sudo vi /etc/fstab # see content below
$ sudo mount -a

$ mkdir /flatpak/extra

$ sudo mkdir -p /etc/flatpak/installations.d
$ sudo vi /etc/flatpak/installations.d/extra.conf # see content below

$ sudo flatpak --installation=extra remote-add flathub https://flathub.org/repo/flathub.flatpakrepo
```

### fstab

```
/dev/mmcblk1    /flatpak        ext4    defaults 0 2
```

### extra.conf

```
[Installation "extra"]
Path=/flatpak/extra
DisplayName=Extra Installation
StorageType=harddisk
```
