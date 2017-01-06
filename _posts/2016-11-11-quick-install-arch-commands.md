---
layout: post
title: quick install arch commands
categories:
  - linux
---

## prepare wifi

wifi-menu

## use first partion of built-in flash memory, do not delete and create partition. It should be Microsoft Data partition type.

fdisk /dev/mmcblk0
mkfs.ext4 /dev/mmcblk0p1
mount /dev/mmcblk0p1 /mnt

## install base

pacman-key --refresh-keys
pacstrap /mnt base tmux vim git make zsh 
genfstab -p /mnt >> /mnt/etc/fstab

## change root
arch-chroot /mnt

## install tmux and get personalized conf 
cd /root && git clone https://github.com/jkoz/home && cd home && make
sed -i -e 's!#en_US.UTF-8 UTF-8!en_US.UTF-8 UTF-8!' -e 's!#en_US ISO-8859-1!en_US ISO-8859-1!' /etc/locale.gen && locale-gen
zsh && tmux

echo "archlinux" > /etc/hostname

pacman -S elinks fbterm wget openssh sudo grub net-tools wireless_tools wpa_actiond ifplugd rfkill axel alsa-utils dosfstools\
    samba ruby ctags bc dialog imagemagick socat the_silver_searcher htop cups cdrkit dvd+rw-tools zip unzip unrar mutt
loadkeys /usr/share/kbd/keymaps/i386/qwerty/emacs2.map.gz

kbdrate -d 30  -r 400

usermod -s /usr/bin/zsh root
passwd

useradd -m -g users -G audio,lp,optical,storage,video,wheel,games,power -d/home/tait -s /usr/bin/zsh tait
passwd tait

pacman -S --noconfirm yajl base-devel
cd /tmp
curl https://aur.archlinux.org/cgit/aur.git/snapshot/package-query.tar.gz | tar xz && cd package-query && makepkg && sudo pacman -U package-query*xz
curl https://aur.archlinux.org/cgit/aur.git/snapshot/yaourt.tar.gz | tar xz && cd yaourt && makepkg && sudo pacman -U yaourt*any.pkg.tar.xz

grub-install /dev/mmcblk1
grub-mkconfig -o /boot/grub/grub.cfg

# font
yaourt -S --noconfirm ttf-monaco ttf-mac-fonts ttf-ms-fonts google-chrome

# tex 
pacman -S --noconfirm textlive-most ghostscript pandoc pandoc-citeproc  gdrive scrot


# ui
pacman -S --noconfirm xorg xorg-server xorg-xinit xclip feh xdotool zathura tabbed zathura-pdf-mupdf alsa-utils mplayer slock xautolock x11vnc
pacman -S --noconfirm libreoffice 

