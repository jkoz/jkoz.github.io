---
layout: post
title: quick install arch commands
categories:
  -
---
```sh
loadkeys /usr/share/kbd/keymaps/i386/qwerty/emacs2.map.gz
kbdrate -d 30  -r 400

fdisk /dev/sda
mount /dev/sda1 /mnt

pacstrap /mnt base vim tmux git openssh

genfstab -p /mnt >> /mnt/etc/fstab


pacman -S wget openssh sudo git zsh grub net-tools wireless_tools wpa_actiond ifplugd rfkill axel alsa-utils \
    samba make ctags bc dialog imagemagick socat the_silver_searcher htop cups cdrkit dvd+rw-tools zip unzip unrar

echo "archlinux" > /etc/hostname

ln -s /usr/share/zoneinfo/Canada/Mountain /etc/localtime

sed -i 's!#en_US.UTF-8 UTF-8!en_US.UTF-8 UTF-8!' /etc/locale.gen
sed -i 's!#en_US ISO-8859-1!en_US ISO-8859-1!' /etc/locale.gen
locale-gen

echo "KEYMAP=\"emacs2\"" > /etc/vconsole.conf

grub-install /dev/sda
grub-mkconfig -o /boot/grub/grub.cfg

usermod -s /usr/bin/zsh root
passwd

useradd -m -g users -G audio,lp,optical,storage,video,wheel,games,power -d/home/tait -s /usr/bin/zsh tait
passwd tait

sudoedit /etc/sudoers

pacman -S --noconfirm xorg xorg-server xorg-xinit xclip feh xdotool zathura tabbed zathura-pdf-mupdf alsa-utils mplayer slock xautolock x11vnc


pacman -S --noconfirm yajl base-devel
cd /tmp
curl https://aur.archlinux.org/cgit/aur.git/snapshot/package-query.tar.gz | tar xz && cd package-query && makepkg && sudo pacman -U package-query*xz
curl https://aur.archlinux.org/cgit/aur.git/snapshot/yaourt.tar.gz | tar xz && cd yaourt && makepkg && sudo pacman -U yaourt*any.pkg.tar.xz

yaourt -S --noconfirm ttf-monaco ttf-mac-fonts ttf-ms-fonts google-chrome

pacman -S --noconfirm libreoffice textlive-most pandoc pandoc-citeproc ruby
```
