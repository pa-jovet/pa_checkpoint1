# 1.1 Préparation du disque

- `cfdisk /dev/sdb`
- Sélectionner dos
- copie écran cfdisk
- `mkfs.ext4 -L DATA /dev/sdb1`
- `mkswap /dev/sdb2`
- `swapon /dev/sdb2`
- `swapoff /dev/sda5`
- copie ecran lsblk
- copie ecran blkid pour label

# 1.2 Montage
- `mkdir /mnt/data`
- `echo -e "\n\n" >> /etc/fstab`
- `blkid | grep sdb1 >> /etc/fstab`
- `blkid | grep sdb2 >> /etc/fstab`
- copie /etc/fstab
- copie ecran après redémarrage
