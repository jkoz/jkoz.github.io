---
layout: post
title: Flashing new rom for Nexus 7
categories:
  - android
---

# Unlock android

- Enable USB debug on android OS

`
adb reboot bootloader
fastboot oem unlock
`

# Install Custom Recovery (Multirom)

- Power off nexus 7

- Combine power and vol down to go to bootloader

- Flash twrp recovery (Google: flo nexus 7 twrp)

`
fastboot flash recovery ~/Downloads/nexus7/twrp-3.0.0-0-flo.img
`

- Root device: go to bootloader -> recovery mode (twrp) -> install SuperSu zip file (Google: supersu)

- Install Multirom from GooglePlay

- Install Busybox from GooglePlay, open busybox app, process to install

- Note:
    + In the recovery mode => press both power and up vol for 3 seconds, then release up vol, but keep power button.

# Build custom initramfs

`
cd ~/Repo/arch-flo/systemd-initramfs/ && find . | cpio -o -H newc | gzip > ~/Downloads/nexus7/initrd.img 
`

`
adb push ~/Downloads/nexus7/initrd.img /sdcard/Download
`

`
mv /sdcard/Download/initrd.img /data/media/0/multirom/roms/Arch/boot/initrd.img
`

# Build flo kernel

`
git checkout -b android-6.0.1_r16 a314b7c
make flo_defconfig

export ARCH=arm
export SUBARCH=arm
export CROSS_COMPILE=arm-eabi- 
export PATH=$PATH:$HOME/Repo/arm-eabi-4.7/bin
make -j8
`

`
adb push arch/arm/boot/zImage /sdcard/Download
`

`
mv /sdcard/Download/zImage /data/media/0/multirom/roms/Arch/boot/vmlinuz
`

- Check kernel version

`
make kernelversion
`

# Multirom configuration

`
adb push ~/Repo/arch-flo/multirom/rom_info.txt /sdcard/Download
`

`
mv /sdcard/Download/rom_info.txt /data/media/0/multirom/roms/Arch/rom_info.txt
`

# Prepare Multirom folder for Arch installation

`
mkdir -p /data/media/0/multirom/roms/Arch
mkdir -p /data/media/0/multirom/roms/Arch/root
mkdir -p /data/media/0/multirom/roms/Arch/boot
`
 
# Prepare ARM Arch image

- Use trimslice package from Arch Linux ARM

`
wget http://archlinuxarm.org/os/ArchLinuxARM-trimslice-latest.tar.gz
`

- Create 10G image file for Arch file system

`
# On host machine
dd if=/dev/zero of=root.img bs=1M seek=1000 count=1
mkfs.ext4 root.img
adb push root.img /sdcard/Download
`

- Repeare loop256 for mounting Arch file

`
busybox mknod /dev/loop256 b 7 256
busybox losetup /dev/loop256 /data/media/0/multirom/roms/Arch/root.img
`

- Mount Arch system

`
busybox mount -t ext4 -o rw,noatime /dev/block/loop256 /data/media/0/multirom/roms/Arch/root
`

- Note: mount can be blocked by selinux, need to be unblocked

`
dmesg | tail | grep audit
supolicy --live 'allow kernel media_rw_data_file file read'
`

`
busybox gunzip ArchLinuxARM-trimslice-latest.tar.gz -c | busybox tar x -f - -C /data/media/0/multirom/roms/Arch/root
`

- Adding directories

`
busybox mkdir -p ${CHROOT}/media/sdcard
busybox mkdir -p ${CHROOT}/media/system
busybox mkdir -p ${CHROOT}/dev/pts
busybox mkdir ${CHROOT}/dev/ptmx
`

- Mounting extra file systems

`
busybox mount -o bind /dev/ ${CHROOT}/dev
busybox mount -t proc proc ${CHROOT}/proc
busybox mount -t sysfs sysfs ${CHROOT}/sys
busybox mount -t devpts devpts ${CHROOT}/dev/pts
busybox mount -o bind /sdcard ${CHROOT}/media/sdcard
`

- Installing packages and upgrading system

`
cd $CHROOT
echo "nameserver 8.8.8.8" > af && mv af ${CHROOT}/etc/resolv.conf
echo "nexus7" > af && mv af ${CHROOT}/etc/hostname
`

- Remove trimslice packages

`
busybox rm -rf ${CHROOT}/opt/nvidia
busybox rm -f ${CHROOT}/etc/ld.so.conf.d/nvidia-trimslice.conf
`

- Change root to Arch

`
busybox chroot ${CHROOT} /usr/bin/env HOME=/root TERM="$TERM" PATH=/bin:/usr/bin:/sbin:/usr/sbin /bin/bash
pacman -Syu --ignore systemd
pacman -S xorg-server rxvt-unicode bspwm zsh vim git tmux ruby python3 python2 sudo wget lightdm st
`

- Downgrade systemd to 212-3 as its version, 228-3 does not work with kernel 3.4 (Error as can not mount /sys/fs/cgroup/systemd). Get 212-3 on github https://github.com/omgmog/archarm-usb-hp-chromebook-11/

`
wget https://raw.githubusercontent.com/omgmog/archarm-usb-hp-chromebook-11/master/deps/systemd-212-3-armv7h.pkg.tar.xz
rm -rf /etc/systemd/system/multi-user.target.wants/remote-fs.target /usr/lib/libnss_myhostname.so.2 exists
pacman -Ud systemd-211-3-armv7h.pkg.tar.xz
`

# Full preparation for change root

`
export CHROOT=/data/media/0/multirom/roms/Arch/root
supolicy --live 'allow kernel media_rw_data_file file read'
busybox mount -t ext4 -o rw,loop /data/media/0/multirom/roms/Arch/root.img /data/media/0/multirom/roms/Arch/root
busybox mount -o bind /dev/ ${CHROOT}/dev
busybox mount -t proc proc ${CHROOT}/proc
busybox mount -t sysfs sysfs ${CHROOT}/sys
busybox mount -t devpts devpts ${CHROOT}/dev/pts
busybox mount -o bind /sdcard ${CHROOT}/media/sdcard
busybox mount -o bind /system ${CHROOT}/media/system
busybox chroot ${CHROOT} /usr/bin/env HOME=/root TERM="$TERM" PATH=/bin:/usr/bin:/sbin:/usr/sbin /bin/bash
`
source /etc/profile;
groupadd -g 3003 aid_inet
groupadd -g 3004 inet
groupadd -g 3005 inetadmin
usermod -aG inet root
usermod -aG inetadmin root






# Install arch linux on android using trimslice package

export USER=tait
useradd -m -g users -s /bin/zsh ${USER} # or /bin/bash...
usermod -aG inet ${USER}
usermod -aG inetadmin ${USER}
usermod -aG aid_inet ${USER}
usermod -aG wheel ${USER}
sudoedit /etc/sudoers # uncomment %wheel ALL=(ALL) ALL

mkdir ~/.vnc
cp /media/sdcard/xstartup ~/.vnc
cp /media/sdcard/init-vnc.sh ~/
vncpasswd # set password VNC
~/init-vnc.sh


