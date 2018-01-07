# Startup of VM

1. Execute `chmod +x /etc/rc.local`

2. Open `/etc/rc.local` in text editor, e.g. `vi /etc/rc.local`

3. Add your commands which will be executed at startup of virtual machine

    * e.g.:

        `pcs cluster start`

        `losetup -f /root/file`

4. Reboot
