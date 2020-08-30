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

## Installing apps

```
$ sudo flatpak --installation=extra install flathub com.uploadedlobster.peek
$ sudo flatpak --installation=extra install flathub org.gnome.Epiphany org.librehunt.Organizer
$ sudo flatpak --installation=extra install flathub org.librehunt.Organizer
$ sudo flatpak --installation=extra install flathub org.gnome.Fractal
$ sudo flatpak --installation=extra install flathub org.gabmus.notorious
$ sudo flatpak --installation=extra install flathub de.haeckerfelix.Shortwave
$ sudo flatpak --installation=extra install flathub org.gnome.clocks
$ sudo flatpak --installation=extra install flathub org.gnome.Weather
$ sudo flatpak --installation=extra install flathub org.gnome.Lollypop
$ sudo flatpak --installation=extra install flathub org.gnome.Cheese
$ sudo flatpak --installation=extra install flathub org.gnome.SoundRecorder
$ sudo flatpak --installation=extra install flathub org.gabmus.gfeeds
$ sudo flatpak --installation=extra install flathub org.gnome.Podcasts
$ sudo flatpak --installation=extra install flathub re.sonny.Tangram
$ sudo flatpak --installation=extra install flathub org.gnome.gitlab.YaLTeR.VideoTrimmer
$ sudo flatpak --installation=extra install flathub com.github.tchx84.Flatseal
$ sudo flatpak --installation=extra install flathub com.github.Johnn3y.Forklift
$ sudo flatpak --installation=extra install flathub uk.co.ibboard.cawbird
$ sudo flatpak --installation=extra install flathub com.github.bleakgrey.tootle
$ sudo flatpak --installation=extra install flathub org.gnome.Documents
$ sudo flatpak --installation=extra install flathub org.gnome.Evince
$ sudo flatpak --installation=extra install flathub net.baseart.Glide
$ sudo flatpak --installation=extra install flathub org.gnome.Geary
$ sudo flatpak --installation=extra install flathub org.gnome.Contacts
$ sudo flatpak --installation=extra install flathub org.gnome.Maps
$ sudo flatpak --installation=extra install flathub org.gnome.Calculator
$ sudo flatpak --installation=extra install flathub org.gnome.eog
$ sudo flatpak --installation=extra install flathub de.haeckerfelix.Fragments
$ sudo flatpak --installation=extra install flathub com.github.bilelmoussaoui.Authenticator
```
