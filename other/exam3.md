# EXAM
9.1.2018

## 1. Installation of virtual machines from scratch (30%)
* Enabled SELinux with targeted policy
* Root password is set to asdf
* Two virtual machines accessible via the names foo and bar

## 2. Cluster (45%)
* Create a 2-node cluster
* Create an NFS mount point that will fail-over to the second node if needed
    * It is NOT required to have same data on both of these machines
* Prepare mount of this NFS mount point on both of the nodes
    * They should be mounted manually via command 'mount /mnt/nfsdata'
* Run Apache on top of the cluster
    * Content should not be available from host machine (preferably use firewalld)

## 3. Storage (25%)
* Use only loopback disks
* Create systemd unit file (with templates) to start existing loopback devices
* Data are unencrypted at the boot time automatically
* Create a scenario with following properties
    * Encrypted data
    * One RAID-6 disk arrays with minimal number of disks required to be in normal state
