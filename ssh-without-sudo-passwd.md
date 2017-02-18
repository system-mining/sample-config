## Sudo without password

**Description**

> You want to run sudo command without type password like EC2 instance on Aws
>
> Warning: This may be make your system less security than using password for sudo, make sure that you has been disable ssh by password
>
> Specs:
>
> * Ubuntu 16.04

**Config**

```
#sudo visudo

#Add command bellow and save it
your_user ALL=(ALL) NOPASSWD:ALL
```

**Source**

* [http://superuser.com/questions/492405/sudo-without-password-when-logged-in-with-ssh-private-keys](http://superuser.com/questions/492405/sudo-without-password-when-logged-in-with-ssh-private-keys)
* [http://security.stackexchange.com/questions/9308/sudo-password-when-authenticating-via-passwordless-ssh](http://security.stackexchange.com/questions/9308/sudo-password-when-authenticating-via-passwordless-ssh)

**Extra Information**

TOBEUPDATE

**Tags**

\#ssh \#sudo \#sudo\_password

