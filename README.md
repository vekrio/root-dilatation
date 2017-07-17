# root-dilatation
CENTOS7 根目录扩容


一.创建LVM逻辑分区 
 fdisk -l 查看分区 
 1:分区类型 sdb或sda 
 2,3:接下来要使用的内容 
 二.增加分区 
三.创建物理卷加入组 
pvcreate /dev/sdb1(默认为sdb1) 
vgextend centos(图1的2)/dev/sdb1 
vgdisplay 查看是否成功 
成功后显示的可用空间为你加入的空间大小 
四.扩容 
lvextend -L +90G /dev/centos(图1的2)/root(图1的3) 
fdisk -l查看是否成功扩容 
五.操作生效 
xfs_growfs /dev/centos/root
 

