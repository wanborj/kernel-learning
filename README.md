ubuntu
======

learn something which is easy to forget about ubuntu 

---

##fdisk

<pre>
<code>
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
</code>
</pre>

##root 登陆设置
<pre>
Ubuntu 12.04默认是不允许root登录的，在登录窗口只能看到普通用户和访客登录。以普通身份
登陆Ubuntu后我们需要做一些修改,普通用户登录后，修改系统配置文件需要切换到超级用户模式,
在终端窗口里面输入: sudo  -s.然后输入普通用户登陆的密码，回车即可进入 root用户权限模式。

然后执行: vi /etc/lightdm/lightdm.conf.

增加 greeter-show-manual-login=true  allow-guest=false  . 修改完的整个配置文件是

[SeatDefaults]
greeter-session=unity-greeter
user-session=ubuntu
greeter-show-manual-login=true #手工输入登陆系统的用户名和密码
allow-guest=false   #不允许guest登录

然后我们启动root帐号：
sudo passwd root

根据提示输入roott帐号密码。

重启ubuntu，登录窗口会有“登录”选项，这时候我们就可以通过root登录了。

Ubuntu 12.04默认使用unity界面，不同的用户体验，但是对于从上一个LTS版本过来的我来说，
gnome classic界面更容易上手。

首先我们需要安装gnome shell，sudo apt-get install gnome-session-fallback

记得在登录框右上选择gnome（classic)
</pre>
##mkfs##
<pre>
<code>
the primary skills are:
sudo mkfs.ext4 /dev/sda2
sudo mkfs.vfat /dev/sda4
...
</code>
</pre>

