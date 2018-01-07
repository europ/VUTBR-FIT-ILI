# FTP

1. Setup a VM ([example](https://github.com/europ/VUTBR-FIT-ILI/blob/master/other/setup.md))

2. Run and login into `VM1`

3. Execute following commands:

* `yum install vsftpd ftp -y`

* Edit vsftpd configuration file: `vi /etc/vsftpd/vsftpd.conf`

* Find the following lines and make the changes as shown below:
```sh
## Disable anonymous login ##
anonymous_enable=NO

## Uncomment ##
ascii_upload_enable=YES
ascii_download_enable=YES

## Uncomment - Enter your Welcome message - This is optional ##
ftpd_banner=Welcome to UNIXMEN FTP service.

## Add at the end of this  file ##
use_localtime=YES
```

* `systemctl enable vsftpd`

* `systemctl start vsftpd`

* `firewall-cmd --permanent --add-port=21/tcp`

* `firewall-cmd --permanent --add-service=ftp`

* `firewall-cmd --reload`

* `setsebool -P ftp_home_dir on`

* `useradd sk`

* `passwd sk`

* Try it `ftp localhost`

* `ftp IP_VM1`

## HELP:
* https://www.unixmen.com/install-configure-ftp-server-centos-7/