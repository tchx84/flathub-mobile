## To mimic the screen setup:

```
$ xrandr --newmode 720x1280_60.00  77.50  720 776 848 976  1280 1283 1293 1327 -hsync +vsync
$ xrandr --addmode Virtual-1 720x1280_60.00
$ xrandr --output Virtual-1 --mode 720x1280_60.00
$ gsettings set org.gnome.desktop.interface scaling-factor 2
```

## To run the GTK fork:

```
$ git --single-branch --branch gtk-flathub-mobile clone https://gitlab.gnome.org/tchx84/gtk.git
$ cd gtk
$ meson _build .
$ cd _build
$ ninja
$ sudo ninja install
```
