# EXAM
19.12.2017

## 1. Installation of virtual machines from scratch (30%)
* Enabled SELinux with targeted policy
* Root password is set to asdf
* Two virtual machines accessible via the names mars and venus
* venus will have 1 (system) + 3 virtual disks
	* content is persistent

## 2. Cluster (30%)
* Create a 2-node cluster
* Create an NFS mount point on top of the exported disk (look at storage part) that will fail-over to the second node if needed (mount to /mnt/nfsdata)
* This mounpoint run on venus if possible

## 3. Storage (30%)
* Create mirror (same content on both disks) on top of the virtual disks on venus
* Export disk from venus to both of the machines
	* We can assume that it will be mounted only once in any time
	* Create two files with different md5sum checksum that will have 75% of capacity of RAID on that disk
	* It should be mountable /mnt/bigdata on any of the machines (mount /mnt/bigdata)

## 4. (10%)
* Install apache on venus, run it and do not response to requests from mars at all.
