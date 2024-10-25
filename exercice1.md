# 1.1 Préparation du disque

- `cfdisk /dev/sdb`
- Sélectionner dos

![cfdisk](/exo1/cfdisk.png)

- `mkfs.ext4 -L DATA /dev/sdb1`
- `mkswap -L SWAP /dev/sdb2`
- `swapon /dev/sdb2`
- `swapoff /dev/sda5`

![cfdisk](/exo1/lsblk.png)

- Le label DATA a bien été attribué à sdb1 et le label SWAP à sdb2 (après correction de la ligne de code utilisée sur le screenshot) ; sdb1 est bien en ext4 et sdb2 en swap :

![cfdisk](/exo1/blkid.png)


# 1.2 Montage
- `mkdir /mnt/data`
- `echo -e "\n\n" >> /etc/fstab`
- `blkid | grep sdb1 >> /etc/fstab`
- `blkid | grep sdb2 >> /etc/fstab`

![cfdisk](/exo1/etcfstab.png)

![cfdisk](/exo1/reboot.png)
