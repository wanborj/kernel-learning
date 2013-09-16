ubuntu
======

learn something which is easy to forget about ubuntu 

---

##fdisk

<pre>
wanbo@wanbo-Rev-1-0:~$ fdisk /dev/sda
fdisk: unable to open /dev/sda: Permission denied
wanbo@wanbo-Rev-1-0:~$ sudo fdisk /dev/sda
[sudo] password for wanbo: 

Command (m for help): m
Command action
   a   toggle a bootable flag
   b   edit bsd disklabel
   c   toggle the dos compatibility flag
   d   delete a partition
   l   list known partition types
   m   print this menu
   n   add a new partition
   o   create a new empty DOS partition table
   p   print the partition table
   q   quit without saving changes
   s   create a new empty Sun disklabel
   t   change a partition's system id
   u   change display/entry units
   v   verify the partition table
   w   write table to disk and exit
   x   extra functionality (experts only)

Command (m for help): p

Disk /dev/sda: 320.1 GB, 320072933376 bytes
255 heads, 63 sectors/track, 38913 cylinders, total 625142448 sectors
Units = sectors of 1 * 512 = 512 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes
Disk identifier: 0xad250a1f

   Device Boot      Start         End      Blocks   Id  System
/dev/sda2            2048   266258429   133128191   83  Linux
/dev/sda3       266258430   625139711   179440641    f  W95 Ext'd (LBA)
/dev/sda5       430098432   625139711    97520640    7  HPFS/NTFS/exFAT
/dev/sda6       271894528   430098431    79101952   83  Linux
/dev/sda7       266258432   271892479     2817024   82  Linux swap / Solaris

Partition table entries are not in disk order
<pre>

---

##mkfs##

<pre>
SEE ALSO
fs(5),  badblocks(8),  fsck(8),  mkdosfs(8), mke2fs(8), mkfs.bfs(8), mkfs.ext2(8),
mkfs.ext3(8), mkfs.ext4(8), mkfs.minix(8), mkfs.msdos(8),mkfs.vfat(8), mkfs.xfs(8), 
mkfs.xiafs(8)

the primary skills are:
* sudo mkfs.ext4 /dev/sda2
* sudo mkfs.vfat /dev/sda4
* ...
<pre>
