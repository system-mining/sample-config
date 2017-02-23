## Limit Directory Access Of A  Ftp User

**Description**

> Retrict a ftp user to access only one directory. example /var/www/html
>
>
>
> Specs
>
> * Ubuntu: 16.04
> * Vsfptd: 3.0

**Config**

```
# vi /etc/vsftpd.conf
# Add the following lines to the end offfile
--------------------------------------------
chroot_local_user=True
local_umask=077
local_root=/var/www/html

# Replace ip with the ip of fpt server
pasv_address=10.10.10.10
pasv_enable=YES
pasv_min_port=13000
pasv_max_port=13100
port_enable=YES
pasv_addr_resolve=YES
# Enable writeable permission of directory
allow_writeable_chroot=YES
```

**Source**

* [http://unix.stackexchange.com/questions/94603/limit-ftp-access-only-to-the-var-www-with-vsftpd](http://unix.stackexchange.com/questions/94603/limit-ftp-access-only-to-the-var-www-with-vsftpd)

**Extra Information**

**Tags**

\#ftp \#vsfpt \#limit\_access



