# VM SETUP

## Download and install [VirtualBox](https://www.virtualbox.org/)

## Download [CentOS](https://www.centos.org/) **everything iso** image

## Run VirtualBox & Setup a VM:

#### Add a new VM

1. Click on `New`

2. Customize VM

	* Name: `VM1`

	* Type: `Linux`

	* Version: `Other Linux (64-bit)`

	![Add VM p1](https://github.com/europ/VUTBR-FIT-ILI/blob/master/img/ILI_1.png)

3. Click on `Create`

	![Add VM p2](https://github.com/europ/VUTBR-FIT-ILI/blob/master/img/ILI_2.png)

3. Click on `Create`

#### Configuring added VM

1. Select `VM1`

2. `Settings` -> `Storage`

3. Click on :cd: `Empty`

4. In Attributes click on icon :cd: and select `Choose Virtual Optical Disk File` -> choose the downloaded CentOS **everything iso** image

5. `OK`

![VM Settings](https://github.com/europ/VUTBR-FIT-ILI/blob/master/img/ILI_3.png)

#### Launching added VM

1. Select `VM1`

2. `Start`

3. `SOFTWARE SELECTION` - enable `Development Tools` than click on `Done` 

4. `INSTALLATION DESTINATION` - click on `ATA VBOX HARDDISK` than click on `Done`

5. `Begin Installation`

6. `ROOT PASSWORD` - set your password e.g. `root`

7. `Reboot`

#### Using added VM

1. Login into `VM1`:

	* Login: `root`

	* Password: `root`

2. Name the VM e.g. `vm1`, execute `hostnamectl set-hostname "vm1"`

## Connecting VM to the internet

#### Configuring network of VM

1. Select `VM1`

2. `Settings`

3. `Network` -> `Adapter 1` -> `Enable Network Adapter` -> Choose `Host-only Adapter`

	![Add VM p2](https://github.com/europ/VUTBR-FIT-ILI/blob/master/img/ILI_6.png)

4. `Network` -> `Adapter 2` -> Choose `NAT`

	![Add VM p2](https://github.com/europ/VUTBR-FIT-ILI/blob/master/img/ILI_7.png)

5. `OK`

6. `Start` `VM1`

7. Login into `VM1`

8. Execute `cd /etc/sysconfig/network-scripts`

9. Edit file `ifcfg-interface_name` e.g. `ifcfg-enp0s3`, not `ifcfg-lo` - loopback interface, via text editor e.g. `vi`

10. Change `ONBOOT` value from `no` to `yes`

11. Save the file and reboot

12. You are now connected to the internet, try out `ping 8.8.8.8`

13. If you would like to work with the virtual maching `VM1` via your shell, get the IP address of the network interface via `ip addr`.

	Open your shell and type `ssh root@IP` e.g. `ssh root@192.168.56.3` and login into virtual machine `VM1`.

	At ssh issue `WARNING: REMOTE HOST IDENTIFICATION HAS CHANGED!` execute command `ssh-keygen -f "/home/USERNAME/.ssh/known_hosts" -R IP` e.g. `ssh-keygen -f "/home/adrian/.ssh/known_hosts" -R 192.168.56.3`

## Clonning VM

1. `Right click` on the VM1

2. Choose `Clone`

3. Name it, e.g `VM2`

	![Add VM p2](https://github.com/europ/VUTBR-FIT-ILI/blob/master/img/ILI_4.png)

4. `Next`

	![Add VM p2](https://github.com/europ/VUTBR-FIT-ILI/blob/master/img/ILI_5.png)

5. `Clone`

6. Select `VM2`

7. `Settings`

8. `Network`

9. `Adapter 1` -> `Advanced` -> Press the icon :arrows_counterclockwise: at `MAC Address`

10. `Adapter 2` -> `Advanced` -> Press the icon :arrows_counterclockwise: at `MAC Address`

11. `OK`

1. Launch and login into `VM2`:

	* Login: `root`

	* Password: `root`

2. Name the VM e.g. `vm2`, execute `hostnamectl set-hostname "vm2"`
