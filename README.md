# check_disk_on_lxc
nagios plugin
This is a simple nagios plugin to monitoring the disk usage percentage, when you are working inside LXC container on proxmox.
It is based on df command to gather info about disk and awk to manipulate output.
Inside LXC container the disk info is misaligned from inside and outside container.
For example for  my LXC container from host I read (from lvs command):
vm-101-disk-1 LSize:36.00g Data% 68.99
this values are in Gib (Gibibyte)
From inside container with dh command I read:
Filesystem: /dev/mapper/pve-vm--101--disk--1 Size 38G Use% 51%
and this values are in more useful format GB (Gigabyte). I need this values!
