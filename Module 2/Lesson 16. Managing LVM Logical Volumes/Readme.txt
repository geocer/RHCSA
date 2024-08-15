#Partitions
cat /proc/partitions
fdisk /dev/sdb
mkfs.xfs -L LABEL /dev/sdb1
mount /dev/sdb1 /mnt
blkid

#LVM Create
fdisk /dev/sdb
p
n
p
partition number
t
partition number
8e
w
partprobe

pvcreate /dev/sdb3
pvs
vgcreate vg_data /dev/sdb3
vgs
lvcreate -n lv_data -L 100M vg_data
lvextend -l +100%FREE /dev/vg_data/lv_data
lvdisplay 
lvs
mkfs.ext2 /dev/vg_data/lv_data
mount /dev/vg_data/lv_data /mnt

#LVM extend
df -h
fdisk /dev/sdb
partprobe
vgextend vg_data /dev/sdb5
lvextend  -l +100%FREE -r /dev/vg_data/lv_data

#LVM shirink
umount /moredata

#file system manual
e2fsck -f /dev/vg_data/lv_data
resize2fs /dev/vg_data/lv_data 100M
lvreduce -L 102400K /dev/vg_data/lv_data

#file system automatico -r
lvreduce -L 50M -r /dev/vg_data/lv_data
