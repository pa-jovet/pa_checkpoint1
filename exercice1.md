# 1.1 Préparation du disque

- `cfdisk /dev/sdb`
- Sélectionner dos

![cfdisk](/exo1/cfdisk.png)

- `mkfs.ext4 -L DATA /dev/sdb1`
- `mkswap /dev/sdb2`
- `swapon /dev/sdb2`
- `swapoff /dev/sda5`

![cfdisk](/exo1/lsblk.png)

- Label SWAP manquait à sdb2 :
  - `swapoff /dev/sdb2`
  - `mkswap -L SWAP /dev/sdb2`
  - `swapon /dev/sdb2`

![cfdisk](/exo1/blkid.png)


# 1.2 Montage
- `mkdir /mnt/data`
- `echo -e "\n\n" >> /etc/fstab`
- `blkid | grep sdb1 >> /etc/fstab`
- `blkid | grep sdb2 >> /etc/fstab`

![cfdisk](/exo1/etcfstab.png)

![cfdisk](/exo1/reboot.png)
