# EXAM
23.1.2018

## 1. Installation of virtual machines from scratch (30%)
* Enabled SELinux with targeted policy
* Root password is set to asdf
* Two virtual machines accessible via the names ice and snow
* You can use 'real' disks in virtual machine

## 2. Storage (30%)
* Create mirror disks (same data are on two disks)
* Data are encrypted and they are open automatically during reboot
* Export data to both of the nodes so they can see same content of same block device
* Do not attempt to make it fail-over
* Persistent

## 3. Cluster (40%)
* Create a 2-node cluster
* Setup (fake) fencing
	* With option 'pcmk_monitor_action=metadata' you can use any fence agent
	* Be aware that some agents can be used only on single machine
* Prepare mount point for /mnt/gfs2 (filesystem gfs2)- so root can mount it via 'mount /mnt/gfs2' on both machines
